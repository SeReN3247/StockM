Stock management system

Group: 84
Name: LIN, Jiacheng (13124347)
Application link: https://stockmanagement-lwf6.onrender.com

********************************************
# Login
Through the login interface, each user can access the stock management system by entering their username and password.

Each user has a userID and password;
[
	{userid: user1, password: us123},
	{userid: user2, password: us123},
	{adminid: user3, password: us123}

]

After successful login, userid is stored in seesion.

********************************************
# Logout
In the home page, each user can log out their account by clicking logout.

********************************************
# CRUD service
- Create
-	A restaurant document may contain the following attributes with an example: 
	1)	Item Name (M&M Chocolate)
	2)	Item ID (0001), item id must be 4 digits
	3)	Manufacturer (M&M)
	4)	Manufacturer Contact (22544579), telephone number must be 8 digits
	5)	Description (classic M&M chocolate, 70g, small package)

Item Name and Item ID is mandatory, and other attributes are optional.

Create operation is post request, and all information is in body of request.

********************************************
# CRUD service
- Read
- There are two options to read and find all information of item list or searching by item id.

1) List all information
	display.ejs will be displayed with all item ID
	clicking on item ID, the details of the tiem will be shown

2) Searching by item id
	input the id of any item you want to find (0001)
	id is in the body of post request, and in display.ejs item id will be shown as link
	clicking on item ID, the details of the tiem will be displayed

********************************************
# CRUD service
- Update
- The user can update the item information through the details interface.
- Among the attribute shown above, Item ID cannot be changed. Since Item ID is fixed, Item ID is searching criteria for updating information. 

- A item document may contain the following attributes with an example: 
	1)	Item Name (M&M Chocolate (small package))
	2)	Manufacturer (M&M)
	3)	Manufacturer Contact (27931322), telephone number must be 8 digits
	4)	Description (classic M&M chocolate, 70g, small package)	

	In example, I updated the item name and manufacturer contact number.

********************************************
# CRUD service
- Delete
-	The user can delete the item information through the details interface.

********************************************
# Restful
In this project, there are three HTTP request types, post, get and delete.
- Post 
	Post request is used for insert.
	Path URL: /api/item/itemID/:itemID
	Test: curl -X POST -H "Content-Type: application/json" --data '{"name": "Coca Cola", "itemID":"0002"}' localhost:8099/api/item/itemID/0002/name/Coca Cola

- Get
	Get request is used for find.
	Path URL: /api/item/itemID/:itemID
	Test: curl -X GET http://localhost:8099/api/item/itemID/0003

- Delete
	Delete request is used for deletion.
	Path URL: /api/item/itemID/:itemID
	Test: curl -X DELETE localhost:8099/api/item/itemID/0003

Login should be done at first for all restful CRUD services.


curl -X POST -H "Content-Type: application/json" --data '{"name": "Coca Cola", "itemID":"0002"}' http://localhost:8099/api/item/itemID/0002

curl -X GET http://localhost:8099/api/item/itemID/0003

curl -X DELETE http://localhost:8099/api/item/itemID/0003
