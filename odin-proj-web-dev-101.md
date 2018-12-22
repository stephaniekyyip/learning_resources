# [ The Odin Project: Web Development 101](https://www.theodinproject.com/courses/web-development-101)

**Key**

- [The Basics](#the-basics)
  - Intro to Web Development

  - How Does the Web Work?

---

### The Basics

#### Introduction to Web Development

- Web developers build and maintain websites, often for clients trying to get their product/ service on the web.

- Front End: Stuff you see on the website. Presentation of content and UI elements. Uses HTML, CSS, JS, and related frameworks. Focused on good user experience. 

- Back End: Guts of the app. Lives on the server and processes data to meets the needs of the front end. Uses Java, Python, Ruby, etc. 

- Full Stack: Both front and back end. 

- :exclamation:  [Happy Bear Software article: How to get a job as a full-stack web developer](https://www.happybearsoftware.com/how-to-get-a-programmer-job)

#### How Does the Web Work?

[Video: BBC Computing -- How Does the Internet Work?](https://vimeo.com/128575085)

[MDN - How Does the Internet Work?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work#Summary)

- **Internet**: Network of computers that are connected adn communicate with one another.
- Each computers on a network is connected to a __router__, which makes sure that a message sent from one computer arrives at the correct destination comptuer.  
- Routers reduce the number of cables required to connect computers to a network, since only one plug is required for each computer to the router, instead of a plug for every connection between two computers. 
- Routers can be connected to other routers to scale the network of computers.
- However, to form networks across the world, you cannot rely on only routers and physical connections between computers. Since telephone cables are already linked to your house, you can connect a network to the telephone infrastructure using a __modem__, which translates the information between the computer network and the telephone infrastructure.
- To send messages from our network to other networks, we need to connect to an __Internet Service Provider (ISP)__, which manages special routers that link together and can access other ISP's routers. 
- Each computer connected to an network is uniquely identified by an __IP Address__. However, the address consists of numbers that are difficult for humans to remember, so these IP addresses are aliased with a __domain name__. 
  - E.g. `google.com` = `173.194.121.32`
- Internet != the Web
  - Internet: Technical infrastructure to allow billions of computers to be connected. 
  - Web: Some of these computers, i.e. web servers, can send messages to be read by web servers. 
  - The Internet is an infrastructure. The web is built on top of that infrastructure. 

[Video: How the Internet Works in 5 Minutes](https://www.youtube.com/watch?v=7_LPdttKXPc&feature=youtu.be&t=46s)

- Servers are computers directly connected to the Internet. Each has its own IP address.

- Webpages are files on the server.

- Computers that we use at home (i.e. laptops) are called __clients__ because they're not directly connected to the Internet, but rather, connected via an ISP (Internet Service Provider).

- Files that are sent over the Internet are broken down into smaller pieces called __packets__. Upon reaching its destination, the packets are reassembled into the correct order to obtain the file.

- Everything connected to the Internet has an IP address. 

- __Routers__ are located where two or more places on the Internet intersect. They help direct packets  reach their destination. 

[MDN - What's the difference between webpage, website, web server, and search engine?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Pages_sites_servers_and_search_engines#Summary)

- **Web Page:** A document written in HTML that can be displayed in a web browser. Each web page is accessed through a unique address.

- **Website**: A collection of web pages grouped together that shaw a unique domain name.

- **Web server**: A computer that hosts a website or multiple websites on the Internet, meaning that all the web pages and files for that website is stored that computer. The server sends any web page from the website to a user's browser as requested.

- **Search Engine:** A website that helps you find web pages from other websites (e.g. Google). 

- **Web Browser**: Software that retrieves and displays web pages. 

[MDN - How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

- **Client**: The typical web device that users use to connect to the Internet, such as computers and phones, as well as the web browsers on those devices.

- **Server**: Computers that store webpages, websites, or apps. A copy of a webpage is downloaded from the server to the client to be displayed on the client's web browser when requested.

- **TCP/ IP**: Transmission Control Protocol and Internet Protocol. Communication protocols that define how data travels across the web.

- **DNS**: Domain Name Server. A website's real address that a web browser needs to retrieve in order to find which server the website is located on in order to send HTTP messages to the right place.

- **HTTP**: Hypertext Transfer Protocol. An application protocol that defines how clients and servers communicate with one another.

- **Component Files**: The files that make up a website, including code files (HTML, CSS, JS) and assets (images, music, videos, etc.).

- **Packet**: Data sent across the web are sent as many small chunks to allow multiple users to download the same website at the same time.

  

1. Browser uses the DNS server to get the real address of the server where the website is located.

2. Browser uses TCP/IP to send HTTP request to server to request a copy of the website for the client. 

3. Server sends client a "200 OK" message if the client's request is approved and then sends all the website's files to the browser via data packets.

4. Browser assembles the packets to display the website. 

   

[Video: DNS Explained](https://www.youtube.com/watch?v=72snZctFFtA&feature=youtu.be&t=45s)
