# fraud-detection-in-transactions-with-SQL
Identifying high-risk transactions in dummy data using ip addresses, postal code and email
Fraud detection scenario: credit card processors alert a finance team to possible fraudulent transactions. Using SQL, the transaction_data is analysed to identify potentially risk transactions and stop them before they are fully processed.

-- Looking at the transaction_data table
SELECT *
FROM transaction_data
LIMIT 10;

/* The column names are: 
id
full_name
email
zip
ip_address 
*/

/* Looking up the full record of a flagged user */

