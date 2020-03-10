## Scripts

A folder to collect different scripts for easier development, instead of leaving them all in the root folder. Nasty.

Run the scripts from root folder, though.

Something to keep in mind if you want to build plugins from scratch is this picture:

```tree
[0][~:myScrewdriverPlugin] > tree
.
├── classes
│   └── tech
│       └── mazunki
│           └── Screwdriver.class
├── lib
│   └── spigot-api-1.15.2-R0.1-SNAPSHOT.jar
├── manifest.txt
└── src
    └── tech
        └── mazunki
            └── Screwdriver.java
```

The folders inside of `/classes/` can be deleted. So after running `$(rm -r classes/*)`, you will have a clean repo such as this:

```
.
├── classes
├── lib
│   └── spigot-api-1.15.2-R0.1-SNAPSHOT.jar
├── manifest.txt
└── src
    └── tech
        └── mazunki
            └── Screwdriver.java
```

where `spigot-api-$VER-$REV.jar` is generated from BuildTools.jar (and copied into the lib folder), and `Screwdriver.java` is placed in the same path its package says it's located in. 

With this, you can run `classes/compileClass.sh`, and `classes/compileJar.sh` afterwards, building together the plugin with the corresponding Spigot-API. 

Run the plugin with `java -jar Screwdriver.jar` to test it, or copy it to your server.
