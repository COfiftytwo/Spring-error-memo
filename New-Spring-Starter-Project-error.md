# 「入門コンテンツのインポートに問題が発生しました」の解決方法

新規Springスタータープロジェクトでプロジェクトを作成したとき下のエラーに遭遇したことはあるだろうか。
```
NoMatchingConfigurationSelectionException: No matching variant of org.springframework.boot:spring-boot-gradle-plugin:3.0.0 was found. The consumer was configured to find a runtime of a library compatible with Java 11, packaged as a jar, and its dependencies declared externally, as well as attribute 'org.gradle.plugin.api-version' with value '7.5.1' but:
  - Variant 'apiElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.0.0 declares a library, packaged as a jar, and its dependencies declared externally:
      - Incompatible because this component declares an API of a component compatible with Java 17 and the consumer needed a runtime of a component compatible with Java 11
      - Other compatible attribute:
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
  - Variant 'javadocElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.0.0 declares a runtime of a component, and its dependencies declared externally:
      - Incompatible because this component declares documentation and the consumer needed a library
      - Other compatible attributes:
          - Doesn't say anything about its target Java version (required compatibility with Java 11)
          - Doesn't say anything about its elements (required them packaged as a jar)
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
  - Variant 'mavenOptionalApiElements' capability org.springframework.boot:spring-boot-gradle-plugin-maven-optional:3.0.0 declares a library, packaged as a jar, and its dependencies declared externally:
      - Incompatible because this component declares an API of a component compatible with Java 17 and the consumer needed a runtime of a component compatible with Java 11
      - Other compatible attribute:
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
  - Variant 'mavenOptionalRuntimeElements' capability org.springframework.boot:spring-boot-gradle-plugin-maven-optional:3.0.0 declares a runtime of a library, packaged as a jar, and its dependencies declared externally:
      - Incompatible because this component declares a component compatible with Java 17 and the consumer needed a component compatible with Java 11
      - Other compatible attribute:
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
  - Variant 'runtimeElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.0.0 declares a runtime of a library, packaged as a jar, and its dependencies declared externally:
      - Incompatible because this component declares a component compatible with Java 17 and the consumer needed a component compatible with Java 11
      - Other compatible attribute:
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
  - Variant 'sourcesElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.0.0 declares a runtime of a component, and its dependencies declared externally:
      - Incompatible because this component declares documentation and the consumer needed a library
      - Other compatible attributes:
          - Doesn't say anything about its target Java version (required compatibility with Java 11)
          - Doesn't say anything about its elements (required them packaged as a jar)
          - Doesn't say anything about org.gradle.plugin.api-version (required '7.5.1')
java.lang.reflect.InvocationTargetException
```

## 解決策：
プロジェクトを作成するときに「新規Springスタータープロジェクト依存関係」でSpringBootのバージョン変えてみる。
<br>今回のエラーは3.0.0でエラーが出ているので、2.7.7を選んで作成してみると解決した。
<br>
<br>
<img src="https://github.com/COfiftytwo/Spring-error-memo/blob/main/img/Spring-error.png" width="680px" height="339" />
