# [Codecov][1] Java Maven Example
## Guide
### Travis Setup

Add to your `.travis.yml` file.
```yml
language: java

script: "mvn cobertura:cobertura"

after_success:
  - bash <(curl -s https://codecov.io/bash)
```
### Produce Coverage Reports
#### Add Cobertura plugin
```xml
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>cobertura-maven-plugin</artifactId>
    <version>2.7</version>
    <configuration>
        <formats>
            <format>html</format>
            <format>xml</format>
        </formats>
        <check />
    </configuration>
</plugin>
```
Call `mvn cobertura:cobertura` during your CI tests, [see here](https://github.com/codecov/example-java-maven/blob/master/.travis.yml#L4)

## Caveats
### Private Repos
Add to your `.travis.yml` file.
```yml
after_success:
  - bash <(curl -s https://codecov.io/bash) -t uuid-repo-token
```
## Support
### FAQ
- Q: Is there a Gradle example?<br/>A: **Yes**, enter [codecov/example-gradle][2]
- Q: Is there a Andorid example?<br/>A: **Yes**, enter [codecov/example-android][3]
- Q: Is there a Jacoc example?<br/>A: **Yes**, enter [codecov/example-java][4]

### Contact
- Intercom (in-app messanger)
- Email: [support@codecov.io](mailto:support@codecov.io)
- Slack: [slack.codecov.io](https://slack.codecov.io)
- [gh/codecov/support](https://github.com/codecov/support)

1. More documentation at https://docs.codecov.io
2. Configure codecov through the `codecov.yml`  https://docs.codecov.io/docs/codecov-yaml

[1]: https://codecov.io/
[2]: https://github.com/codecov/example-gradle
[3]: https://github.com/codecov/example-android
[4]: https://github.com/codecov/example-java
