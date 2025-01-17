Directus Medusa Synchronization Project REPORT

Setup Process:

a. Installed PostgreSQL Locally:

I have downloaded PostgresSQL Database setup from the official website and installed PostgreSQL DB at Local system.

I have created a new database for Directus using the following commands

psql -U postgres 

CREATE DATABASE products;

Screenshot is mentioned below of the product table where I have added the 4 products as mentioned below and showcase the table content with below commands

Select * from products;




	b. Installed and Set Up Directus:
First, I installed Directus globally via npm on the local Machine using below command

npm install -g directus

Then, I created a new Directus project in the nodejs using below command:

directus init products

To run Directus, I have used :

directus start

Once Directus is created and started I have moved to the next step to create a product collection at url : http:/localhost:8055

	c. Created a Product Collection in Directus:
I have logged into Directus and created a new collection called products, with fields as mentioned in the below screenshot :
Product name
Description
Price
Images



I added some sample products with all the required details to test CRUD operations.




	d. Install and Set Up Medusa
For Medusa, I installed the CLI globally:
npm install -g @medusajs/medusa-cli

I have created a new Medusa store with below command:
npx create-medusa-app@latest my-medusa-store

Medusa was now up and running at http://localhost:9000/app


I logged into the Medusa admin panel at http://localhost:9000/app/products and added a few sample products manually to check the sync.

ADMIN –


Store Front –
Url : http://localhost:8000/dk/store



 2. Scripts and Commands: 
I created a script to synchronize product data between Directus and Medusa. The script is supposed to fetch products from Directus and then send them to Medusa to create new products.
The basic flow of the script is:
Fetch Products: Get product data from Directus.
Send to Medusa: Send the fetched data to Medusa to create new products.
However, the script isn't working as expected because of an issue with Directus. Directus doesn't recognize my local URL when trying to trigger the synchronization. The webhook for triggering the sync is not firing because it doesn't accept localhost URLs.


As a result, the products are not being created in Medusa. I am unable to synchronize product data between the two platforms due to this issue.
3. Known Issues and Troubleshooting:
Script Functionality:
Created a script to sync product data between Directus and Medusa.
The script fetches product data from Directus and sends it to Medusa to create products.(Getting Error as mentioned below)
Issue:
The Directus webhook is not recognizing the localhost URL being used.
This prevents data from being sent to Medusa, stopping the sync process.

Challenges:
First time using Directus and Medusa, so knowledge of these tools is limited.
Struggled to understand their working and connection setup.
Directus webhook is not functioning correctly with the localhost URL.
The webhook fails to send data to Medusa, blocking the synchronization process.

Result:
Sync is not working as expected.
Products are not being created in Medusa due to the Directus webhook issue.
Efforts:
Spent significant time troubleshooting and attempting to resolve the problem.
Unable to fix the issue despite repeated efforts.
