Download Link: https://assignmentchef.com/product/solved-eecs3214-assignment1-word-of-wisdom-wow
<br>
In this project, we will consider a simple ‘Word of Wisdom’ (WoW) client-server application framework, as illustrated in the below figure. In the given framework, the WoW server is a program that contains a repository of some popular ‘words of wisdom’ messages, and it sends these messages to WoW clients ‘on demand’.

From the implementation point of view, we will assume that both the WoW server and WoW client are coded in Java, and they both deploy UDP sockets (i.e., UPD protocol is used to facilitate the exchange of WoW requests and WoW-message responses).

The ‘operator’ running the WoW server evokes this application/program with the following command:

&gt;  java WoWserver &lt;file&gt; &lt;port&gt;

where file is the name of the (local) file that contains the actual WoW repository (e.g., WoW.txt), and port is the port number on which the server listens for incoming requests. Each WoW request arrives in a separate UDP packet and is processed independently of other (previous) WoW requests. That is, as soon as the server responds to one requests, it loops back and serves another request, without attempting to examine/validate whether the two requests arrived from the same client or not.

On the other hand, the user running the WoW client evokes this application/program with the following command:

&gt;  java WoWclient &lt;hostname&gt; &lt;port&gt;

where hostname is the name of the machine that currently hosts/runs the WoW server program, and port is the WoW server’s port number. Once evoked, the WoW client sends one WoW request <u>every 5 seconds</u>, and each received WoW message is displayed to the user.

The code for the WoW server is provided for you at: <a href="http://www.cse.yorku.ca/course/3214/Notes/WoWserver.java">www.cse.yorku.ca/course/3214/Notes/WoWserver.java</a>

A sample repository of WoW messages is also provided at:

<a href="http://www.cse.yorku.ca/course/3214/Notes/WoW.txt">www.cse.yorku.ca/course/3214/Notes/WoW.txt</a>

<strong>Your task is to implement the WoW client (i.e., write the code for WoWclient.java) which can adequately communicate with and request/receive service from the provided WoWserver.java. </strong>

<strong><u>Note:</u>  </strong>

<ul>

 <li>The WoW server only expects requests (UDP packets) from WoW clients. Thus, it is really not necessary that these requests/packets carry ‘meaningful’ content. That is, in order to request a WoW message, a WoW client will simply send a UDP packet with 1 byte of (random) payload data. Accordingly, as soon as the WoW server receives a UDP packet with 1 byte of payload, it will consider this to be a valid request, and will send a WoW message back.</li>

 <li>It is possible that you will not have access to two different computers when testing WoWserver.java and WoWclient.java. So, if both of the programs have to be run on the same machine, then the value of hostname will simply be ‘localhost’.</li>

</ul>