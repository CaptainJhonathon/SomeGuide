# conflict when working with java project and android

If you are using java to code androind and other project.

Do not place android studio project and java project under the  
same directory while working with vscode extension of java.

The extension will use a simple jre to provide grammer check.

So it will mess up the environment.

If you want to clean up this mess, go to the android studio project  
directory and run:
```
./gradlew --stop
./gradlew clean
```
Then just seperate these two or simply open pure one project at a time.

Well the best way is to set envirnment variables correctly for 
vscode setting and use:
```
./gradlew compileDebugJavaWithJavac --no-daemon
```
(haven't been tested by myself)