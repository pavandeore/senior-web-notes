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

obj2 = {...obj1}
// only top level 


------------

7] Performance Navigation Timing
<pre>
[DNS]
DomainLookupStart -> DomainLookupEnd 

[TCP-TLS]
connectStart -> secureConnectionStart -> connectEnd

[HTTP Req]
requestStart 

[HTTP Res]
responseStart -> responseEnd

[DOM]
domLoading
domInteractive
domContentLoadedEventStart
domContentLoadedEventEnd
domComplete

[Load]
loadEventStart
loadEventEnd
</pre>

---------------

8] Cache Directive

no-cache - validates a cache response with origin server before using it, even if it is still refresh  ( it will always make request to server before using cache version [remeeber ETag verfication] ) 
must-revalidate - validates a state response with the origin server before using it.
no-store - doesn't cache any part (perfect for sensitve data maybe financial record)
private - prevent caching on shared caches (maybe you have cdn in between) it makes sure that caching happens only on user http client
stale-while-revalidate - serves state content while validating the cached response with the origin server 


-----------------

9] Garbage Collection

dynamic data always stored in heap 
as soon as we set things to null it removes it from callstack and thus the heap data is also removed 

-------------

10] Animation Cost

when we change 

width: Layout -> Paint -> Composite
opacity: only Composite
backgroung-image: Paint -> Composite
left: Layout -> Paint -> Composite
Transform: Layout -> Composite


---------------

11] Event Propagation

3 steps - Capturing, Target, Bubling

by default click listenres runs during bubling phase
you can change this by passing 2nd argument true, false

capturing - top to bottom
target - actual target
bubling - bottom to top


------------------------

12]  Css Specificity

inline
ID
classes, attribute
element

-----------------------

13]  Weakmap



---------------------------

14] Web vitals

<pre>
TTFB - time it takes for the server to respond to a request and start sending data back to client
FID - time it takes for webpage to users first interaction
TTI - the time it takes to be fully loaded and responsive to user input
TBT - the time that the main thread is blocked from responding to user input
CLS - the stability of webpages' layout or unexpected layout shifts that occur on webpage as it loads
INP - the average time it takes for webapge to update its visuals afteer a users interacts it
</pre>


----------------------------

15] Content Security Policy header (CSP)

with csp header we cab control where our website can load resources from 



------------------------

16] 



---------------------





