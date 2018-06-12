# proto file

## Usage

file {project}.proto

```protobuf
syntax = "proto3";

import "base.proto"

package {project}

service {project} {
    rpc RpcApi(ApiReq) returns (ApiRes) {}
}

message ApiReq {
    uint64 id = 1;
}
```

## CRUD Api

```protobuf
service PetManagement {
    rpc CreatePet(CreatePetReq) returns (Pet) {}
    rpc ListPets(base.Empty) returns (Pets) {}
    rpc GetPet(base.IdReq) returns (Pet) {}
    rpc UpdatePet(UpdatePetReq) returns (Pet) {}
    rpc DeletePet(base.IdReq) returns (base.DefaultRes) {}
}

enum Gender {
    MALE = 0;
    FAMALE = 1;
}

message Pet {
    uint64 id = 1;
    string variety = 2;
    Gender gender = 3;
    string birthday = 4;
    string birthplace = 5;
    string nickname = 6;
    repeated string avatar_urls = 7;
}

message Pets {
    repeated Pet objects = 1;
}

message CreatePetReq {
    string varity = 1;
    Gender gender = 2;
}

message UpdatePetReq {
    uint64 id = 1;
    string nickname = 2;
}
```