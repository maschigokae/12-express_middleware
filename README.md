## Hello and welcome to my Electric Vehicle API.

In the last decade, Electric vehicles have exploded in popularity with the advent of new battery technologies and practical vehicles hitting the market, from flashy luxury models like Tesla's Model S, to affordable commuter/family models like Nissan's Leaf. As technology improves and better, more affordable models hit the market, Electric vehicles have the potential to make a serious dent in pollution from automotive transportation. This is especially true in markets with relatively green power grids.

For this API, we define "Electric Vehicles" more technically and specifically as "Battery-Electric Vehicles," or BEVs. Only vehicles that are powered exclusively by electricity from a battery are included. This designation excludes plug-in-hybrid vehicles (like the Chevrolet Volt) and hydrogen fuel cell vehicles.

The API saves and returns entries for individual vehicles as JSON objects. Each vehicle object has 4 properties:
  * vehicle -- Make and Model of Vehicle. Example: "Nissan Leaf". **Must be a string.**
  * info -- Details about vehicle. Example: "practical and affordable hatchback". **Must be a string.**
  * range -- Vehicle's EPA-rated range on a full charge, in miles. **Must be a number.**
  * mpge -- Vehicle's EPA-rated "miles-per-gallon equivalent" (MPGe). **Must be a number.**

The purpose of this API is ultimately to be a resource for consumers interested in Electric Vehicles and green transportation in general, containing the most up-to-date information on Electric Vehicles. Info such as market availability, quick-charging options and standards, and more technical specs will eventually be added (as additional API properties).

## How to use this API

Currently, this API is configured for use in the command line. It is set up to run on port 3000 of your computer's local IP (this IP can be accessed with the identifier `localhost`).

You will need a command line http tool installed. I recommend httpie, and I assume you have it installed for this example.

  * In the command line, making sure you're in the root directory of your local version of the API, start the node server by typing `node server.js`
  * Let's add a sample vehicle to the API. In a **separate** window or pane of your command line interface (your first window is running the node server), making sure you're still in the root directory of your local version of the API, type `http POST localhost:3000/api/bev vehicle="Nissan Leaf" info="108 mile-range on a single charge"`
  * Let's add a second sample vehicle. Type `http POST localhost:3000/api/bev vehicle="Tesla Model S" info="classy, sporty, high-tech luxury sedan" range=300 mpge=95`
  * Let's get the unique id for each vehicle. Each id is a random string of numbers, letter, and dashes autogenerated with node-uuid. type `http localhost:3000/api/bev` This should print an array of ids (for this example there should be two) in the command line.
  * Let's take one of the ids and look up the vehicle information it references. Copy the text of one of the ids. Then in the command line, type `http localhost:3000/api/bev/` (make sure the closing forward-slash is present) and paste the id before submitting the command. You should see an object printed to the command line with the vehicle info.

  Thanks for using my API. Check back soon for updates and improvements!
