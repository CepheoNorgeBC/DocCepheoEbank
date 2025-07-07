# Aritma Finance Manager - User Guide

## Table of Contents

1. [Getting Started](#getting-started)
2. [Initial Setup](#initial-setup)
3. [Managing Bank Accounts](#managing-bank-accounts)
4. [Processing Payments](#processing-payments)
5. [Transaction Management](#transaction-management)
6. [Bank Reconciliation](#bank-reconciliation)
7. [Reports and Analytics](#reports-and-analytics)
8. [Troubleshooting](#troubleshooting)
9. [Frequently Asked Questions](#frequently-asked-questions)

---

## Getting Started

### What is Aritma Finance Manager?

Aritma Finance Manager is a comprehensive banking solution for Microsoft Dynamics 365 Business Central that allows you to:

- Process payments directly from Business Central
- Import bank transactions automatically
- Reconcile bank accounts efficiently
- Manage multiple currencies and exchange rates
- Create payment proposals based on outstanding invoices
- Track payment status in real-time

### Key Benefits

✅ **Streamlined Payment Processing**: Create and send payments directly from Business Central
✅ **Automated Transaction Import**: Automatically import bank transactions
✅ **Real-time Status Tracking**: Monitor payment status and updates
✅ **SEPA Compliance**: Fully compliant with European payment standards
✅ **Secure Banking**: Industry-standard security with OAuth2 authentication
✅ **Multi-currency Support**: Handle payments in different currencies

---

## Initial Setup

### Prerequisites

Before you begin, ensure you have:
- Microsoft Dynamics 365 Business Central access
- Aritma Banking API credentials (client ID and secret)
- Bank account information (IBAN, account details)
- Appropriate user permissions in Business Central

### Step 1: Configure E-Bank Setup

1. **Open E-Bank Setup**:
   - Search for "E-Bank Setup" in Business Central
   - Click to open the setup page

2. **Configure Authentication**:
   - Enter your **Client ID** (provided by Aritma)
   - Enter your **Client Secret** (provided by Aritma)
   - Set **Authentication URL** to the provided endpoint
   - Set **Base API URL** to: `https://banking.dev.aritma.io/api/`

3. **Configure Bank Settings**:
   - Select your default **Bank Account**
   - Enter your **IBAN** number
   - Set up **Posting Groups** as needed
   - Configure **Notification Settings**

4. **Test Connection**:
   - Click "Test Connection" to verify your setup
   - Ensure you receive a successful authentication response

### Step 2: Set Up Bank Accounts

1. **Navigate to Bank Accounts**:
   - Go to **Bank Accounts** in Business Central
   - Select the bank account you want to configure

2. **Configure Bank Account Details**:
   - Enter **IBAN** and **SWIFT Code**
   - Set **Currency Code** if different from LCY
   - Configure **Posting Groups**
   - Set up **Dimensions** if required

3. **Link to API**:
   - Ensure the bank account is properly linked to the Aritma Banking API
   - Test the connection to verify data flow

### Step 3: Configure User Permissions

1. **Set User Permissions**:
   - Assign appropriate permission sets to users
   - Ensure users have access to banking functions
   - Configure approval workflows if needed

---

## Managing Bank Accounts

### Viewing Bank Account Information

1. **Access Bank Accounts**:
   - Search for "Bank Accounts" in Business Central
   - Select the desired bank account

2. **View Account Details**:
   - Review account balance and currency
   - Check last statement date
   - View recent transactions

### Adding New Bank Accounts

1. **Create New Bank Account**:
   - Click "New" in the Bank Accounts list
   - Enter account details (Name, Number, IBAN)
   - Set currency and posting groups
   - Configure API integration settings

2. **Configure Integration**:
   - Set up connection to Aritma Banking API
   - Test the integration
   - Verify transaction import functionality

---

## Processing Payments

### Creating Individual Payments

1. **Access Bank Transfers**:
   - Search for "Bank Transfer" in Business Central
   - Click "New" to create a new transfer

2. **Enter Payment Details**:
   - Select **Debtor Account** (your bank account)
   - Choose **Account Type** (Vendor, Customer, Bank Account, Employee)
   - Select the specific **Account No.**
   - Enter **Amount** and **Currency**
   - Set **Execution Date** (when payment should be processed)

3. **Add Payment Lines**:
   - Enter **Creditor IBAN**
   - Specify **Creditor Name**
   - Add **Remittance Information** (payment reference)
   - Include any additional reference data

4. **Submit Payment**:
   - Review all details carefully
   - Click "Submit" to send payment to the bank
   - Monitor status updates

### Creating Bulk Payments

1. **Generate Payment Proposals**:
   - Go to "Bank Transfer Proposals" report
   - Set filters for due date, vendor, or amount
   - Generate proposal based on outstanding invoices

2. **Review and Modify**:
   - Review the generated payment lines
   - Modify amounts or dates if needed
   - Remove any payments you don't want to process

3. **Process Bulk Payment**:
   - Select all payment lines to process
   - Click "Process Payments"
   - Monitor the batch processing status

### Payment Types Supported

- **Standard Credit Transfers**: Regular SEPA payments
- **Instant Payments**: Real-time payment processing
- **Scheduled Payments**: Future-dated payments
- **Bulk Payments**: Multiple payments in one batch

### Payment Status Tracking

1. **Monitor Payment Status**:
   - View payment status in the Bank Transfer list
   - Status updates include: Suggested, Submitted, Processing, Completed, Failed

2. **Handle Failed Payments**:
   - Review error messages for failed payments
   - Correct any issues (wrong IBAN, insufficient funds, etc.)
   - Resubmit corrected payments

---

## Transaction Management

### Importing Bank Transactions

1. **Automatic Import**:
   - Transactions are automatically imported from the Aritma Banking API
   - Import frequency can be configured in E-Bank Setup
   - New transactions appear in the Bank Transactions list

2. **Manual Import**:
   - Go to "Import Transactions"
   - Select date range for import
   - Choose specific bank accounts
   - Click "Import" to retrieve transactions

### Viewing and Managing Transactions

1. **Access Bank Transactions**:
   - Search for "Bank Transactions" in Business Central
   - View all imported transactions

2. **Transaction Details**:
   - **Date**: Transaction date
   - **Description**: Transaction description from bank
   - **Amount**: Transaction amount and currency
   - **Type**: Payment, Receipt, Fee, etc.
   - **Reference**: Bank reference numbers

3. **Categorize Transactions**:
   - Assign transaction types for better organization
   - Add internal references or notes
   - Link to related Business Central entries

### Transaction Processing

1. **Review New Transactions**:
   - Check for any duplicate transactions
   - Verify transaction amounts and dates
   - Ensure proper categorization

2. **Match Transactions**:
   - Link transactions to existing entries (invoices, payments)
   - Use auto-matching features where available
   - Manually match complex transactions

---

## Bank Reconciliation

### Automatic Reconciliation

1. **Access Bank Reconciliation**:
   - Go to the standard Business Central Bank Reconciliation
   - Select the bank account to reconcile

2. **Import Statement**:
   - Import bank statement data via Aritma integration
   - Review imported transactions
   - Check for any discrepancies

3. **Auto-matching**:
   - Use automatic matching features
   - Review suggested matches
   - Confirm accurate matches

### Manual Reconciliation

1. **Match Transactions Manually**:
   - For transactions that don't auto-match
   - Select the bank statement line
   - Choose the corresponding ledger entry
   - Confirm the match

2. **Handle Discrepancies**:
   - Investigate unmatched transactions
   - Create journal entries for bank fees or charges
   - Resolve any differences

3. **Complete Reconciliation**:
   - Ensure all transactions are matched
   - Post the reconciliation
   - Review the final bank account balance

---

## Reports and Analytics

### Payment Reports

1. **Bank Transfer Reports**:
   - View all payments by date range
   - Filter by status, amount, or account
   - Export data for analysis

2. **Payment Status Reports**:
   - Monitor payment processing status
   - Track failed payments and reasons
   - Generate compliance reports

### Transaction Reports

1. **Transaction History**:
   - View transaction history by account
   - Filter by date, amount, or type
   - Generate detailed transaction reports

2. **Balance Reports**:
   - Current account balances
   - Historical balance tracking
   - Multi-currency balance reporting

### Custom Reports

1. **Create Custom Reports**:
   - Use Business Central's reporting tools
   - Include Aritma banking data
   - Schedule automatic report generation

---

## Troubleshooting

### Common Issues and Solutions

#### Authentication Problems

**Issue**: Cannot connect to Aritma Banking API
**Solution**:
1. Verify Client ID and Client Secret are correct
2. Check that the API URL is properly configured
3. Ensure your IP address is whitelisted (if required)
4. Contact Aritma support if credentials are expired

#### Payment Failures

**Issue**: Payment rejected by bank
**Solution**:
1. Verify IBAN format is correct
2. Check account has sufficient funds
3. Ensure payment amount doesn't exceed limits
4. Review creditor information for accuracy

#### Transaction Import Issues

**Issue**: Transactions not importing automatically
**Solution**:
1. Check API connection status
2. Verify date ranges for import
3. Ensure bank account is properly configured
4. Review API rate limiting settings

#### Reconciliation Problems

**Issue**: Transactions not matching properly
**Solution**:
1. Check transaction references and amounts
2. Verify dates align between systems
3. Look for duplicate transactions
4. Use manual matching for complex cases

### Getting Help

1. **Check Documentation**: Review this user guide and technical documentation
2. **Contact Support**: 
   - Aritma Support: https://www.aritma.com
   - Technical Support: https://www.cepheo.com
3. **API Documentation**: https://banking.dev.aritma.io/api/
4. **Business Central Community**: Use Microsoft's Business Central community forums

---

## Frequently Asked Questions

### General Questions

**Q: What banks are supported by Aritma Finance Manager?**
A: Aritma Finance Manager supports banks that comply with SEPA standards and integrate with the Aritma Banking API. Contact Aritma for specific bank compatibility.

**Q: Can I process payments in multiple currencies?**
A: Yes, the system supports multi-currency payments with automatic exchange rate handling.

**Q: Is there a limit on payment amounts?**
A: Payment limits are determined by your bank and account settings. Check with your bank for specific limits.

### Technical Questions

**Q: How often are transactions imported?**
A: Transaction import frequency can be configured in the E-Bank Setup. Default is typically every few hours, but can be set to more frequent intervals.

**Q: What happens if a payment fails?**
A: Failed payments are marked with an error status and detailed error message. You can review the error, correct the issue, and resubmit the payment.

**Q: Can I cancel a payment after it's submitted?**
A: This depends on the payment status and your bank's policies. Contact your bank directly for payment cancellation requests.

### Security Questions

**Q: How secure is the Aritma Finance Manager?**
A: The system uses industry-standard OAuth2 authentication, TLS encryption, and secure credential storage via Azure Key Vault.

**Q: Who can access the banking functions?**
A: Access is controlled through Business Central's permission system. Only users with appropriate permissions can process payments and access banking data.

**Q: Are my banking credentials stored securely?**
A: Yes, all sensitive credentials are stored in Azure Key Vault with enterprise-grade security measures.

### Compliance Questions

**Q: Is Aritma Finance Manager SEPA compliant?**
A: Yes, the system is fully compliant with SEPA (Single Euro Payments Area) standards and regulations.

**Q: What audit trail is available?**
A: The system maintains comprehensive audit logs of all transactions, payments, and user activities for compliance purposes.

---

## Support and Resources

### Documentation Resources
- **API Documentation**: https://banking.dev.aritma.io/api/
- **Technical Documentation**: Available in the application folder
- **Business Central Help**: Microsoft's official Business Central documentation

### Support Contacts
- **Aritma Support**: https://www.aritma.com
- **Technical Support**: https://www.cepheo.com
- **Emergency Support**: Contact your system administrator

### Legal and Compliance
- **Privacy Policy**: https://www.aritma.com/privacy
- **Terms of Use**: https://www.aritma.com/legal
- **GDPR Compliance**: Fully compliant with data protection regulations

---

*This user guide is for Aritma Finance Manager version 1.0.0.4. For the most current information, please refer to the official documentation or contact support.*
