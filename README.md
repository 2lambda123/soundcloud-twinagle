# Twinagle = Twirp + Finagle

Code generation and runtime support for writing Twirp services with Finagle.

[![Build Status](https://travis-ci.org/soundcloud/twinagle.svg?branch=master)](https://travis-ci.org/soundcloud/twinagle)

# Notes

* IntelliJ [doesn't run plugins][intellij] during project build. Before importing,
 `sbt compile` may be necessary. 

# TODO

## General

* [ ] docs (expand API docs + how-to-use)
* should we match [Scrooge](https://twitter.github.io/scrooge/Finagle.html#creating-a-server)'s conventions?

## Codegen
* [ ] expose protobuf comments as scaladocs on service traits
  - [x] on the trait
  - [ ] method scaladocs
* [x] build SBT plugin based on https://github.com/fiadliel/fs2-grpc
  - [x] refactor codegen based on [`GrpcServicePrinter`][GrpcServicePrinter]. 
* [x] make sure that multiple service definitions in proto file do something sensible
* [ ] how to handle streaming RPCs? log and error and ignore? abort?
* [x] add an extension point that clients can use to instrument generated clients / servers

## Runtime

* [x] use sbt-buildinfo plugin to provide correct twinagle-runtime dependency
* [x] refactor/simplify exceptions ~~(no separate `ErrorCode`)~~

[intellij]: https://intellij-support.jetbrains.com/hc/en-us/community/posts/206825945-sbt-tasks-as-part-of-the-normal-build
[GrpcServicePrinter]: https://github.com/scalapb/ScalaPB/blob/master/compiler-plugin/src/main/scala/scalapb/compiler/GrpcServicePrinter.scala
