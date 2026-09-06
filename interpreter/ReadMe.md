# 📙 Command and Interpreters

In GOMI, you have the default interpreter and the one that the community can add.   

Here, I focus on the default one included in the software.   

GOMI is composed of three main components:   

* `Command Line`, starting with `cmd:`, representing an action to be performed and requiring the full line context.   
* `Shortcut Line`, starting with `sc:`, representing an action to be performed based on the words stored in the line.   
* `boolean register`, a register of named true or false values that you can build, observe, and hook actions to.    

The rest revolves around it.

I switched to Godot because of its ability to be moddable on any platform.   
Consider that if you can code it in GDScript, you can add it to the tool.   

GDExtension is not an option in the default GOMI.   
However, you can create your own project using your GDExtensions or interact with the network through the `Gate In` option.    

`Gate In` provides UDP and WebSocket entry points to interact with GOMI from your own language.    

You can add your own `Gate In` in GDScript if, for example, you prefer MQTT or something else.   


Note: If you are a bit geeky and learned `GDScript`  
You can add your own code in it and just code your macro in GDScript.   
A `not code` UI will be added later with the native Graph of Godot.

( I want to add [Godot Block Coding Plugin](https://github.com/endlessm/godot-block-coding) in GOMI. 
But I need to check if it does not break too much. )

------------------








