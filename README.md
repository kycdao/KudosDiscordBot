# KudosDiscordBot
A bot to encourage users to make helpful comments in Discord

# Concept

Kudos Discord Bot (working title…) is a bot which tracks the kudos tokens given to certain users in a Discord server for contributing by making helpful comments in the server. Users are then ranked in the server so the community can see who has been the ‘most helpful’, thereby encouraging users to stick around on servers and contribute. An NFT is used to keep track of all the Kudos tokens you’ve received from various different servers, so you can show-off how helpful you’ve been in the Web3 world!

# Inspiration

The concept was inspired by the various Web3 Discord servers that are filled with users (often beginners) that are all looking to understand a certain framework/technology/blockchain. The ‘help’ channels are filled with unanswered questions, as the server admins do not have time to answer everyone and need the rest of the community to chime in with answers. A lot of users simply join to ask their question, leave when it doesn’t get answered after a long time or leave even if it IS answered, as they have no motivation to stick around and be helpful to others. Having a way to track users helpful responses encourages people to stay, and answer any questions that they might understand. It gives the server admins a way of tracking who is the most helpful and each community can reward these users as they see fit.

# How does it work?

## Add the bot to your server

The first step is to download the Kudos bot and add it to your Discord server

## Server Registration

Next, with the bot running in your channel, the Discord server admin *[can we somehow authenticate who is an admin?]* will run the `/kudos_serverRegister` command. This command will open a page where you can register your Discord server as part of the Kudos program. *[This would trigger server registration in the smart contract, with the Discord server id for their specific Kudos token. In this step we should probably set up GSN for all the txs the bot will make on their behalf as well.]*

## User Registration

Users would then need to individually register themselves for the Kudos program by running the ‘/kudos_userRegister’ command in a channel with the bot. This would take them to a user registration page where they would first run a quick ‘captcha’ to discourage bots, and then register themselves by minting a cool looking Kudos NFT to their chosen wallet address. At this point their address and Discord username is linked. *[Should the NFT mint go through GSN?]* The User Registration only needs to happen once, after this each other Discord server (with a separate Kudos token) can track the users existing Kudos NFT.

## Giving Kudos

When a user that is registered with the Kudos program makes a helpful comment in Discord, other registered users can then react to the comment with a special custom ‘Kudos’ emoji, indicating that they found the comment especially helpful. The Kudos bot first checks that both users are registered, then it mints a server specific Kudos token to the user that created the comment. A user is allowed to award/mint only X(3?) tokens per day to other users, after this any Kudos emoji reactions are ignored by the bot. Any kudos reactions given to their own comments are also ignored. *[How do we prevent people from creating alt accounts to react to all their comments to game the system?]*

## Seeing Kudos rankings

The Kudos ranking site will display the Kudos tokens given to users from various different servers by interacting with the deployed smart contract itself. It will consist of a few pages:

- A user page which displays all the server token counts for a specific user (by looking at their connected wallet address).
- A server page which ranks the various users and displays those with the most Kudos tokens for that server.

# Future / Extensions

## Kudos tiers / rewards

It might be useful for each Discord server to group certain Kudos token rankings into ‘tiers’, so that those in specific tiers can be given special titles/badges in the Discord server.

Or they might want to reward those in the highest rankings every month with their own ‘spendable’ token.

## Tracking common questions

Common questions get asked multiple times, it would be helpful for the Discord bot to somehow ‘pin’ or ‘track’ often asked questions and have this on the Kudos site for a place for new users to look up commonly asked questions. This might be done with keyword tracking, or tags.
