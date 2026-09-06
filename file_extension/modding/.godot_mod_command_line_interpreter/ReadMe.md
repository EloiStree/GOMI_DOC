Add an interpreter to the app.
If a command line is not understood by the program,
it asks the modding interpreter whether they understand it and want to handle the code to deal with it.

The application works with two types of commands.
Command Line: A given text is split into lines, and the lines are parsed into code.

Shortcut Word: A given line is split into words, and the words are parsed into code.

This interpreter you are going to code only manages command lines.

```gdscript
extends Node

func is_able_to_interpret_given_command_line(line: String) -> bool:
    ## Return true if the line matches the regex you expect.
    return false

func interpret_given_command_line(line: String) -> void:
    ## You accepted a line, so now what code do you want to execute?
```

By default, the interpreter is in
`claim mode`.

If you want to do code regardless of what the other interpreters look at,
use
`.godot_mod_command_line_any`.

This is exactly the same, but if you find the regex you like, you don't care about the others and execute after the official and claim ones.