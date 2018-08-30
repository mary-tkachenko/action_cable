#### Life Before Action Cable and WebSockets ####
<img src="https://softcover.s3.amazonaws.com/636/learn_enough_action_cable/images/figures/walkie_talkie.png"></a>
<p> With HTTP long-polling, the client continually polls the server requesting for new information. The server hold the request open until any new data is available, and responds with the new information once available. In essence, the client is constantly polling the server to see if the database has changed state. As soon as the client receives that new information, it can immediately send another request and the operation is continually repeated.</p>
<p>This can get very taxing as the loop continues and the backend database grows. With more users pinging the server, this may take even longer. It is very expensive in terms of CPU, bandwidth consumption and storage. Every time a user makes an HTTP request, a bunch of headers and cookie data are transferred to the server. This can add up to a reasonably large amount of data that needs to be transferred, which in turn increases latency. So what’s the fix?

In comes WebSockets. Websockets allow a long-held single TCP (transmission control protocol) socket connection to be established between the client and server, allowing for for bi-directional, full duplex, messages to be instantly distributed. This is done with minimal overhead resulting in a low latency connection. </p>
 
<img src="https://cdn-images-1.medium.com/max/2000/1*v2XywM5pSK_f5VZyWDMPoQ.gif"></a>
### Introduction to Action Cable and WebSockets  ###
<p> Action Cable seamlessly integrates WebSockets with the rest of the Rails application. It allows for real-time features to be written in Ruby in the same style and form as the rest of the Rails application, while still being performant and scalable. It's a full-stack offering that provides both a client-side JavaScript framework and a server-side Ruby framework. You have access to your full domain model written with Active Record or your ORM of choice.</p>

<p>WebSockets are a protocol built on top of TCP. They hold the connection to the server open so that the server can send information to the client, even in the absence of a request from the client. WebSockets allow for bi-directional, "full-duplex" communication between the client and the server by creating a persistent connection between the two.</p>

### Key Advantages Of WebSockets Over HTTP Long-Polling ###

* Continuous connection between client and server: data can be sent to the client at any time, even without the client requesting it.
* Full duplex communication: communication can be sent either way at any time during the connection.
* Very low latency: there is limited HTTP overhead (like headers, cookies, etc.) making the speed at which data transfers happen much faster.

<img src="https://bamboolab.eu/uploads/picture/chat.gif">

## Helpful Links ##
* <a href="https://guides.rubyonrails.org/action_cable_overview.html#connection-setup"> Rails Guide Action Cable Overview</a>
* <a href="https://www.youtube.com/watch?v=kJbuZecN1c8"> Rails WebSocket Chat Real Time Tutorial </a>
* <a href="https://medium.com/front-end-hacking/what-are-websockets-7bf0e2e1af2"> What are WebSockets? </a>
* <a href="https://www.imaginarycloud.com/blog/websockets-and-action-cable-in-rails-5/"> WebSockets And Action Cable In Rails 5 </a>
* <a href="https://www.imaginarycloud.com/blog/websockets-and-action-cable-in-rails-5/"> Github Repo: Rails WebSocket Example (just need to run '$ bundle update' to make it work) </a>
* <a href="https://www.learnenough.com/action-cable-tutorial"> An Introduction to Real-Time Apps With Rails 5 </a>

