* `at_exit` The commands are triggered when scenes are reloaded or when the application exits.
  
```
FILE>>>|.godot_event_to_command_at_exit
cmd:log AT_EXIT EVENT

```


Utilizing:  
``` gdscript
func _exit_tree():
    print("Your command are triggers")
```
