# Basic Config

1.  Add the ModMenu entrypoint to your fabric.mod.json file\


    ```json
    "entrypoints": {
      "modmenu": [
        "com.example.modid.ModMenuIntegration"
      ]
    }
    ```
2.  Override the getModConfigScreenFactory() method\


    ```java
    import com.terraformersmc.modmenu.api.ConfigScreenFactory;
    import com.terraformersmc.modmenu.api.ModMenuApi;

    public class ModMenuIntegration implements ModMenuApi {

        @Override
        public ConfigScreenFactory<?> getModConfigScreenFactory() {
           return null;
        }
    }
    ```
3.  Create the config file:\


    ```java
    ConfigFile configFile = new ConfigFile(YOUR_MOD);
    ```
4.  Return a ConfigScreen with your config file\


    ```java
    @Override
    public ConfigScreenFactory<?> getModConfigScreenFactory() {
        ConfigFile configFile = new ConfigFile(YOUR_MOD); // YOU_MOD is the mod's main class
        configFile.load(); // load the existing config before creating a screen
        ClothConfigScreen configScreen = new ClothConfigScreen(configFile);
        return configScreen::createConfigScreen;
    }
    ```

\
You can now add values to your config!
