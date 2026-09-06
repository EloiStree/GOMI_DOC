A gate is a specific entry in GOMI that allows other software and developers to inject input into the application.
You can already in those games send simple text command lines.
But if you want to trigger actions very quickly in the app, you can use this.

Unlinked it to S2W.

Here you decide on a blank canvas to say: "Hey, if I call you with a
- `453`, do those actions.
- `42`, do those.
- `782`, do those actions."

It allows you to prepare some ready-to-be-executed commands and call them with a 4-byte integer as an entry.
You can also, in an IID philosophy, add an II trigger (index/value) if you want to use GOMI as an input hub for a multiplayer RSA game.

Use `.integer_to_command` if you want to trigger an action for the interpreter of the command line.

Use the Shortcut interpreter if you want to trigger a shortcut:
`sc: 1000 1000> 2000 📋>1`


See UDP In Out of this implementation of the code behind the index:
https://github.com/EloiStree/2025_10_27_gdp_udp_in_out_gate

And in the future a version of TBIO Moddable will be added.
