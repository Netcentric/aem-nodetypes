[![License](https://img.shields.io/badge/License-EPL%201.0-red.svg)](https://opensource.org/licenses/EPL-1.0)
[![Maven Central](https://img.shields.io/maven-central/v/biz.netcentric.aem/aem-nodetypes)](https://search.maven.org/artifact/biz.netcentric.aem/aem-nodetypes) 
![Java CI/CD](https://github.com/Netcentric/aem-nodetypes/workflows/Java%20CI/CD/badge.svg) 

# Overview
Provides a [CND file][1] with all Node types and Namespaces defined in AEM. It can be used for the [FileVault Validation Module][2] and its `jackrabbit-nodetype` validator.

# Usage with Maven
You can use this module with the [FileVault Package Maven Plugin][3] in version 1.1.4 or higher like this

```
<plugin>
  <groupId>org.apache.jackrabbit</groupId>
  <artifactId>filevault-package-maven-plugin</artifactId>
  <version>1.1.4</version>
  <configuration>
    <validatorsSettings>
      <jackrabbit-nodetypes>
        <options>
          <!-- use the nodetypes and namespaces from the aem-nodetypes.jar provided in the plugin dependencies -->
          <cnds>tccl:aem.cnd</cnds>
        </options>
      </jackrabbit-nodetypes>
    </validatorsSettings>
  </configuration>
  <dependencies>
    <dependency>
      <groupId>biz.netcentric.aem</groupId>
      <artifactId>aem-nodetypes</artifactId>
      <version>2020.11.0</version>
    </dependency>
  </dependencies>
</plugin>
```


[1]: https://jackrabbit.apache.org/jcr/node-type-notation.html
[2]: https://jackrabbit.apache.org/filevault/validation.html
[3]: https://jackrabbit.apache.org/filevault-package-maven-plugin/index.html

# Provided Versions

| Version   |  Type   |  Description |
| --------- | ------- | ------------ |
| 2020.11.0 | Cloud   | Exported from AEM SDK 2020.11.4506.20201112T235200Z. |
| 2020.09.0 | Cloud   | Exported from AEM SDK 2020.9.4194.20200909T200349Z-200827. Suffers from <https://github.com/Netcentric/aem-nodetypes/issues/2> |
| 6.5.7.0   | Classic | Exported from AEM 6.5.7 |
| 6.5.5.0   | Classic | Exported from AEM 6.5.5, has not changed for AEM 6.5.6. Suffers from <https://github.com/Netcentric/aem-nodetypes/issues/2> |

Pick the version which is closest to your AEM version. In general the node types are very stable (i.e. do not change for service packs in Classic and very rarely in Cloud aka AEMaaCS).