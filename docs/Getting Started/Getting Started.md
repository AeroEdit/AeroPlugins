# Getting Started
In this tutorial, you'll learn how to create a new plugin for AeroEdit!

## The Manifest
We've designed plugins to be *very* similar to Chrome and Firefox extensions. This is so developers that normally develop plugins for browsers are used to it. Start by creating an empty folder for your plugin. Inside it, create a file called `manifest.json`:
```json
{}
```

Great! Now we're ready to go. Next, add the required keys - AeroEdit requires certain keys. Without them, a plugin is considered corrupted.

```json
{
    "name": "Cool Plugin",
    "description": "This is a cool AeroEdit plugin!",
    "version": "1.0.0",
    "manifest_version": 2
}
```

## Localization
Because people make crazy errors all over the world, it's recommended to localize your plugins. Let's do just that. Localizing your plugin works in the exact same way localization works for Chrome extensions. Make these modifications to your `manifest.json` file.

```json
{
    "name": "__MSG_pluginName_",
    "description": "__MSG_pluginDesc_",
    "version": "1.0.0",
    "manifest_version": 2,
    "default_locale": "en-US"
}
```

Now, create a folder called `_locales`. Inside it, create 3 folders called `en-US`, `es-ES`, and `ja-JP`.Inside each of those folders, create a `messages.json` file. Your directory tree now should look like this:

```
Project Root
 | manifest.json
 | _locales
   | en-US
     | messages.json
   | es-ES
     | messages.json
   | ja-JP
     | messages.json
```

Now put the following content into the `messages.json` files:

`/_locales/en-US/messages.json`
```json
{
    "pluginName": {
        "description": "The name of the plugin.",
        "message": "Cool Plugin"
    },
    "pluginDesc": {
        "description": "The description of the plugin.",
        "message": "This is a cool AeroEdit plugin!"
    }
}
```

`/_locales/es-ES/messages.json`
```json
{
    "pluginName": {
        "description": "The name of the plugin.",
        "message": "Plugin Genial"
    },
    "pluginDesc": {
        "description": "The description of the plugin.",
        "message": "Este es plugin genial de AeroEdit!"
    }
}
```

`/_locales/ja-JP/messages.json`
```json
{
    "pluginName": {
        "description": "The name of the plugin.",
        "message": "かっこいいプラッギン"
    },
    "pluginDesc": {
        "description": "The description of the plugin.",
        "message": "これはかっこいいエアロエディットプラッギンですね。"
    }
}
```

Now your plugin should show its name and description properly in English, Spanish, and Japanese!
