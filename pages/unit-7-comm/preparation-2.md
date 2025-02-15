# HTTP - Hypertext Transfer Protocol

This is only a very brief description of HTTP to relate it to the
previously described communication topologies and message patterns. You
have probably already heard about HTTP in other courses. Here, we look
at it from an application's perspective. If you are interested in more
technical details, read for instance on [Wikipedia](<https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol>).

HTTP is a request-response message pattern, and uses a client-server
topology. The server usually provides resources to the client, which can
be a web browser. In HTTP, the initiatives for communication are
uni-directional. This means, the client takes initiative and contacts
the server, not the other way round. For the original purpose of HTTP
(requesting documents from a server) this is suitable characteristic,
since it simplifies the construction of efficient servers and how
documents can be cached.

## Getting Bi-Directional  {#getting-bi-directional .unnumbered}

One websites should get more interactive, this is a limitation we are
all aware of. We are used to refresh a website to see if there is new
information available. And when booking a flight or paying via credit
card, you see clumsy messages like "Don't reload this page." This is so
inelegant because technology was never intended to this stuff with a
browser! With this example you also see which fundamental effect
communication topologies and message patterns have. Websites today are
incredibly more advanced than ten years ago. Still, some of these old
limitations are hard to get rid off.

There are some mechanisms that work around these limitations of HTTP. If
you are interested in the details, have a look at the [Wikipedia article
on Comet](https://en.wikipedia.org/wiki/Comet_(programming)). To keep it brief; it's fascinating, but ugly. In essence,
the workaround is that the client still initiates all communication, but
client and server keep an HTTP connection alive, so that the server can
send updates once there are some. When Google offered chat on their
Gmail website, for instance, they used this mechanism to [push new chat
messages immediately from the server to the browser](https://stackoverflow.com/questions/732705/how-is-gmail-chat-able-to-make-ajax-requests-without-client-interaction). Google Docs
uses a [similar mechanism](https://stackoverflow.com/questions/35070217/what-technology-does-google-drive-use-to-get-real-time-updates).

To address the needs of server to notify the client when new information
is available, the [WebSocket protocol](https://en.wikipedia.org/wiki/WebSocket) was built. Like HTTP, it also
builds upon TCP, but offers full-duplex. With WebSockets, you can for
instance build relatively simple web-applications running in the browser
that support fine-grained, bi-directional interactions like chat or
games.

---
type: nav
prev: ["Communication Protocols", "preparation-1.html"]
next: ["MQTT", "preparation-3.html"]
---
