# Gate Out UDP

Gate Out means that you want to send something outside of the application.   
UDP means that you want to send something without waiting for the receiver to confirm the reception.   
UDP does not manage bytes vs. text. Everything is just an array of `101011110110110`.   

You need to provide the address of the target device and the port.   

If you are not sure which port to use, just broadcast on all the ports you remember xD.   
Dirty, but it works.  

If you are a beginner, you will use only one target.   
But if you are multiboxing or doing an advanced setup, you may want to name your targets.   

# One Target

Here is an example:   
```.gate_out_udp
FILE>>>|.gate_out_udp
byte♦️192.168.178.49♦️3615 7073
text♦️192.168.178.49♦️3614
```

* `FILE>>>|.gate_out_udp`: The following lines are considered a `.gate_out_udp` file.   
* `byte♦️192.168.178.49♦️3615 7073`: If the app user wants to send bytes, they can append this target.  
* `text♦️192.168.178.49♦️3614`: If they want to send text, they can append this target and parse it into UTF-8 bytes.  
* `byte`, `text`: The type of information being sent.  
* `192.168.178.49`: The IPv4 address of the device to broadcast the message to.   
* `3615 7073`: The two ports to send the message to. This creates two targets in the app.   

An example of use:
```
sc:1032 1000> 2032    # Ask the target to press space for 1 second   
sc:1|1300 1000> 1|2300    # Ask the target to press A on its gamepad for 1 second   
```

In GOMI, by default, any integer in a Shortcut Command `sc:` is a signed 32-bit little-endian integer to be sent to the default targets.   
Any integer followed by `>` (`int>`) in a Shortcut Command means to wait for a short time locally before continuing.  

## Several Targets

```.gate_out_udp
FILE>>>|.gate_out_udp
healer♦️byte♦️192.168.178.50♦️7073
tank♦️byte♦️192.168.178.51♦️7073
dps♦️byte♦️192.168.178.52♦️7073
main♦️byte♦️127.0.0.1♦️3615
main♦️text♦️127.0.0.1♦️3614
```

* `FILE>>>|.gate_out_udp`: The following lines are considered a `.gate_out_udp` file.
* `healer♦️byte♦️192.168.178.50♦️7073`: Send bytes to the healer at this address.
* `healer`: The name of the device to be called in your code.
* `byte`: Byte requests sent to `healer` will be redirected to this target.
* `192.168.178.50`: The IPv4 address of the target.
* `7073`: The port of the target.

An example of use:

```
sc: 0> ~healer|1032>    # Ask the healer to start jumping
sc: 1000> ~healer|2031> # Then ask it to stop jumping after 1 second
sc: 200> ~dps|1|1300>   # The DPS presses A on its Xbox controller (index 1)
sc: 400> ~dps|1|2300>   # The DPS releases the A button after 200 ms
```

----------

# Experiment with it

## Listen to text

``` python
import socket
PORT = 3614
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.bind(("0.0.0.0", PORT))
print(f"Listening for text on UDP port {PORT}...")
while True:
    data, addr = sock.recvfrom(65535)
    text = data.decode("utf-8", errors="replace")
    print(f"[{addr[0]}:{addr[1]}] {text}")
```

## Listen to bytes

``` python
import socket
PORT = 3615
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.bind(("0.0.0.0", PORT))
print(f"Listening for bytes on UDP port {PORT}...")
while True:
    data, addr = sock.recvfrom(65535)
    print(f"[{addr[0]}:{addr[1]}] {data.hex(' ')}")
```


## Listen to bytes as II

``` python
import socket
import struct
PORT = 3615
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.bind(("0.0.0.0", PORT))
print(f"Listening for bytes on UDP port {PORT}...")
while True:
    data, addr = sock.recvfrom(65535)
    print(f"[{addr[0]}:{addr[1]}] {data.hex(' ')}")
    if len(data) == 4:
        # 4 bytes -> signed 32-bit integer, little endian
        value = struct.unpack("<i", data)[0]
        print(f"  value = {value}")
    elif len(data) == 8:
        # Two little-endian signed 32-bit integers
        value1, value2 = struct.unpack("<ii", data)
        print(f"  Int32[0]: {value1}")
        print(f"  Int32[1]: {value2}")
```


## Listen to bytes with a bit of info

``` python
import socket
PORT = 3615
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.bind(("0.0.0.0", PORT))
print(f"Listening for bytes on UDP port {PORT}...")
while True:
    data, addr = sock.recvfrom(65535)
    print(f"\n[{addr[0]}:{addr[1]}]")
    print(f"Received {len(data)} bytes")

    # Raw bytes
    print(f"HEX:         {data.hex(' ')}")

    # Big endian
    big_endian = int.from_bytes(data, byteorder="big")
    print(f"BIG ENDIAN:  0x{big_endian:X}")
    print(f"             {big_endian}")

    # Little endian
    little_endian = int.from_bytes(data, byteorder="little")
    print(f"LITTLE END:  0x{little_endian:X}")
    print(f"             {little_endian}")

    # Binary, preserving exactly 8 bits per byte
    binary = " ".join(f"{byte:08b}" for byte in data)
    print(f"BINARY:      {binary}")
```

