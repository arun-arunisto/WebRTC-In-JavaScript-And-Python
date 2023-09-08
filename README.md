# WebRTC-In-JavaScript-And-Python
## Part 1 - Caller-Callee-Js-Tutorial
WebRTC is an open-source project providing peer=to-peer, real-time communication capabilities to web browsers, mobile devices, and any other device that can run code using the available API's for JavaScript, Python, .NET, Golang and more.
<br>
WebRTC is mainly used to build a chat or video conferencing application, or you want to build distributed systems that communicate efficiently without putting a huge strain on a central server
<br>
How the WebRTC works it's a peer-to-peer communication available platform, but not directly NATS, private networks and all that good stuff that makes IPv4 still usable. To use this 3 main types of servers in WebRTC architecture
<br>
1. STUN Server: in order for two peers to exchange packets directly, first, they have to find out how they can be contacted directly. This information is gathered though the use of a STUN Server.
2. Signaling Server: It allows two peers to exchange that information about how they can connect directly, there is no specification to implement, It requires coding, and it can use Firebase, or it can be a Django App, it can run WebSockets or just HTTP.
3. TURN Server: if two peers can't exchange packets directly, the packets will have to be relayed through a TURN server, this requires some configuration, it will be used throughout the whole communication session and it will require bandwidth.
<br>
In this tutorial we will act as the signaling server by just copy-pasting information that needs to be exchanged between the two peers in order to connect them,
<br>
and in this tutorial we are using just two branches of code, one is "caller" function and other one is "callee" function.
### WebRTC API
we are not explaining it briefly we are just going through some instance only
<br>
Every peer has an instance of <code>RTCPeerConnection</code> every instance of a <code>RTCPeerConnection</code> has a <code>localDescription</code> and a <code>remoteDescription</code> of type <code>RTCSessionDescriptionInit</code> An instance of the latter class can be of type <code>offer</code> or <code>answer</code> depending on who created it, the caller or the callee.It also contains information such as <code>RTCIceCandidates</code> and the channels (such as text, media).
<img src="https://miro.medium.com/v2/resize:fit:640/format:webp/1*3iRtWbDcq5B4Qosg1F5AYA.png">
<br>
A <code>localDescription</code> contains info about what type of data the current peer can exchange (channels such as text, media), and how it can be reached (ICECandidates)
<br>
A <code>remoteDescription</code> contains info about what type of data the other peer can be exchange and how it can be reached.
<br>
A <code>localDescription</code> can be type <code>offer</code> if the current peer is the caller, and it can be of type <code>answer</code> if the current peer is the callee.
<br>
A <code>remoteDescription</code> can be of type <code>offer</code> if the current peer is callee, and it can be of type <code>answer</code> if the current peer is caller.
<br>
<img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*e-tVh6-twN41S67gsRsHuw.png">
<img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*IHcfCd7_zVrZ-nYJ7b5e_Q.png">
<br>
