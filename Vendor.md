# Preferred bank account for vendors
The account used for bank transfers to vendors must be defined in the vendor bank account table in Business Central and all the vendors must have been set up with a preferred bank account.

The system will benefit from having both the bank account no. and the IBAN number defined for each bank account.

The application will always prioritize the use of IBAN when present on the vendor bank account. If no IBAN is present the system will use the national bank account no. 

In some cases the vendor may have several bank accounts and can have stated a spesific bank account on a spesific invoice. In these cases you can assign the correct bank account to the incoming invoice before it is posted. 


For more information on setting up vendor bank accounts, see [Set up vendor bank accounts](https://learn.microsoft.com/en-us/dynamics365/business-central/purchasing-how-set-up-vendors#to-set-up-vendor-bank-accounts-for-export-of-bank-files) in the Microsoft Learn documentation.
