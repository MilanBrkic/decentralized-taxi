# Decentralized Taxi App  
### [Full Demo](https://youtu.be/qmGPU88ZN5M) <br>  
![Gif demo](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbXN5eDZvMjhuM2RxdW90NWlkZGRpZG81N3J6dm16aXc4am81b3hleCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/2uZqZt1Gwq8HEkPFFG/giphy.gif)

<br>  
A taxi app with a smart contract running on the TestNet blockchain of Algorand. Classified more as a "Web 2.5 App," since it makes use of a smart contract to control every scenario that could arise during a taxi journey. However, in the event that players are uncooperative, the centralised server must assist in locating the participants. The centralised server doesn't need to become involved if the passenger and rider cooperate and the ride ends as planned. If a server interferes, participants who are dishonest about their location are penalised.
<br>
<br>
This app has been created as part of my final thesis for my master's degree. It enables:  

- Passengers to request rides;
- Drivers to bid on rides;
- The passenger to choose the best offer;
- The ride conclusion and payment to be decided decentralised.

### <b>[Backend:](https://github.com/MilanBrkic/decentralized-taxi-backend)</b>  
- Written in Node.js and TypeScript;  
- MongoDb for storing off-chain data;  
- WebSockets for enabling sending and receiving real time data (location, ride bids);  
- Lib @reach-sh/stdlib for calling methods and listening to events on the smart contract

  
### <b>[Smart Contract:](https://github.com/MilanBrkic/decentralized-taxi-blockchain)</b>  
- Used [Reach.sh](https://www.reach.sh/) for writing smart contracts;
	- A write once, compile to multiple smart contract languages on different chains;
	- JavaScript familiar syntax
	- Has support for Ethereum, Algorand, etc;
- Deployed on Algorand TestNet;
- Fully tested with the @reach-sh/stdlib;

  
### <b>[Mobile:](https://github.com/MilanBrkic/decentralized-taxi-mobile)</b>  
- Used ExpoDev for development;
- Done in React Native
- Using Google Maps API for mapping coordinates to address names and vice versa

## App architecure
![App architecture]()
