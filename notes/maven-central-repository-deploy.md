Deploy to Maven Central Repository
----------------------------------
registration of groupId, https://issues.sonatype.org/   
pom.xml 
```xml
<project>
    <parent>
        <groupId>org.sonatype.oss</groupId>
        <artifactId>oss-parent</artifactId>
        <version>9</version>
    </parent>
    <pluginManagement>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-gpg-plugin</artifactId>
                <version>1.6</version>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-release-plugin</artifactId>
                <version>2.5.3</version>
            </plugin>
        </plugins>
    </pluginManagement>
</project>
```
Configure GPG to sign Maven artifact 
------------------------------------
by a tool like gnupg2, generate a key pair and share pub-key to a keyserver.    
Keyserver synchronize between each other, so it takes some time, be patient!
```bash
sudo apt-get install gnupg2
gpg2 --version
gpg2 --gen-key 
gpg2 --list-keys
gpg2 --list-secret-keys
gpg2 --keyserver hkp://pool.sks-keyservers.net --send-keys A6BAB25C     #A6BAB25C is pubkeyId
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys A6BAB25C
gpg2 --edit-key A6BAB25C
```
config maven conf/setting.xml
-----------------------------
to protect your credential, do not set these config in project pom.
```xml
<servers>
    <server>
        <id>sonatype-nexus-snapshots</id>
        <username>user</username>
        <password>16P#62h6C8xiUkYp!eneW12ww53</password>
    </server>
    <server>
        <id>sonatype-nexus-staging</id>
        <username>user</username>
        <password>16P#62h6C8xiUkYp!eneW12ww53</password>
    </server>
</servers>
<profiles>
<profile>
    <id>sonatype</id>
    <properties>
        <gpg.useagent>false</gpg.useagent>
        <!-- gpg-plugin defaults to trying 'gpg' on the path, this changes that to 'gpg2' instead -->
        <gpg.executable>gpg2</gpg.executable>
        <gpg.passphrase>plainPassPhrase@gpg --gen-key</gpg.passphrase>
    </properties>
</profile>
</profiles>
```
Release
-------
`mvn release:clean release:prepare release:perform -Psonatype`

