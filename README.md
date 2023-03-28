# fraud-detection-in-transactions-with-SQL
Identifying high-risk transactions in dummy data using ip addresses, postal code and email
Fraud detection scenario: credit card processors alert a finance team to possible fraudulent transactions. Using SQL, the transaction_data is analysed to identify potentially risk transactions and stop them before they are fully processed.


-- Looking at the transaction_data table
SELECT *
FROM transaction_data
LIMIT 10;


-- The column names are: 
id
full_name
email
zip
ip_address 


-- Looking up the full record of a flagged user 
SELECT full_name, email, zip
FROM transaction_data
WHERE zip = 20252;
-- This results in 7 records in the area 

 
-- Names and emails associated with these transactions.
SELECT full_name, email
FROM transaction_data
WHERE full_name = 'Art Vandelay'
   OR full_name LIKE '% der %';
   

-- The IP addresses where some of the transactions are originating from are irregular. IP addresses starting with 10 are for internal use, and therefore shouldn't be accessing these financial services.
SELECT ip_address, email
FROM transaction_data
WHERE ip_address LIKE '10.%';


-- Some users may be making fraudulent transactions using a temporary email address service that self-destructs after use. By identifying these, fraudulent acctors can stopped.
SELECT *
FROM transaction_data
WHERE email LIKE '%temp_email.com';


-- Identifying a specific transaction that occured based on an ipdress starting with '120' and name starting with 'John'
SELECT *
FROM transaction_data
WHERE full_name LIKE 'John%'
  AND ip_address LIKE '120.%';
  












