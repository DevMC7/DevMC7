# Config Values

In thermite config, you need to specify a default value for every config option

```java
ConfigFile#setDefault("category name", "key", new PrimitiveWrapper("value"));
```

The value paramater must be a JsonSerializable. Primitives (strings, booleans and numbers), lists and colors are already implemented, but you can add your own custom types too!

To get a JsonSerializable from the config file:

```java
ConfigFile#get("category", "key");
```

There are also type-safe getters for primitive values

```java
ConfigFile#getString("category", "key");
ConfigFile#getBoolean("category", "key");
ConfigFile#getInteger("category", "key");
ConfigFile#getLong("category", "key");
ConfigFile#getFloat("category", "key");
ConfigFile#getDouble("category", "key");
```

To reset a value to its default

```java
ConfigFile#resetToDefault("category", "key");
```

To remove a value from the config

```java
ConfigFile#remove("category", "key");
```

If you provide no category name, the mod's default one will be used (defaults to the mod's id)
