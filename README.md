# Error message with cyclonedx-maven-plugin 2.7.3 and Maven 4.0.0-alpha-2

* The plugin shows errors 

* No error with Maven 3.8.6
```
❯ mvn -V -q clean cyclonedx:makeBom
Apache Maven 3.8.6 (84538c9988a25aec085021c365c560670ad80f63)
Maven home: /usr/local/Cellar/maven/3.8.6/libexec
Java version: 17.0.5, vendor: Eclipse Adoptium, runtime: /Library/Java/JavaVirtualMachines/temurin-17.jdk/Contents/Home
Default locale: de_DE, platform encoding: UTF-8
OS name: "mac os x", version: "13.0.1", arch: "x86_64", family: "mac"
```

* Error **message** with Maven 4.0.0-alpha-2 (the build is not broken but the logging is different).

```
❯ mvn4 -V -q clean cyclonedx:makeBom
Apache Maven 4.0.0-alpha-2 (c07700ffc97d3967a8de77d5a1065f5e6115c00e)
Maven home: /Users/XXX/lib/apache-maven-4.0.0-alpha-2
Java version: 17.0.5, vendor: Eclipse Adoptium, runtime: /Library/Java/JavaVirtualMachines/temurin-17.jdk/Contents/Home
Default locale: de_DE, platform encoding: UTF-8
OS name: "mac os x", version: "13.0.1", arch: "x86_64", family: "mac"
1907 [ERROR] An error occurred attempting to read POM
org.codehaus.plexus.util.xml.pull.XmlPullParserException: Unrecognised tag: 'goals' (position: START_TAG seen ...</version>\n                <goals>... @232:24) 
    at org.apache.maven.model.v4.MavenXpp3Reader.checkUnknownElement (MavenXpp3Reader.java:3645)
    at org.apache.maven.model.v4.MavenXpp3Reader.parsePlugin (MavenXpp3Reader.java:2669)
    at org.apache.maven.model.v4.MavenXpp3Reader.parseBuild (MavenXpp3Reader.java:932)
    at org.apache.maven.model.v4.MavenXpp3Reader.parseModel (MavenXpp3Reader.java:492)
    at org.apache.maven.model.v4.MavenXpp3Reader.read (MavenXpp3Reader.java:204)
    at org.apache.maven.model.io.xpp3.MavenXpp3Reader.read (MavenXpp3Reader.java:140)
    at org.apache.maven.model.io.xpp3.MavenXpp3Reader.read (MavenXpp3Reader.java:74)
    at org.apache.maven.model.io.xpp3.MavenXpp3Reader.read (MavenXpp3Reader.java:89)
    at org.cyclonedx.maven.BaseCycloneDxMojo.readPom (BaseCycloneDxMojo.java:759)
    at org.cyclonedx.maven.BaseCycloneDxMojo.extractPom (BaseCycloneDxMojo.java:718)
    at org.cyclonedx.maven.BaseCycloneDxMojo.convert (BaseCycloneDxMojo.java:479)
    at org.cyclonedx.maven.CycloneDxMojo.execute (CycloneDxMojo.java:70)
    at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo (DefaultBuildPluginManager.java:155)
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute2 (MojoExecutor.java:380)
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute (MojoExecutor.java:361)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:232)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:188)
    at org.apache.maven.lifecycle.internal.MojoExecutor.access$000 (MojoExecutor.java:78)
    at org.apache.maven.lifecycle.internal.MojoExecutor$1.run (MojoExecutor.java:179)
    at org.apache.maven.plugin.DefaultMojosExecutionStrategy.execute (DefaultMojosExecutionStrategy.java:42)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:174)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:112)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:80)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:64)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:141)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:341)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:248)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:158)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:1004)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:307)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:204)
    at jdk.internal.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at jdk.internal.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:77)
    at jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:568)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:282)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:225)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:406)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:347)
```
