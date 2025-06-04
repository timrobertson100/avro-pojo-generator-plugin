# avro-pojo-generator-plugin
Maven plugin to convert Avro schemas to Lombok pojos

Expect to be dealing with some bugs!

Something like this should get you going.

```
      <plugin>
        <groupId>org.gbif.maven</groupId>
        <artifactId>avro-pojo-generator</artifactId>
        <version>1.0-SNAPSHOT</version>
        <executions>
          <execution>
            <phase>generate-sources</phase>
            <goals>
              <goal>generate-pojos</goal>
            </goals>
            <configuration>
              <inputDir>src/main/avro</inputDir>
              <outputDir>src/main/java-generated</outputDir>
            </configuration>
          </execution>
        </executions>
        <dependencies>
          <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.17.0</version>
          </dependency>
        </dependencies>
      </plugin>
      
      ...

    <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
    </dependency>
```