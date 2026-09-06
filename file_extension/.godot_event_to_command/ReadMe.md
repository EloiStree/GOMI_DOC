This file allows commands to be added and triggered by Godot events.
There may be other events in the future, but the four main ones are `at_ready`, `at_focus_enter`, `at_focus_exit`, and `at_exit`.

```text
FILE>>>|.godot_event_to_command
at_ready ♦️ cmd:log at_ready
at_focus_enter ♦️ cmd:log at_focus_enter
at_focus_exit ♦️ cmd:log at_focus_exit
at_exit ♦️ cmd:log at_exit
```

* `at_ready` The command will be loaded into GOMI at Godot's `_ready()`, that is, when the scene is loaded and imported into the scene.
* `at_focus_enter` Triggers the commands when the user returns to GOMI from another application.
* `at_focus_exit` Triggers the commands when the user leaves GOMI to switch to another application.
* `at_exit` The commands are triggered when scenes are reloaded or when the application exits.

 
Si cela est plus parlant, ou si vous devez lancer plusieurs commandes en même temps, vous pouvez utiliser ces formats de fichiers :   
- [.godot_event_to_command_at_ready](.godot_event_to_command_at_ready.md)   
- [.godot_event_to_command_at_focus_enter](.godot_event_to_command_at_focus_enter.md)   
- [.godot_event_to_command_at_focus_exit](.godot_event_to_command_at_focus_exit.md)   
- [.godot_event_to_command_at_exit](.godot_event_to_command_at_exit.md)   
   
