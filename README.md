# Unstubbing SharedPreferences #

The Android libraries aren't available from the JUnit 4 test runner in
Eclipse.  This library exists to restore a stub version of
`SharedPreferences`.

Please forgive me.

## GitHub-hosted Maven repository ##

The command `mvn deploy` uploads the built jars to the `mvn-repo`
branch of `github.com/mozilla-services/android-sync`.  You need to
have administrator access to that git repository, and something like
the following in your `$M2_REPO/settings.xml` to enable uploading:

```
<settings>
  ...
  <servers>
    <server>
      <id>github</id>
      <username>YOUR-GITHUB-USERNAME</username>
      <password>YOUR-GITHUB-PASSWORD</password>
    </server>
  </servers>
  ...
</settings>
```

To refer to this Maven repository, you should use something like the
following in your project `pom.xml`:

```
<project>
  ...
  <repositories>
    <repository>
      <id>android-sync-mvn-repo</id>
        <url>https://raw.github.com/mozilla-services/android-sync/mvn-repo/</url>
        <snapshots>
          <enabled>true</enabled>
          <updatePolicy>always</updatePolicy>
        </snapshots>
        <releases>
          <enabled>true</enabled>
          <updatePolicy>always</updatePolicy>
        </releases>
    </repository>
  </repositories>
  ...
</project>
```
