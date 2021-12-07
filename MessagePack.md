# MessagePack

> Does the MessagePack Java library support iterating over event stream?

Yes. [MessageUnpacker](https://www.javadoc.io/static/org.msgpack/msgpack-core/0.9.0/org/msgpack/core/MessageUnpacker.html) provides interface to do the iteration for reading and [MessagePacker](https://www.javadoc.io/static/org.msgpack/msgpack-core/0.9.0/org/msgpack/core/MessagePacker.html) for writing.

> Does the MessagePack Objective-C library support iterating over event stream?

No. [MPMessagePackReader](https://github.com/gabriel/MPMessagePack/blob/master/MPMessagePack/include/MPMessagePackReader.h) only provide interface to read from `NSData` and [MPMessagePackWriter](https://github.com/gabriel/MPMessagePack/blob/master/MPMessagePack/include/MPMessagePackWriter.h) for writing to `NSData`.
