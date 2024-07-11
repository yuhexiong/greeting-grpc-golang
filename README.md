# Greeting GRPC
Demonstrate the use of gRPC by generating Protocol Buffers files using commands, enabling bidirectional communication between client and server using pb for efficient interactions.  
Note that while this demonstration uses Go, Protocol Buffers support cross-language capabilities.  


## Overview

- Language: Go v1.21.4
- Library: Protocol Buffers v27.2

## Requirement

download Protocol Buffers from [GitHub](https://github.com/protocolbuffers/protobuf/releases/tag/v27.2)  

## Run

### Update Modules
```
go get -u && go mod tidy -v
```

### Generate pb.go file
```
protoc --go_out=. --go-grpc_out=. example.proto
```

### Install pb package local
```
go mod edit -replace greeting-grpc-golang=./..
go get greeting-grpc-golang/pb
```

### Run
- greeting-grpc-golang/server  
```
go run server.go
```
you will see: `2024/07/09 14:11:12 Starting gRPC server on 50051` 

- greeting-grpc-golang/client  
```
go run client.go
```
can get reponse from server: `2024/07/09 14:11:26 Response from server: Hello, Xiong`