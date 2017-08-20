## Getting Started


###Required Software

First you’ll need a Java IDE. We suggest [IntelliJ by Jetbrains](https://www.jetbrains.com/idea/download)but there are a bunch of alternatives, use whatever you’re comfortable with.

You’ll also need the latest version of the [Java Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
Be sure to get the one that says JDK

To add the JDK to IntelliJ, open it, go to File>Other Settings>Default Project Structure and below Project SDK hit new>JDK and navigate to the folder where you installed the JDK. Something like C:\Program Files\Java\jdk1.8.0_111


###Github Setup 


Create or log into your Github account, visit [the project's page](https://github.com/Mu0n/XWVassal) and click the fork button in the top right corner. 

Now that you have your own copy of the project, you need to clone it to your machine. If you're using IntelliJ you can follow [these directions](https://www.jetbrains.com/help/idea/using-git-integration.html). 

You'll want to add [Muon's repo](https://github.com/Mu0n/XWVassal) as an upstream repository so that it'll be easy to keep your version of the project up to date. 

Before you begin working, make a new branch and commit regularly. When your work is ready to be added to the main repo, merge any changes from the main repo, push your branch up to github and use the website to make a pull request for Mu0n's repo.  

### Building the vassal module

Once you've made some changes to the module, you'll want to build the module and add it to vassal so that you can test out any changes. 

If you're on Windows, an easy way to do is to use a bat file with the following lines of code. Do note that you'll need to change the file paths on lines 1 and 3. The resulting bat file will produce a vmod file in the /mic/build/distributions folder.
```
cd "C:\dev\vassal\XWVassal\mic\swxwmg.vmod-unpacked\images"
del Thumbs.db
cd "C:\dev\vassal\XWVassal\mic\"
call gradlew downloadXwingData
call gradlew buildVmod %1
cd "C:\"
```

Move the new module file to the folder with your other vassal modules and open the module in Vassal. You can avoid the image tiling process on subsequent builds by overwriting the swxwing.vmod file. 