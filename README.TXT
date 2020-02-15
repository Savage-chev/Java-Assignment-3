SOFTWARE: BlueJ(IDE)
BOOK: Object First with Java | Sixth Edition | Chapter 5
PROJECT TITLE: Wine Direct
PURPOSE OF PROJECT: University weekly assignment
VERSION or DATE: November 2019
AUTHOR: Plamen Savchev 

ASSIGNMENT INSTRUCTIONS:


Individual Assessed Coursework 
November 2019

Scenario:  Wine Direct is an attempt by a cooperative to sell their wine reserves directly to the public. Wine is only sold by the case. People who are interested in buying the wine have to submit their details online and, once accepted, are then given a unique ID which they can later use to log in and then to buy wine.  For the purposes of this assessment, you may assume that only one person can log onto the web site at any one time. 

You are to model this scenario using a BlueJ project following these steps:

Step 1: A simple Browser class
Write a basic Browser class with three private fields, yearOfBirth, email (a String) and iD (which you can assume consists of a unique sequence of digits).  

There are going to be two kinds of browsers: those who already have an ID (and so can purchase the wine straightaway) and those who do not. Hence this class will need two constructors: one for each type of browser. One constructor will be passed three arguments and the other two arguments – the third field needs to be set to a suitable value. 

Now introduce a new field isBuyer, which is set by the constructor, and a method setBuyerStatus(), which is passed a boolean value as an argument.  This method will be used whenever the potential buyer logs into the Wine Direct website.

The class should include suitable accessor & mutator methods. In future steps, you will not necessarily be reminded to include, for example, accessor methods.  You will be expected to provide any necessary accessor methods and write sensible code following the general principles and conventions you have been studying in this module.

Step 2: A simple Website class
a)	Write a simple Website class to represent the web site.  The constructor for the class should be passed the name of the website which is then stored in a field name. A second field hits should record the number of buyers who log in to the website and a third field salesTotal which should record the amount of money taken at checkout. 

There are two types of browsers who access this web site: those who already have their ID i.e. buyers, and those who do not. Part of the web site allows the buyers to simply log in and to then buy a case of wine. Those who do not already have an ID must submit their personal details and, once these have been checked, then they too can buy wine.

b)	Write a method for the class, called buyerLogin(), which allows a buyer to log in to the site. This method is passed a Member object as a parameter and which for the moment simply outputs a welcome message to the terminal window in the format (assuming your chosen site name is Wine Direct): 
Wine Direct welcomes buyer 6732, you are now logged in.

c)	Next, write a method becomeBuyer() which is also passed a parameter that is a pointer to a Browser object. This method then checks that the potential buyer is over the age of 18 and so is able to make a purchase. Of course, in real life more checks would have to be made . You also don't need to worry about checking for an accurate age i.e. you don't need to include months and days in your calculation. Unless you want to that is . 
		
Anyhow, if the potential buyer is indeed old enough then the method sets the buyer's iD field (see paragraph below) and calls the method buyerLogin(). 

To set the browser's iD field, you have a choice: either set it to 999 or, for more marks, set it to a random value. To do the latter, you need to use an object from the Random class as follows. Firstly, write the code import java.util.Random before the class header of Website. Then use the BlueJ Help menu to find out about the Random class and which method from that class it is most appropriate to use here. 

 
Step 3: Add a basic WineCase class and allow a buyer to select a case of wine to buy.

a)	Write a basic WineCase class to represent a case of wine.  A WineCase object has four fields: refNo (a unique sequence of letters and digits), description (e.g. "chablis", "white burgundy" or similar), noOfBottles (in the case) and price (the price of the case in pounds).  The constructor for the class should be passed suitable arguments to initialise these four fields.
b)	Add a selectWineCase() method to the Browser class which allows a browser to choose a case of wine provided that browser is a buyer. This method is passed a WineCase object as a parameter.  You should declare a new field wineCase in the Browser class in order to store the case of wine selected. 
c)	Make the selectWinecase() method print a message to the terminal window about the selection. An example is shown below: 
	  Buyer with ID 6732 has selected wine case with reference number
	  LO786, a case of 2018 Chardonnay from New Zealand of 12 bottles
	  at £120

Step 4: Allow a buyer to pay for the case of wine.
a)	Add a method payForWine() to the Browser class.  This method will simply call a method in the Website class to pay for the wine i.e. to record the transaction with the website. 

And here we have a problem: at the moment the Website object does not record which browser has entered the store and, conversely, the Browser object also keeps no details of  which site it has entered. Let’s deal with that now.

b)	Add another field website to the Browser class.  This field will be used to store a reference (i.e. a pointer) to the website the browser is currently logged into.  Write a mutator method setWebsite().
•	Modify the buyerLogin() method of Website so that after the user is logged into the website, setWebsite() is called with a pointer to that website. 
	Think about what this value could be:
So, setWebsite() needs to be passed, as an argument, a pointer to the Website object that you are currently browsing. This will enable the Browser object to record which website it is logged into.

In fact, the Website object needs to be able to tell the Browser object "point to me". That is, the Website object needs a pointer to itself.

And a pointer that points to the object itself is called a self-referencing pointer and has value this.
Amend your code to do this.

Next, complete payForWine() by adding a call to the method checkout() of the Website class. What parameters do you think checkout() will need? Try working this out for yourself and then to check, read c) below which details the parameters needed.

c)	Add a method checkout() to the Website class which is passed a parameter which is a pointer to a Browser object representing the browser wishing to purchase a case of wine.  The checkout() method should print a message to a terminal window confirming successful completion of the transaction.

d)	It is decided to give a discount of 10% to every 10th buyer who logs into the website -- if they select and pay for a case of wine during this login session then they will receive a 10% discount at checkout. Add a method checkHitDiscount() to the Website class which checks whether a discount is available. Amend your checkout() method to use this new method and, if appropriate, to print a congratulatory message to the screen and, of course, to reduce the cost of the wine(s).

Finally !

Now, you need to think more about you model: re-read the specification and see whether there are any parts that you have not yet fully implemented or how your code can be improved.  Remember your original Account class and the Naïve Ticket Machine project -- how were they improved ?  Around 10% of the marks will be available for any improvements that you make. 

However, do not add functionality which allows multiple cases of wine to be purchased or multiple members to log in to the website – as this is part of the next homework 


Hand in details
•	You will need to submit a hard copy of the source code for this project.  Your Java group number should be written on the front page.  All work should be handed in inside a clear plastic wallet and should be handed in at your workshop on Tuesday 19th November 2019. 

Note that by the act of following these instructions and handing your work in, it is deemed that you have read and understand the rules on plagiarism as written in your student handbook.


