
I like UDP and WebSocket connections,
but I am not very comfortable with WebTransport, REST APIs, or secure MQTT.

TBIO stands for Text Byte In/Out.

Add your Godot code here to listen for incoming text and bytes, and to send them out.
Also notify when text or bytes have been received.

Examples:
`~Paul|0|42>` sends 8 bytes as two 16-bit integer shorts to whatever or whoever "Paul" refers to.
`~PC1|t|Hello>` sends the text `Hello` as a shortcut to PC1.

You should not need to worry about the underlying network protocol when sending data. You only need to know whether you are sending text or a byte array.

The goal is to create a network layer so the user does not have to think about what is being sent or how it is transmitted.


```
extends Node

signal on_server_to_client_byte_package(package:BytePacked)

signal on_server_to_client_byte_package(package:String)


func on_client_to_server_byte_package(package:BytePacked):
    pass

func on_client_to_server_byte_package(package:String):
    pass
```