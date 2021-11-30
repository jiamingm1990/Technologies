# JSON

> Where can I find the JSON grammar?

Read state transition diagram in [the official site](https://www.json.org/json-en.html). Or read [the grammar in McKeeman Form](https://www.crockford.com/mckeeman.html).

> What are the three ways to process JSON?

1. Iteration: Iterating over Event (or, token) stream.
2. Data Binding: Binding Json data into Objects.
3. Tree Traversal: Building a tree structure (from Json) and tranversing it using suitable methods.

Above content is from [There are Three -- and Only Three -- Ways to Process Json!](http://www.cowtowncoder.com/blog/archives/2009/01/entry_131.html). There is only one Objective-C library [yajl-objc](https://github.com/gabriel/yajl-objc) that provides the iteration abstract interface.

> Where can I find all the popular JSON libraries?

See the bottom of [the JSON official site](https://www.json.org/json-en.html).

> How can I process JSON by reading and writing event streams?

Read [Json processing with Jackson: Method #1/3: Reading and Writing Event Streams](http://www.cowtowncoder.com/blog/archives/2009/01/entry_132.html) to know more details. It is implemented in [jackson-core](https://github.com/FasterXML/jackson-core).

> How can I process JSON using data binding?

Read [Json processing with Jackson: Method #2/3: Data Binding](http://www.cowtowncoder.com/blog/archives/2009/01/entry_137.html) to know more details. It is implemented in [jackson-databind](https://github.com/FasterXML/jackson-databind).

> How can I process JSON using tree traversal?

Read [Json processing with Jackson: Method #3/3: Tree Traversal](http://www.cowtowncoder.com/blog/archives/2009/01/entry_153.html) to know more details. It is implemented in [jackson-databind](https://github.com/FasterXML/jackson-databind). The [JsonNode definition](https://fasterxml.github.io/jackson-databind/javadoc/2.7/com/fasterxml/jackson/databind/JsonNode.html).
