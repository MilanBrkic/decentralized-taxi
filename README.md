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

## Tech specs

### Architecture
<img src="https://github.com/MilanBrkic/decentralized-taxi/blob/main/High_level_architecture.png" alt="App architecture" width="600"/>

### DB data model
<img src="https://github.com/MilanBrkic/decentralized-taxi/blob/main/Db_data_model.png" alt="Data model" width="600"/>

### Payment table
<img src="https://github.com/MilanBrkic/decentralized-taxi/blob/main/table_of_payments.png" alt="Payment table" width="600"/>

The payment table tells us all the possible outcomes of the ride. These are the representations of the columns:
- "Driver" - did he confirm he arrived with the passenger at the end destination?;
- "Passenger" - did he confirm he arrived at the end destination?;
- "Driver arrived" - did the driver REALLY arrive at the end destination? (Admin checks this);
- "Passenger arrived" - did the passenger REALLY arrive at the end destination? (Admin checks this);

So depending on the boolean value of the above columns, payment is determined by the next variables:
- v: represents the value or price of the ride
- d: represents a deposit that both participants need to pay before the ride. Mostly some percent of the v variable.

The participant that has not cooperated and is dishonest, will lose the deposit value.
