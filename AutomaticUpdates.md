# Configuration of Automatic Updates
As part of Cepheo E-Bank, several procedures have been created that will automatically perform specific functions in the solution. These can be configured to run through job queues in Business Central. Below you will find a description of these routines and how they can be configured.
## Automatic Status Updates - Bank Transfers
Codeunit 72182591 "DXTEBANK AritmaStatusUpdate"
This procedure will automatically retrieve status updates for all bank transfers that have been sent to the bank. We recommend that this is configured in a job queue that runs at least once per hour, but not more often than every 2 minutes.
## Automatic Retrieval of Charged Bank Transfers
Codeunit 72182594 "DXTEBANK GetBookedPayments"
This procedure will automatically retrieve new charged bank transfers from the bank. We recommend that this is configured in a job queue that runs at least once per day, but not more often than once per hour.
## Automatic Posting of Charged Bank Transfers
Codeunit 72182595 "DXTEBANK Post Booked Banktrans"
This procedure will automatically post bank transfers that have been charged in the bank, but which have not yet been posted in Business Central. We recommend that this is configured in a job queue that runs at least once per hour, but not more often than every 2 minutes.
