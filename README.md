# maven-repos
打包时将图片自动转为webp

webp相对于png 和 jpg来说，拥有更高的压缩比，并且提供有损压缩和 无损压缩，即便是在无损压缩的情况下，webp也比png和jpg有更小的体积。本插件在打包时，自动将项目中满足条件的图片进行webp压缩

### 配置环境变量
需要用到webp转换插件，请下载对应的版本并配置好环境变量
https://storage.googleapis.com/downloads.webmproject.org/releases/webp/index.html

配置完后再命令窗口输入cwebp，可查看插件是否配置OK

###引入
maven {url uri('https://raw.githubusercontent.com/xmuyzy/maven-repos/master')}
        
classpath 'com.oi.android.plugin.WebpConvert:webpconvert:1.0.0'

apply plugin: 'com.oi.gradle'

### 配置
webpinfo {
q = 75  //压缩比例 0～100，100是无损压缩，默认75
skipDebug = true //debug下是否开启webp压缩 默认不开启
isShowLog = true //是否打开log
}

### 输出
project.buildDir/outputs/webpcompressoutput.txt 文件中会输出这次替换的结果

### 其他
android-gradle 3.0.0之后：
在工程的gradle.properties中添加
android.enableAapt2=false

