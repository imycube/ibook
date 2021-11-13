# banner

### banner 可以添加多种形式

在classpath（即在resources下）中添加中一个banner.txt文件，将或者banner.location设置到此类文件的位置来更改启动时的Banner。如果文件采用了不一样的编码，设置banner.charset（默认是UTF-8）来解决。除了使用文本文件，还可以将banner.gif，banner.jpg或者banner.png图像文件添加到您的classpath中，或者设置一个banner.image.location属性。图像将会被转换成ASCII的表现形式并打印在任何文本banner上方
```
${spring-boot.version}   输出当前项目的版本号
${spring-boot.formatted-version} Spring Boot版本格式化之后显示（用括号括起来，以 v 为前缀）。例如 (v1.5.4.RELEASE)
${AnsiColor.GREEN}   自定义输出文本的颜色，这边是绿色（其他：RED，YELLOW，BLUE等）
${application.version}  在 MANIFEST.MF 中声明的应用版本号。例如，Implementation-Version: 1.0 将被打印为 1.0
${application.formatted-version} 在 MANIFEST.MF 中声明的应用版本号，格式化之后打印（用括号括起来，以 v 为前缀） 例如 (v1.0)
${application.title}  在 MANIFEST.MF 中声明的应用标题，例如 Implementation-Title: MyApp 打印为 MyApp
```