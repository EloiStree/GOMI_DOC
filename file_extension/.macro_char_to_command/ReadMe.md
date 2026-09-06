
Save idea that `.char_to_commands`

Ready to trigger an action from a third-party application outside of the app.

4/8 bytes are used in the IID format.
But when you do an IoT project with Arduino, you usually link an action to one or at most two bytes.

Like:

`A` : Turn motor to 100%
`a` : Turn motor to 0%

To stay readable, you can use bytes linked to the Base58 format:
AB..Zab...z0..9

I am using integers in my software because outside of Arduino, they are much easier to work with.
But the idea stays the same.

You can link one or two bytes to an index of actions.
Very fast to trigger.

See Electronic Bluetooth as a reference for what I am talking about here.
https://bluetooth-electronics.en.softonic.com/android


See UDP In Out of this implementation of the code behind the index:
https://github.com/EloiStree/2025_10_27_gdp_udp_in_out_gate

And in the future a version of TBIO Moddable will be added.


