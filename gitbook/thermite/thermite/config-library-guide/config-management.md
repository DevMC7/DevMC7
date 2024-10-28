# Config Management

To load your configuration file, you simple need to do

```java
ConfigFile#load();
```

To save it,

```java
ConfigFile#save();
```

You can get the config's name (not necessarily the file's name) using

```java
ConfigFile#getName();
```

You can enable/disable pretty print (enabled by default) using

```java
ConfigFile#setPrettyPrint(enabled)
```

You can create configs using ConfigFile.Builder

```java
ConfigFile configFile = new ConfigFile.Builder()
       .name("config name")
       .mod(YOUR_MOD_CLASS)
       .file(new File("my-mods-config.json"))
       .build();
```

Note: name and file don't need to be provided (defaults to mod.getModId())
