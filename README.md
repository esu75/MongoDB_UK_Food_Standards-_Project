
mongoDB_UK_Food_Standards-_Project
--------------------------
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. The main goal of analyzing this data is 
 to evaluate some of the ratings data in order to help  the editors of a food magazine, Eat Safe, Love, journalists and food critics decide where to focus future articles.
 
 The analysis has been perforemd using NoSQL (PyMongo)
 
 step 1: Import dependencies (required libraries)- PyMongo library
 step 2: json Data was imported to jupyter Notebook from MongoDB Shell (terminal) using MongoDB command:
 mongoimport --type json -d uk_food1 -c establishments --drop --jsonArray establishments.json
 step 3: Create an instance of the Mongo Client.
 step 4: Confirmed appropirate collections and documents are uploaded to the jupyter Notebook
 
Update the Database
-------------------
The magazine editors have some requested modifications for the database before  performing any queries or analysis for them.
A request to add another Restaurant/Cafe/Canteen to the data

step 5: 
Inserted the new Restaurant/Cafe/Canteen in to the existing json data
step 6:created a query to search for the  BusinessTypeId and the new Restaurant/Cafe/Canteen ID was updated  
## Additional requirement:
The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority.
Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
step 7:Created a query to search for any establishments in Dover and deleted

step 8:updated all the latitude and longitude datatype to decimal

Exploratory Analysis
---------------------------
Eat Safe, Love has specific questions they want  to be answered, which will help them find the locations they wish to visit and avoid.

step 9: Determine which establishments have a hygiene score equal to 20?
Atotal of 41 establishements were found in the dataset

![image](https://user-images.githubusercontent.com/118146659/227392554-f72f3b3b-5fec-4b23-aabd-8fee02f13128.png)

step 10:Determine which establishments in London have a `RatingValue` greater than or equal to 4?
Atotal of 34 establishments were found

step 11: convert the result to pandas DataFrame:

![image](https://user-images.githubusercontent.com/118146659/227393057-651af254-202a-49e2-80ad-e6bc89ffae94.png)

step 12:Determine top 5 establishments with a `RatingValue` rating value of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
Searched with a query within 0.01 degree on either side of the latitude and longitude and the json data was converted to pandas DataFrame:

![image](https://user-images.githubusercontent.com/118146659/227599336-1fe044d2-9838-4f02-965e-8d144e289195.png)

step 13: Determine the number of  establishments in each Local Authority area having a hygiene score of 0?

A pipeline was created using match, group by and sort queries and 55 establishments were found. The result is converted to pandas DataFrame:


![image](https://user-images.githubusercontent.com/118146659/227600050-8090c955-4057-43bf-8abf-f5175f38ece0.png)






 
 
 
 
