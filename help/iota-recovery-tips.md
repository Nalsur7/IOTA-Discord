# Tips to understand the status of your wallet:

This is a collection of information to help our users understand the status of their IOTA 1.0 wallet

- [Differences between a wallet account with a correct seed and a new seed](#differences-between-a-wallet-account-with-a-correct-seed-and-a-new-seed)
  * [Address list of a correct seed](#address-list-of-a-correct-seed)
  * [Address list of a new seed](#address-list-of-a-new-seed)
- [Correct but unused account a.k.a. Snapshot Transition](#correct-but-unused-account-aka-snapshot-transition)
- [Reclaim](#reclaim)
- [iotaseed.io or online seed generator scam](#iotaseedio-or-online-seed-generator-scam)
- [Trinity Incident](#trinity-incident)
- [Wallet migration following the Moonpay incident](#wallet-migration-following-the-moonpay-incident)
- [Wallet NOT migrated following the Moonpay incident](#wallet-not-migrated-following-the-moonpay-incident)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


## Differences between a wallet account with a correct seed and a new seed

### Address list of a correct seed
- If the **Address List** in Trinity looks like this, it is a seed with incoming and outgoing transaction history

  ![image-20210110205421887](/_resources/images/help/image-20210110205421887.png) 

### Address list of a new seed
  If the **Address List** in Trinity looks like this, then it looks more like an empty wallet

  ![image-20210110205633372](/_resources/images/help/image-20210110205633372.png)

- Make sure to double/triple check if the seed is correct. By typing one wrong character an empty wallet will open. It is possible to use the following community tool to look for a typo in the seed.

  :warning: THIS TOOL IS A COMMUNITY TOOL AND IS NOT ENDORSED BY THE IOTA Foundation.  
  This tool also requires an Address where your tokens are, please make sure to have an address at hand where the tokens reside. It is possible to look at the exchange withdrawal history where the tokens have been retrieved:
  https://github.com/FVANtom/find-typo-in-iota-seed
### How to find an IOTA address on Bitfinex

Exhanges are required by AML law (Anti Money Laundering) to keep 5 years of financial records, therefore it should be possible to find an address in your withdrawals list.  
Follow the official guide from Bitfinex to get a report:
https://support.bitfinex.com/hc/en-us/articles/115003361173-Trade-Order-Reports
and make sure that the dates are selected (by clicking on them) like in this picture here:
![bitfinex-history](/_resources/images/help/bitfinex_history.png)

  
### Correct but unused account a.k.a. Snapshot Transition

- If the seed has less than 81 characters, one can pad the number `9` at the end of the input until the seed is 81 characters 
- If the seed is 100% correct and the tokens were not moves for a long time (1-2 years) then:

  **A)** Set Trinity to the following node settings, follow the settings top to bottom, so, disable **Automatic node management** first and go from there and in the end click on the **Save** button on the bottom of the screen 

  ![image-20210110184645086](/_resources/images/help/image-20210110184645086.png)

  
  Then click on the **Snapshot Transition** under the Account **Tools** until the tokens are available in your account:

  ![image-20210110174331122](/_resources/images/help/image-20210110174331122.png)

## Reclaim

  **B)** Please verify an address (from an exchange or similar) on https://explorer.iota.org  to see if the tokens are still there. 
  -  If the explorer shows 0 balance and there are also **outgoing** transactions that it is necessary to follow the outgoing transactions
  -  If the explorer shows 0 balance, AND there are **no outgoing** transactions, then it might be a reclaim case. It is possible to search your address and compare it with the list on the following page for a first assessment.  
  :warning: THE LIST CONTAINS ONLY ADDRESSES WITHOUT CHECKSUM. Should the address have 90 characters, make sure to remove the last 9 characters from the address that is being compared  
  https://gist.githubusercontent.com/cyclux/2bb05d873c4ec6115cad1d100263d489/raw/612a49e46091586957448f6606ea981ab18022e7/snapshot_validation_20171023.txt
  
  - If the text near the address says **AVAILABLE** then it is possible to access the tokens by inserting the correct seed into Trinity
    ![image-20210111085102865](/_resources/images/help/image-20210111085102865.png)  
  
  - If the text near the address says **KEY_REUSE** or **CURL_NOT_TRANSITIONED**
  
    ![image-20210111085016773](/_resources/images/help/image-20210111085016773.png)  
    Please send the **address** (WARNING: NEVER SHARE THE SEED) to the IOTA Foundation for further verification and confirmation.

  Example of an **address** that needs to be reclaimed. The Balance shown in 0. There is **only an incoming transaction** AND **no outgoing transactions** with ##.## MIOTA.
  ![image-20210110180647260](/_resources/images/help/image-20210110180647260.png)

## iotaseed.io or online seed generator scam

- Did the tokens move away between **January 2018** and **January 2019** and the seed was generated using iotaseed.io, then it is a theft case from the iotaseed.io scam.
  This is the relative article from Europol:
  https://www.europol.europa.eu/newsroom/news/cryptocurrency-iota-international-police-cooperation-arrests-suspect-behind-10-million-eur-theft
  This was the procedure that has been followed by one of the IOTA community users:
  The local police department received a questionnaire  from the state criminal investigation office which was to fill out. It was e.g. about the cyrpto-background; how the user found iotaseed.io; amount of coins,... 
  After answering all questions the next steps was basically that they are preparing a class action against the thief. This also includes Europol. So the users answers will be forwarded and collected at a higher instance before the perpetrator is sued.

## Trinity Incident

- Did the tokens move away between the **12th December 2019 and the 12th February 2020**, the user might be victim of the Trinity Incident, that involved the theft of the seed during the time Trinity integrated the Moonpay services. In that case send the address to the IOTA Foundation for further verification. (More information here: https://blog.iota.org/trinity-attack-incident-part-1-summary-and-next-steps-8c7ccc4d81e8)

## Wallet migration following the Moonpay incident
- Did the tokens move away between the **29th February 2020 and the 10th March 2020**, then it looks like the user was aware of the theft and did the migration using the migration tool (https://blog.iota.org/seed-migration-tool-now-available-c253ccd9d23c/). In this case there should be a SeedVault.kdbx and a journal.log file on their system. Make sure now to add the password protected SeedVault to Trinity. Be aware that the SeedVault file is password protected that has been chosen by the user during migration. Without the password it will not be possible to recover the tokens. . This video shows the whole migration and how to add the SeedVault to Trinity (https://www.youtube.com/watch?v=mjex3IU44VY)

## Wallet NOT migrated following the Moonpay incident
- Did the tokens move away **after the 11th March 2020**, then the user did not follow the migration, the seed might have been part of the aforementioned incident and the tokens have been stolen. In this case we encourage users who have had tokens stolen to file a report with their local police and to cite the following case number when doing so: LKA Berlin, Center for Cybercrime, case number: 200213-1717-i00290.
