This proto file(s) have using Google predefined Common Data Type:
[https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/timestamp.html#class_google_1_1_protobuf_1_1_well_known_types_1_1_timestamp](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/timestamp.html#class_google_1_1_protobuf_1_1_well_known_types_1_1_timestamp)

## Generate Golang code:

1. Clone [protobuf source](https://github.com/google/protobuf) to an arbitrary location, like ~/include/prtobuf .

2. Invoke protoc cli tool:  
```
protoc -I ~/include/protobuf/src/ -I ./proto --go_out=plugins=grpc:. ./proto/coscup2017_grpc_proto/save_text/*.proto
```

## Generate C# code:

1. Clone [protobuf source](https://github.com/google/protobuf) to an arbitrary location, like ~/include/prtobuf .

2. Install Grpc.Tools nuget package to get protoc cli tool.  
[https://preview.nuget.org/packages/Grpc.Tools/](https://preview.nuget.org/packages/Grpc.Tools/)

3. Set tool path environment variable on command line: 
```
export ToolPath=~/.nuget/packages/grpc.tools/1.4.1/tools/linux_x64
```

4. Invoke protoc cli tool,  
first generate Protocol Buffer part C# code:  
```
$ToolPath/protoc -I ~/include/protobuf/src/ -I ./proto --csharp_out proto ./proto/coscup2017_grpc_proto/save_text/*.proto  
```
then generate gRPC part C# code:  
```
$ToolPath/protoc -I ~/include/protobuf/src/ -I ./proto --grpc_out proto --plugin=protoc-gen-grpc=$ToolPath/grpc_csharp_plugin ./proto/coscup2017_grpc_proto/save_text/*.proto
```