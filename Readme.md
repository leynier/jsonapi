# jsonapi

> A minimalistic JSON API framework in Python with support for **graphql**-style queries.

**jsonapi** is heavily inspired by [graphql](https://graphql.org), but aimed at a much simpler use case. The idea is to have a minimal framework for easily building JSON based APIs, that doesn't require any particular frontend technology. The design is inspired in **graphql**'s idea of a single fully customizable endpoint, but instead of defining a specific query language, **jsonapi** is entirely based on JSON both for the query and the response, requires much less boilerplate code, only works in Python, and of course, is much less battle-tested. If you find **graphql** amazing but would like to try a decaffeinated version that you can setup in 10 lines, then give **jsonapi** a shoot.

## Instalation

**jsonapi** is a single Python file with no dependencies that you can just clone and distribute with your project's source code:

    git clone https://github.com/apiad/jsonapi.git

## Hello world

To illustrate the usage is best to start with an example. The main class in **jsonapi** is (wait for it...) `JsonApi`, which defines all the available commands in the API as public methods:

```python
>>> from jsonapi import JsonApi

>>> class HelloWorld(JsonApi):
...     def hello(self):
...         return "world!"
...     def the_answer(self):
...         return 42

```

Afterwards, create an instance of this API and call it's `query` method, passing along either a JSON-enconded string, or a pure Python dictionary:

```python
>>> api = HelloWorld()

>>> api({"hello": None})
{'hello': 'world!'}

>>> api({"the_answer": None})
{'the_answer': 42}
```

## Moving on

There is much more that can be done with **jsonapi**, read the [documentation](/docs/index.md) to learn more.

## Contributing

Contributions are highly appreciated. Just fork and submit a pull request. All contributors will be granted credit on the following list:

* Alejandro Piad ([@apiad](https://github.com/apiad))
