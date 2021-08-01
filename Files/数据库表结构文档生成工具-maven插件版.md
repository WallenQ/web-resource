# 数据库表结构文档生成工具-maven插件版

## 1.功能描述

​		通过配置pom文件，仅需执行maven命令即可生成word、MD或html类型数据库文件

## 2.代码实现

在pom文件中加入如下代码

```xml
<!--导出数据库文档的插件-->
<build>
        <plugins>         

            
            <plugin>
                <groupId>cn.smallbun.screw</groupId>
                <artifactId>screw-maven-plugin</artifactId>
                <version>1.0.3</version>
                <dependencies>
                    <!-- HikariCP -->
                    <dependency>
                        <groupId>com.zaxxer</groupId>
                        <artifactId>HikariCP</artifactId>
                        <version>3.4.5</version>
                    </dependency>
                    <!--mysql driver-->
                    <!--<dependency>
                        <groupId>mysql</groupId>
                        <artifactId>mysql-connector-java</artifactId>
                        <version>8.0.20</version>
                    </dependency>-->
                    <!--oracle驱动-->
                    <dependency>
                        <groupId>com.oracle.ojdbc</groupId>
                        <artifactId>ojdbc8</artifactId>
                        <version>19.3.0.0</version>
                    </dependency>
                    <dependency>
                        <groupId>cn.easyproject</groupId>
                        <artifactId>orai18n</artifactId>
                        <version>12.1.0.2.0</version>
                    </dependency>
                </dependencies>
                <configuration>
                    <!--username-->
                    <username>c##tms</username>
                    <!--password-->
                    <password>tms</password>
                    <!--oracle driver-->
                    <driverClassName>oracle.jdbc.driver.OracleDriver</driverClassName>
                    <!--mysql driver-->
                    <!--<driverClassName>com.mysql.cj.jdbc.Driver</driverClassName>-->
                    <!--jdbc url-->
                    <jdbcUrl>jdbc:oracle:thin:@192.168.145.236:1521/pdborcl</jdbcUrl>
                    <!--生成文件类型,支持 MD、HTML、WORD 格式-->
                    <fileType>HTML</fileType>
                    <!--文件输出目录-->
                    <fileOutputDir>D:\</fileOutputDir>
                    <!--打开文件输出目录-->
                    <openOutputDir>false</openOutputDir>
                    <!--生成模板-->
                    <produceType>freemarker</produceType>
                    <!--文档名称 为空时:将采用[数据库名称-描述-版本号]作为文档名称-->
                    <!--<docName>测试文档名称</docName>-->
                    <!--描述-->
                    <description>数据库文档生成</description>
                    <!--版本-->
                    <version>${project.version}</version>
                    <!--标题-->
                <title>TMS数据库文档</title>
                <!--忽略表前缀-->
                    <tablePrefix>ACT_,QRTZ_,XXL_,API_,CFC_</tablePrefix>
                </configuration>
                <executions>
                    <execution>
                        <phase>compile</phase>
                        <goals>
                            <goal>run</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
            </plugins>
    </build>
```
配置完以后在 maven project->plugins-> screw-> screw:run 双击执行。                

## 3.参考查阅

https://gitee.com/leshalv/screw

