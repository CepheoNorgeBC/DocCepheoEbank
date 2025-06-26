# Bank Reconciliation in Microsoft Dynamics 365 Business Central

Bank reconciliation is the process of matching your bank account transactions in Business Central with the actual transactions on your bank statement to ensure accuracy and identify any discrepancies.

## Overview
The bank reconciliation process in Business Central helps you:
- Verify that your bank account balance matches your bank statement
- Identify outstanding checks and deposits
- Detect bank errors or unauthorized transactions
- Maintain accurate financial records

## Prerequisites
Before starting bank reconciliation, ensure that:
- Your bank account is properly set up in Business Central
- Bank account posting groups are configured
- You have imported or manually entered bank transactions
- All relevant payments and receipts have been posted

## Step-by-Step Bank Reconciliation Process

### 1. Access Bank Account Reconciliation
1. Choose the ![Lightbulb that opens the Tell Me feature](https://docs.microsoft.com/dynamics365/business-central/media/ui-search/search_small.png) icon
2. Enter **Bank Account Reconciliations** and choose the related link
3. Select **New** to create a new reconciliation

### 2. Import Bank Statement
1. On the **Bank Acc. Reconciliation** page, choose **Import Bank Statement**
2. Select your bank statement file (if using electronic import)
3. Alternatively, manually enter bank statement lines

### 3. Match Transactions
Business Central provides several matching options:

#### Automatic Matching
1. Choose **Match Automatically** to let the system find matches
2. The system will match based on:
   - Transaction amounts
   - Transaction dates (within tolerance)
   - Document numbers
   - External document numbers

#### Manual Matching
1. Select unmatched bank statement lines
2. Choose **Match Manually**
3. Select the corresponding bank account ledger entries
4. Choose **OK** to confirm the match

#### Text-to-Account Mapping
1. Set up automatic posting for recurring transactions
2. Choose **Text-to-Account Mapping**
3. Define rules for automatic posting of bank fees, interest, etc.

### 4. Handle Unmatched Transactions
For unmatched bank statement lines, you can:
- **Create new entries**: For transactions not yet recorded in Business Central
- **Transfer to General Journal**: For complex transactions requiring manual posting
- **Write off differences**: For small rounding differences

### 5. Post the Reconciliation
1. Ensure all lines are matched or accounted for
2. Verify the **Statement Ending Balance** matches your bank statement
3. Choose **Post** to finalize the reconciliation

## Payment Reconciliation Journal
For processing customer and vendor payments, use the **Payment Reconciliation Journal**:

1. Choose **Payment Reconciliation Journals**
2. Import bank statement or payment files
3. Use automatic matching rules
4. Apply payments to open customer/vendor ledger entries
5. Post the journal

## Best Practices

### Regular Reconciliation
- Perform bank reconciliation monthly at minimum
- Reconcile more frequently for high-volume accounts
- Don't let unreconciled items accumulate

### Bank Statement Import
- Set up electronic bank feeds when possible
- Use standard bank file formats (ISO 20022, BAI, etc.)
- Maintain consistent import procedures

### Matching Rules
- Configure automatic matching rules for recurring transactions
- Set appropriate date and amount tolerances
- Review and update matching rules regularly

### Outstanding Items
- Investigate old outstanding checks and deposits
- Follow up on unreconciled items promptly
- Maintain documentation for adjustments

## Troubleshooting Common Issues

### Duplicate Transactions
- Check for duplicate imports
- Verify posting dates and amounts
- Use filters to identify duplicates

### Missing Transactions
- Ensure all payments and receipts are posted
- Check for transactions in other periods
- Verify bank account selection

### Balance Differences
- Verify statement ending balance entry
- Check for unposted transactions
- Review bank charges and interest

## Integration with Aritma Pay
When using Aritma Pay with Business Central:
- Bank transactions are automatically imported
- Payment status updates are synchronized
- Reconciliation is streamlined through automation
- Matching rules can be customized for your banking setup

## Additional Resources

For more detailed information on bank reconciliation in Business Central, see the following Microsoft Learn documentation:

- [Reconcile bank accounts](https://learn.microsoft.com/en-us/dynamics365/business-central/bank-how-reconcile-bank-accounts-separately)
- [Set up bank account reconciliation](https://learn.microsoft.com/en-us/dynamics365/business-central/bank-how-setup-bank-accounts)
- [Apply payments automatically and reconcile bank accounts](https://learn.microsoft.com/en-us/dynamics365/business-central/receivables-apply-payments-auto-reconcile-bank-accounts)
- [Set up rules for automatic application of payments](https://learn.microsoft.com/en-us/dynamics365/business-central/receivables-how-set-up-payment-application-rules)
- [Reconcile payments using automatic application](https://learn.microsoft.com/en-us/dynamics365/business-central/receivables-how-reconcile-customer-payments-list-unpaid-sales-documents)

## Support
If you encounter issues with bank reconciliation while using Aritma Pay, contact support@aritma.com for assistance.