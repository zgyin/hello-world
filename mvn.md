有时候你自己的项目依赖了一些jar包在公司私服上面没有 又不好找SA去加 就选择在本地安装相应的jar包吧  
一般寻找jar包去[官网](https://repository.sonatype.org/index.html)  
找到对应的维度信息如：  
`<dependency>  
  <groupId>org.junit</groupId>
  <artifactId>com.springsource.org.junit</artifactId>
  <version>4.7.0</version>
</dependency>`  
使用下面命令安装到本地：  
对应上面例子:`mvn install:install-file -Dfile=E:\extraJar\com.springsource.org.junit-4.7.0.jar -DgroupId=org.junit  -DartifactId=com.springsource.org.junit -Dversion=4.7.0 -Dpackaging=jar`
