
[![AppBuilder](https://raw.github.com/Icenium/icenium-cli/release/ab-logo.png "AppBuilder")](http://www.telerik.com/appbuilder "The AppBuilder web site")

<h1 style="padding: 8px; background-color: #f1c40f; color: #34495e; font-weight: bold;">The Telerik Platform product is retired as of May 10, 2018. For more information about the discontinuation and how you can recover your apps or data, see the <a id="platfrom-next-level" style="border: 1px solid #34495e; padding: 3px 8px; margin-left: 10px" href="https://www.telerik.com/platform-next-level">full announcement</a>. </h1><br/>

<h2 style="padding: 8px; background-color: #00FF21; color: #34495e; font-weight: bold;">Telerik recommends <a id="sidekick" style="border: 1px solid #34495e; padding: 3px 8px; margin-left: 10px" href="https://www.nativescript.org/nativescript-sidekick">NativeScript Sidekick</a> for developing modern, cross-platform mobile apps with web technologies like JavaScript, Angular, or Vue.js, and <a id="kinvey" style="border: 1px solid #34495e; padding: 3px 8px; margin-left: 10px" href="https://www.kinvey.com/">Kinvey</a> for hosting critical business back-end in the cloud.</h2><br/>

# Progress AppBuilder Jenkins Plugin

## Overview
This plugin provides a simple way for Progress AppBuilder developers to execute cloud builds in a CI environment

### Dependencies
* [Apache Maven][maven] 3.0.4 or later

### Run in Docker
-------------------------
```shell
  $ docker run --name ab-jenkins -p 8080:8080 -p 50000:50000 -v /{ABSOLUTE_PATH}/jenkins_home:/var/jenkins_home -v /{ABSOLUTE_PATH}/telerik-appbuilder-plugin:/var/telerik-appbuilder-plugin telerikappbuilder/jenkins-appbuilder-plugin
```

### Run Plugin Locally
-------------------------
1. Build (with shell command '$mvn clean install') the project to produce `target/appbuilder-ci.hpi`
2. Remove any installation of the appbuilder-ci in `$user.home/.jenkins/plugins/`
3. Copy `target/appbuilder-ci.hpi` to `$user.home/.jenkins/plugins/`
4. Start/Restart Jenkins

[maven]: https://maven.apache.org/

### Publish to jenkins-ci.org
-------------------------
```shell
  $ docker exec -it {CONTAINER_ID} cd /var/telerik-appbuilder-plugin && mvn release:prepare release:perform -Dusername=... -Dpassword=...
```
