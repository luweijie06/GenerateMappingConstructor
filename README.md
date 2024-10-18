# GenerateMappingConstructor - IDEA 映射构造器生成插件

GenerateMappingConstructor 是一款强大的 IntelliJ IDEA 插件，用于简化 Java 类之间的对象映射过程。它可以自动生成映射构造器，特别适用于涉及数据传输对象（DTO）和领域对象的项目。

## 主要特性

- 🔍 类选择对话框：轻松搜索和选择源类进行映射
- 🧠 智能字段映射：自动将源类的字段映射到目标类
- 🏷️ Lombok 支持：识别 Lombok 注解的 getter 方法
- 🛠️ 自定义参数名：为源对象选择你喜欢的参数名
- 🔤 模糊搜索：通过模糊匹配快速找到类

## 安装方法

1. 打开 IntelliJ IDEA
2. 进入 `Settings/Preferences` → `Plugins`
3. 搜索 "GenerateMappingConstructor"
4. 点击 `Install` 安装
5. 重启 IntelliJ IDEA

## 使用方法

1. 将光标放在你想要生成构造器的目标类内
2. 右键点击并从上下文菜单中选择 `generate > GenerateMappingConstructor`
3. 在类选择器对话框中，搜索并选择源类
4. 如果需要，自定义参数名
5. 点击 `确定` 生成构造器

## 示例

假设有一个源类 `UserDTO`：

```java
@Data
public class UserDTO {
    private String username;
    private String email;
    private int age;
}
```

和一个目标类 `User`：

```java
public class User {
    private String username;
    private String email;
    private int age;
}
```

GenerateMappingConstructor 将在 `User` 类中生成以下构造器：

```java
public User(UserDTO dto) {
    this.username = dto.getUsername();
    this.email = dto.getEmail();
    this.age = dto.getAge();
}
```

## 技术特点

1. 智能类搜索
    - 支持模糊匹配和精确匹配
    - 实时搜索结果更新
    - 按包名组织搜索结果

2. 字段映射
    - 自动识别同名字段
    - 支持自定义字段对应关系
    - 可视化映射配置界面

3. 代码生成
    - 自动生成标准的 Java 代码
    - 保持代码格式和样式

## 参与贡献

欢迎提交 Issue 和 Pull Request 来帮助改进这个插件！

## 开源协议

本项目采用 Apache-2.0  协议开源 - 详见 [LICENSE](LICENSE) 文件

## 支持

如果你遇到任何问题或有任何疑问，请在 GitHub 项目页面提交 issue。