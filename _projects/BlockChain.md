---
short_name: Light-civilization 
name: Blockchain Light-civilization 
date: 2019-12-19
summary: Light Civilization is an online RTS(Real Time Strategy) game based on Ethereum.
youtubeID: gwvuXl3semk
thumbnail: ../images/thumbnail_images/thumbnail_lightcivilization.png
---

# Light-Civilization on Ethereum

> Posteck CS490: Blockchain & Cryptocurrency

* 1st SangKi Kim 
	* Pohang University of Science and Technology  
	* * sangki@posteck.ac.kr
*  2nd SangKyu Jeon
	* Hangdong Global University
	*  skjeon96@naver.com

## Introduction

* Light Civilization is an online RTS game based on Ethereum, inspired by the game "Civilization" produced by "Firaxis Games. The existing game, called civilization, is a game of territorial expansion, prosperity and development using various diplomatic factors, such as negotiations, battles and alliances among players. Light Civilization, among these, provides a simple strategy game by focusing on battles. 

* Light Civilization is web-based game. For the front end, it utilized express frame work with jade file. At the back end, all the smart contracts are coded with solidity and deployed on network with remix-ide. 

* To learn about scalability of Ethereum and block chain technology, to build a definite revenue in games and to experience the possibility of online games is available on blockchain, we have developed Light Civilization.

## Design

### Goal

* We developed Light-Civilization using Ethereum to be more productive and game-seeking. While it is common to use Unity or Unreal Engine to develop, which can make good use of Graphics, Light Civilization is a game that takes advantage of Blockchain’s strength. The following are three goals that we were trying to achieve on the Ethereum platform.
* First, today's blockchain technology is a technology based on strong security and trust that has never been seen before. Games also need a leap in these skills. This is our personal challenge, but it was also our exploration of the scalability of the blockchain in other words, we were trying to check the possibility of block chain.
* Second, we wanted to form a definite profit structure. When developing games in the past, the most difficult but obvious is the problem of generating revenue. Unlike general services, many online games do not require an admission or subscription fee.
* Thus, game companies often force to insert contents to charge money in games or add advertisements that harm game quality to the game itself. However, in blockchain platform, everything works and trades with coins called ether. So, we aimed to use Ethereum to generate revenue in a way that does not interfere with game play.
* The last is to run online games that are processed in real time on the Ethereum platform. Although we have not yet experienced a game that runs on the blockchain with real-time, it is a very important attempt to speed up the process of dealing with such a powerful security-based technology. Therefore, it is our last goal to run without any problems in the Ethereum through the RTS genre.

### Adavnatage

* With Light Civilization choosing Ethereum Blockchain, the advantages of getting good marks from the game market are as follows:
* First, as mentioned earlier, it can create a clear revenue structure. In Ethereum, all running contract is run by consuming gas on Ethereum. In this way, all transactions are recorded in blockchain of Ethereum, which has an environment sufficient to make a profit from a small amount of taxes by charging them from the beginning. So without unnecessary advertising or charging systems, players enjoy games and developers can generate revenue.
* The second is the prevention of hacking. All accounts require only user account address, not user personal info. Therefore, it is far from the issue of personal information leakage. Even if the system inside the game intentionally executes certain codes indefinitely by attempting to hack into the system, thanks to gas Consumption , it is unlikely that the hacker hacks into the system. Of course, changing the contents of the blockchain is a more difficult task for strong security algorithms like PoW and PoS, so it has great advantages with respect to security.
* Finally, it is an advantage to the server. Due to the property of MMO games, servers must always be open, and it takes a lot of money and experts to run them. However, Ethereum is a blockchain-based platform. It is possible to upload data to a block and read blocks that are propagated. In this way, server operating costs can be greatly reduced by using blockchain rather than by opening and operating a private service.
* Considering these advantages, there is enough reasons to develop RTS-style games on block chain.

### Support

* There are many tools that supports developing Ethereum DApp. Solidity is a language for creating Smart Contract.  The EVM tool “truffle" and " remix ide" exist to help distribute the prepared smart contact to the block chain. Truffle even supports test-net ganache-cli and front-end library drizzle. 
* Web 3 js is a library that provides access to the blockchain of the Ethereum when web is operated as a front. 
* In addition, if you use nethereum, you can develop games by linking it with Unity, a game engine tool. 
* As such, much of Ethereum platform’s scalability and its own development are now developing. In our project, we have developed web DApp game, using solidity, remix and web 3 js.

### High Level Design

* In a Light-Civilization project, there are two main designs. Back-end, which manages and deploy Smart-contract, and front-end, which is responsible for the appearance of the game.

<center> <img src="../images/project_images/Blockchain/highlevel_1.png" alt="highlevel_1" style="zoom:100%;" /></center>


​                               

* First is back-end. At the back end, the smart contact is coded using solidity . These smart contracts than is deployed to the network such as private network, main-net or ganache-cli. .

  <center> <img src="../images/project_images/Blockchain/highlevel_2.png" alt="highlevel_1" style="zoom:100%;" /></center> 

* On the Front-end, it enable web through node.js and access blockchain through web3.js libary in javascript. The Web is designed by utilizing the express frame work and jade file.

 

## Implementation 

### System Hierarchy

* This is a system high-level diagram that further embodies the high-level design described earlier.

<center> <img src="../images/project_images/Blockchain/system_hierarchy.png" alt="highlevel_1" style="zoom:100%;" /></center> 

* Front-end offers a total of three web-pages. It consists of login page, sign up page, and main page, respectively. All of the pages are linked to node.js and through web 3 js, all the data that is necessary to render the page, is loaded from blockchain. 
* In the Back-end, a contract called userAction, deployed by remix-ide, is executed. In this userAction Contract, the game is executed by runing functions written in thesmart contract in userAction. Most of variables, such as account information and map data is saved at contract mapData and userData. 



### Front-end

* This is a diagram of how front-end is executed when user is trying to play Light-Civilization.

<center> <img src="../images/project_images/Blockchain/front_end.png" alt="highlevel_1" style="zoom:100%;" /></center>                                

* First, user can access the main page through login or, if user do not have any account, user can create an account by connecting to the sign-up page.
* Account number, user id, and password can be used to create an account. The generated account is added to the userData array. 
* After generating an account, user can access the main page by connecting through login-page again. The Main page allows users to play the game by executing function that is written in smart contract. 
* For all the action, gas is consumed and all the actions are recorded in the Ethereum blockchain as an transaction.

### Back-end

* In Back, the design is as follows:

<center> <img src="../images/project_images/Blockchain/back_end.png" alt="highlevel_1" style="zoom:100%;" /></center>                                

* Mapdata contains the information, capital of the city's owner, the city's HP, fortification existence and number of soldiers.
* These data are implemented in a structure type and declared as an array type to manage information of the city that is occupied by users. In addition, all information is inherited by userData.
* In userData, it contains information on accounts, game goods, and values of survival. These data are implemented as a structure type and declared as array type, as in mapData, to manage information about the account.
* All this information is inherited again by userAction.
* The functions of account creation, login, military purchase, attack, recovery, userData return, mapData return, etc. are defined.

### Function

* A total of five important functions are implemented in the game.

* First, collect taxes. Every seconds, the user can collect 1  game goods, which are can be exchanged for soldiers or build fortifications. Second, fortification construction. The price of the fortification construction is 100 game goods, and in construction the defense can be increased to 2 time of origin defense system to activate the defense for once. Third, recovery. Fill up the city's physical strength up to 100. Fourth, military purchase. You can buy a soldier with 1 attack power for 1 dollar. Lasly, attack. Select the target city to attack, select the city and the quantity of the soldiers to be dispatched from among your cities, and launch the attack.



### Game Policy

* The game policy of Light civilization is simple in three ways:

<center> <img src="../images/project_images/Blockchain/game_policy_1.png" alt="highlevel_1" style="zoom:100%;" /></center>                                

* First, play for survival, not victory. After a fierce battle between blue player and red player and , even if the blue player wins and takes over the city of red player the game does not end as long as there are still  users in the game. Thus, this is an end less battle game.

<center> <img src="../images/project_images/Blockchain/game_policy_2.png" alt="highlevel_1" style="zoom:100%;" /></center>                                

* Second, if player has captured(take over) another city in battle, than the city is now belong to the winner. For instance, if blue player has conquered city B, than the territory of B is owned by blue player.

<center> <img src="../images/project_images/Blockchain/game_policy_3.png" alt="highlevel_1" style="zoom:100%;" /></center>                                

* Finally, alliances are not allowed. This is a game. Every players should be equal in the game. Therefore, it is not allowed to form an alliance.

## Result

* Light-Civilization prototype test was successfully done. Front and Back-end systems were successfully implemented. User were able to access and generate accounts. Without any errors, users were able to execute all the smart contracts. Moreover, all the policies that were mentioned above, had been successfully worked in the demo. 

   

## Conclusion

### Light-Civilization with Ethereum

* From Light-Civilization project, we were able to link a game concept with blockchain technology, Ethereum. Still there are many steps to procced, but we have achieved developing a game on Ethereum. 

* We have experienced that with the technology of Blockchain, more services can be served to public just like Light-Civilization. 

* However, we also experienced that all the execution from Ethereum could charge money, which means that ether and gas from execution should be fairly designed unless this game could be worse than any other games. Thus, in order to develop a game that runs on Ethereum, level design should be fairly done.

### Lack of front-end skill

* From the demo, it is clear that the front design must be done with expertise assists. Icons and texts are not clearly aligned, and buttons are not user friendly. For this reason, players cannot easily click buttons and view the data of players from the pages. It is definite that art designers are necessary for this project.

### Charging System

* Since this is prototype of Light-Civilization, we had excluded charging system from the game. Hence in the demo either user or the game company cannot make any profits. However, the gas is still consumed from players whenever they execute smart contracts.
* In the upgraded version of Light-Civilization we will include charging system in a way of profits structure.



> ##### References
>
> [1]   Icon made by Bercis from www.flaticon.com
>
> [2]   Icon made by Freepik from www.flaticon.com