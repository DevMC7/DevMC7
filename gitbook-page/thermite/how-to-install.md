# How to Install

After you add the gradle dependency, you need to add the following to your mod's main class

```java
public class MyMod implements Mod /* no need to add ModInitializer here */ {

    private final Logger logger = LoggerFactory.getLogger(getModId());

    @Override
    public void onInitialize() {
        // your mod's logic
    }

    @Override
    public String getModId() {
       return "modid";
    }

    @Override
    public Logger getLogger() {
       return logger;
    }
}
```
