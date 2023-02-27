# public-config-resources

## Gradle import

``` gradle
buildscript {
    ext.buildScriptRootUrl = 'https://raw.githubusercontent.com/jeongph/public-config-resources/main/gradle'
    apply from: "$buildScriptRootUrl/variables.gradle"
    
    repositories {
//        mavenLocal()
        maven {
            url "${mavenReleasesRepositoryUrl}"
            credentials {
                username System.getenv("MAVEN_USERNAME")
                password System.getenv("MAVEN_PASSWORD")
            }
        }
        mavenCentral()
    }

    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:$springBootVersion")
    }
}
```
