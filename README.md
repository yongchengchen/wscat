# wscat - WebSocket cat
## Abstract
I would like to use [wscat](https://github.com/websockets/wscat) on macOS, but this requires to install Node.js.
So I decide to make the same command without Node.js. And I am learning Golang. This is a chance to learn more Golang through making this command.

## Build

```shell
$ go build wscat.go
```

## Usage


```shell
$ ./wscat ws://echo.websocket.org
```

Or, 

```shell
$ ./wscat -c ws://echo.websocket.org
```

You can use -i option when a sending data to a WebSocket server reads from a file. Also you can use -o option when a receiving data from a WebSocket server saves to a file you want.
When you don't specify any options, sending data reads stdio and receiving data writes stdout.

You can use -e to check the last line of the result if match with the string, then will return command status code 0.

```shell
$ ./wscat -c ws://echo.websocket.org -i send.txt -o recv.txt -e COMMAND_SUCCESS
```

## License

MIT License
