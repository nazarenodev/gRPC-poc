# gRPC Service with Go, SQLite, and Evans Client

This repository contains a gRPC service built with Go that uses SQLite as the database. Evans, a gRPC client tool, is used to interact with the service.

## Features

- **gRPC Service**: A high-performance, language-agnostic RPC framework for building distributed systems.
- **SQLite Database**: A lightweight, file-based SQL database for data storage.
- **Go Language**: A modern, efficient language for backend development.
- **Evans Client**: A CLI tool to test and interact with the gRPC service.

---

## Requirements

Before running the project, ensure you have the following installed:

1. **Go**: [Download and install Go](https://golang.org/doc/install).
2. **SQLite**: Comes pre-installed on most systems, or download from [sqlite.org](https://sqlite.org/).
3. **Evans**: Install using Homebrew (macOS/Linux) or download from [Evans GitHub](https://github.com/ktr0731/evans).

---

## Getting Started
#### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```
#### 2. Install Dependencies
```bash
go mod tidy
```
#### 3. Generate gRPC Code
Ensure you have the protoc compiler and the Go gRPC plugin installed:
```bash
# Install Protocol Buffers compiler
brew install protobuf

# Install Go gRPC plugin
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```
Generate the Go code fro your .proto files:
```bash
protoc --go_out=. --go-grpc_out=. proto/course_category.proto
```
#### 4. Run the Server
Start the gRPC server:
```base
go run cmd/grpcServer/main.go
```
#### 5. Interact with the Service using Evans
Start Evans in interactive mode:
```bash
evans -r repl
```
From the Evans CLI:
 - Select your proto file: proto/course_category.proto
 - Call gRPC methods and view responses.

 ---
### Configuration
- Database: Configure the database in db/ directory. Modify server/main.go to use your desired SQLite database file.
- gRPC Port: Default port is 50051. Change it in server/main.go if needed.

---
### Testing
Run tests using Go's built-in testing framework
```bash
go test ./...
```

---

### License
This project is licensed under the MIT License. See the LICENSE file for details.

---
### Contributing
Contributions are welcome! Please fork this repository and submit a pull request for any improvements or features. Let me know if you need specific customizations or additional sections!