Lottery Smart Contract
======================

This smart contract is a simple lottery game that allows multiple users to buy tickets and participate in a game. The contract owner sets the price of each ticket and the maximum number of tickets that can be sold in a round. The contract maintains a record of all ticket holders and their ticket counts, as well as a prize pool that is funded by the ticket sales. When a winner is selected, the prize pool is distributed to the winner.

Features
--------

*   Multiple users can buy tickets for the lottery by calling the `buyTicket` function and sending the required amount of funds to the contract
*   The contract owner sets the ticket price and maximum ticket count using the `constructor` function when deploying the contract
*   A record is kept of all ticket holders in the `ticketHolders` array and their ticket counts in the `ticketCounts` mapping
*   A prize pool is funded by ticket sales and can be accessed by calling the `prizePool`
*   A winner is selected by calling the `selectWinner` function and the prize pool is distributed to the winner
*   An optional referral system allows users to receive additional tickets when they refer other users to the lottery by specifying a referrer in the `_referrer` argument of the `buyTicket` function
*   The contract includes events for logging when a ticket is purchased, granted to a referrer, and when a winner is selected, which can be used for auditing or front-end display purposes

Contract Details
----------------

*   The contract maintains a `roundNumber` public variable to track the current round of the lottery
*   The contract includes a `maxTicketCount` public variable to store the maximum number of tickets that can be sold in a round
*   The contract has a `ticketsSold` public variable to keep track of the number of tickets sold in the current round
*   The `ticketPrice` public variable stores the price of each ticket in wei
*   The `winner` public variable stores the address of the winner once a winner has been selected
*   The `ticketCounts` mapping stores a record of the ticket counts for each user, and the `ticketCountsKeys` array stores the keys for this mapping in the order that they were added
*   The `newHolders` private variable is a temporary array used for properly canceling tickets when the `cancelTicket` function is called
*   The contract includes three events for logging: `TicketPurchased`, `TicketGranted`, and `WinnerSelected`

Usage
-----

To participate in the lottery, a user must first buy tickets by calling the `buyTicket` function and sending the required amount of funds to the contract. The user can also specify a referrer in the `_referrer` argument to receive additional tickets. If no referrer is specified, the user can still participate in the lottery.

Once the the contract owner calls the `selectWinner` function, a winner is selected and the prize pool is distributed to the winner.

Requirements
------------

*   A web3 enabled Ethereum wallet
*   A small amount of Ethereum for purchasing tickets

License
-------

This smart contract is licensed under the MIT License.
