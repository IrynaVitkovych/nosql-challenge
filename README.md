# nosql-challenge: Eat Safe, Love
module 12
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. The task was to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

#Part 1: Database and Jupyter Notebook Set Up
In the initial setup, I began by importing the data from establishments.json using the Terminal. I designated the database as uk_food and the collection as establishments. Here's the command I used for importing the data:
`mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json`

After importing the data, I proceeded to set up the necessary environment in the Jupyter Notebook. I imported the PyMongo and Pretty Print libraries, and instantiated a Mongo Client.
To ensure that the data was imported correctly, I verified the existence of the uk_food database and assigned it to a variable. Additionally, I confirmed the presence of the establishments collection within the database and assigned it to another variable for further use.

#Part 2: Update the Database
For the database update process, I first constructed a dictionary containing the details of the new restaurant, Penang Flavours, and utilized the insert_one() method to incorporate it into the establishments collection.

Subsequently, I identified the Business Type ID for Restaurant/Cafe/Canteen and updated Penang Flavours with the corresponding Business Type ID.

Next, I located all establishments in Dover and removed them from the collection.

Initially, there were 994 establishments in Dover. Following the removal process, the count of documents pertaining to Dover was reduced to 0.

Lastly, I utilized the update_many() method to convert latitude and longitude values from strings to decimal numbers within the collection.

#Part 3: Exploratory Analysis

For the exploratory analysis, I addressed the following questions:

1.Hygiene Score of 20: I crafted a query to identify establishments with a hygiene score of 20 and employed count_documents() to ascertain the count of such establishments. The result showed 41 establishments with a hygiene score of 20.
2.London Establishments with Rating Value >= 4: I formulated a query targeting establishments located in London, with a rating value greater than or equal to 4. The query returned 33 such establishments.
3.Top 5 Establishments with Rating Value of 5, Sorted by Hygiene Score, Nearest to Penang Flavours: By setting the latitude and longitude parameters to those of Penang Flavours and defining a search radius of 0.01 degrees, I sorted establishments by their hygiene scores from lowest to highest and limited the result to the top 5 closest to Penang Flavours.
4.Establishments with Hygiene Score of 0 in Each Local Authority Area: I constructed a match query to find establishments with a hygiene score of 0. Subsequently, I utilized a group query to group establishments by Local Authority Area, aggregating the total count of documents within each group. The results were sorted in descending order, displaying the top 10 local authority areas with the highest number of establishments having a hygiene score of 0.

# While working on this module, I used Google, Xpert Learning Assistant, Chat GPT, which helped me build and run the code. For some reason, I can not open NoSQL_setup_starter.ipynb in the repository. It shows, "Sorry, this is too big to display.”,but when I git clone, it's perfectly open and works. Let me know if you need me to copy the whole code and send it as a text file.
