This proto file(s) have using Google predefined Common Data Type:
[https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/timestamp.html#class_google_1_1_protobuf_1_1_well_known_types_1_1_timestamp](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/timestamp.html#class_google_1_1_protobuf_1_1_well_known_types_1_1_timestamp)

To get Golang code geneerated:

1. Clone [protobuf source](https://github.com/google/protobuf) to an arbitrary location, like ~/include/prtobuf .

2. Invoke protoc like following:
protoc -I ~/include/protobuf/src/ -I ./proto --go_out=plugins=grpc:proto ./proto/coscup2017_grpc_proto/save_text/*.proto