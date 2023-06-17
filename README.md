# senior-web-notes

1] script execution 

noraml - fetched and executed right aways - blocking
async - fetched parallel with rendering and blocked execution
defer - fetched parallel with rendering but executed on load

--------------

2] Rendering pipeline

prase html -> DOM Tree -> CSSOM Tree -> conbination of both Render tree -> layout phase (position, size, gemetry) ->  Paint (actual writing) ->  Composite (final, one final images thats gets rendered) -> display


---------------

3] How DNS

browser sends request to DNS Resolver -> queries Root Name Server -> responds with Top level Domain name server -> TCP bullshit -> page rendering bullshit ->view!


------------------

4] Call Stack and Event Loop

setTimeout(()=> console.log(1))
Promise.resolve().then(()=> console.log(2))
Promise.resolve().then(()=> setTimeout(() => console.log()))
new Promise(()=> console.log(4))
setTimeout(()=> console.log(5))
// 42153

-----------------------------

5] Resource Hints

Network
(there is also limit that maximum number of simultaneous connection browser can have)

Normal flow
DNS -> TCP -> TLS -> REQ ->  RES

DNS-prefetch
performs domain name resolution in the background

DNS ------------  TCP, TLS, REQ, RES


Preconnect
performs DNS resolution and TCP/TLS handshake

DNS, TCP, TLS ----------------- REQ, RES


Prefetch
Downloads certain resource ahead of time, even if they aren't immediately needed, and store it in cache

(can be skipped by browser if they feel there is no bandwidth)


Preload
downloads resources that are likely to be needed in the future


--------------------


6] Object reference and Destructuring









