Text in the file is Godot code that you want to be able to call and trigger on/off

You call the mod by its name.

For example, say_hello.godot_mod_one_time:
`⚙️record_telemetry:on`
`⚙️record_telemetry:off`

```gdscript
on_mod_script_requested_on()->void:
    pass

on_mod_script_requested_off()->void:
    pass

on_mod_script_requested(value:bool)->void:
    pass
```

