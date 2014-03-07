PTS-Template
================================

Copyright (c) 2009-2013 Bitshares PTS Developers
Copyright (c) 2013-2014 Barwizi

Minimal Changes Needed 

Search/replace "BitShares-PTS" with your coin's name.

Replace/Rename /src/qt/res/icons/ files to your coins name (i.e.: Bitshares PTS.png to yourcoin.png)

Replace /src/qt/res/images/* with your own images.

Change /src/main.cpp following lines:

LINE 1073: int64 nSubsidy = 80 * COIN; //set your block rewards, it's adviseable to set reducing rewards else your chain will have infinite coins, the MAX_MONEY setting in main.h is only called in rare instances and is not enough to effectively limit the amount of coin produced in the chains lifetime. 


---------------------------------------------------------------------------------------------------------

Now, compile it like foocoin and run it. Debug.log will spit out a Merkel, for you. 

change 

/src/main.cpp LINE 38 uint256 merkleRootGenesisBlock("0x");

paste the new merkle then run it again with valid one and it will give you Genesis Block, nNonce and birthdays and ntime

/src/main.cpp LINE20: const bool IsCalculatingGenesisBlockHash = false;

Plug the new values here:

/src/main.cpp LINE 2833 block.nTime   = 0;

/src/main.cpp LINE 2835 block.nNonce   = 0;

/src/main.cpp LINE 2836 block.nBirthdayA   = 0;

/src/main.cpp LINE 2837 block.nBirthdayB   = 0;

/src/main.h LINE 64 static const uint256 hashGenesisBlockOfficial("0x"); 65 if you are working on a testnet

Now recompile with the new .cpp and .h and your MOMPoS coin is ready to go! 

--------------------------------------------------------------------------------------------------------------

Advanced Changes for Development Teams

/src/main.h LINE 29  --- change the max size of your blocks 

/src/main.h LINE 51  --- change the minimum transaction fee

/src/main.cpp LINE 39 --- change minimum work difficulty the template comes with lowest difficulty to make function testing easier, change it as you wish. 

/src/main.h LINE 53 --- change how long mined coins take to mature

TODO++

Genesis Block creation function

Balance importation tools and functions

Tip Jar PTS --- PiNEJGUv4AZVZkLuF6hV4xwbYTRp5etWWJ
Tip Jar BTC --- 1CCuamNem7kaEFUxHTLCQUMhpiHds4sdpA
