
```
FILE>>>|.gate_in_game_telemetry
## Host a websocket server that can receive game telemetry 
websocket♦️server♦️0.0.0.0♦️7072

## Host a websocket server that only listen to game telemetry from the same device
# websocket♦️server♦️127.0.0.1♦️7072

## Listen to incoming text byte from a game telemetry given.
# udp♦️text♦️0.0.0.0♦️7073
# udp♦️byte♦️0.0.0.0♦️7072

## Connect to a telemetry server that emit game information to clients
# websocket♦️client♦️192.168.1.3♦️7074

```
