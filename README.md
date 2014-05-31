PADTool BETA - An automatic game manager.
=======
Authenticated APIs-------------------------------------------
Account---------------------------------
/user/getAccount
/user/getSecretId
/user/listAccount
/user/addAccount
/user/downloadAccount
/user/toggleGameSettings
/user/togglePrivacySettings
/user/rollMachine
/user/spendStone
/user/issueDeviceChangeCode
/user/restoreStamina
/user/buyMonsterSlot
/user/buyFriendSlot

Monsters--------------------------------
/user/getMonsterBox/{accountId}/ - GET
 > Returns the user's complete monster box. Materials are considered monsters.
 > {accountId} is not the ingame ID. It's the number returned in the 'id' value of /user/getGameAccounts.
 
/user/getTeams - GET
 > Returns the monster IDs of each of the user's teams. It should be matched to the cuid values returned with getMonsterBox.
 
/user/doMergeCards - POST
 > Fuse cards. No evo... yet.
 
/user/sellCard
 
Friends---------------------------------
/user/getFriends
/user/sendFriendRequest
/user/getSuggestions
/user/getId
/user/getAllMessages
/user/getMessage
/user/respondFriendRequest
/user/toggleFavMessage
/user/deleteMessage
/user/deleteAllMessage
/user/sendMessage
/user/deleteFriend

/user/do

Public API - These API calls are used to programatically pull game data about users who have chosen to make their profiles public. They are not authenticated and thus are suitable for either a public profile page, or for data imports into another service.

NOTE: These APIs will return 500 Not Authenticated if the user has chosen to make it private. These APIs update every 5 minutes unless the user has forced an update by logging into his or her PADTool account and calling an authenticated account data API.

WARNING: Do not use these APIs for data mining purposes. Your app will be blocked if you do so. If you have a good reason to make high-volume requests, contact us.

/public/getAccount/{friendId}/ - GET
 > Returns some general information on the account.
 > {friendId} is the ingame Friend ID. Do not add in commas - submit only the 9 digit number.
 
/public/getMonsterBox/{friendId}/ - GET
 > Returns the user's complete monster box. Materials are considered monsters.
 > {friendId} is the ingame Friend ID. Do not add in commas - submit only the 9 digit number.

/public/getTeams - GET

/public/getFriends

Data API - These API calls can be used programatically to pull general game data, including data regarding monsters and dungeons. Their data is updated sporadically, but generally should be the most up to date version.
Please do not harvest data from these API calls to directly display on your own website without contacting us first about it. If possible, use this data to provide a value-added service! For example, use our APIs to provide a dungeon simulator.

/data/getMonsterBook
 > Returns the complete set of monster data from the game.
