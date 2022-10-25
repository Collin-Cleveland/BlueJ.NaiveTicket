# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

First you need to FORK this repo into your account, then you need to CLONE that foreked repo, the one in your account. 
When you are finished with your code, be sure to ADD/COMMIT and PUSH your code to your repo.

Use the URL from your repo as the submission to the portal. 

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
* Use `getBalance` to check that the machine has a record of the amount inserted.
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.

### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?
	//Checking the machines balance after printing a ticket will always result in zero given the code below:
		// Clear the balance.
        		balance = 0;
	Regardless if there was more money in the account than the actual ticket price, no refund will be granted.

### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
		//The machine does not work how you would expect it to as the ticket will still print and increment even if the price 			isnt met. In addition, any additional balance put into the machine over the ticket price is lost given there are no 			refunds.
	* What happens if you insert too much money into the machine – do you receive any refund?
		//No refund is granted, the balance is always set to zero after printing a ticket.
	* What happens if you do not insert enough and then try to print a ticket?
		//The machine will still print the ticket even if the balance is less than the price of the ticket. Also, the ticket 			increment will continue to increase with every iteration.

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?
		//Even after chaning the price of the ticket the machine still acts as I have explained above, incorrectly (well in terms 			of efficiency).

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.
 //public class Student{...}, public class LabClass{}

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?
	//Yes, the error "class, interface, enum or record expected" populates 30 times within the code when we switch the order of 		public and class. The scope of the following code is confused when we state the data type prior to the word "public" or "private. 		There is a nomenclature heirarchy to be followed when describing objects in Java.

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
		//When we try to input class then public before TicketMachine, Java is expecting us to list the name of the class 			immediatley after the word "class" so when the word thereafter is public (a reserved work by the language) an error 			occurs.
	* What error message do you get when you now press the compile button?
		//"class, interface, enum or record expected"
	* Do you think this message clearly explains what is wrong?
		//At first I was confused, but upon rereading the error a couple times its clear to see that the error is trying to say 		that it is expecting the title of the class to be recorded but 1. public is reserved by the language and cannot be used 		for naming objects and 2. throws off the remaining of the code as TicketMachine is not defined as the class initially.

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.
	//After removing the word "public" and compiling, the code seems to remain clean and still compiles. 

### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.
	//Fields: price, balance, total, ticketNumber
	Constructors: TicketMachine(Integer ticketCost)
	Methods: getPrice(), getTicketNumber(), getBalance(), calculateTotal(), incremementTicketNumber(), printTicket()

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?
	//The first thing I noticed is the construtor also has the same name as the class which makes sense as the 		constructor is is 		stating an instance of the object when we set a ticket price to the machine. 		Secondly, I see that there is no "return" in the 		constuctor as there is in all the other methods. 

### Exercise 2.11
* What do you think is the type of each of the following fields?
	//The type is described by the first word following "private" in the below. So the types repsectively are int, 		Student, Server.
```java
private int count;
private Student representative;
private Server host;
```

### Exercise 2.12
* What are the names of the following fields?
	//The feild in the below are what follows the type. The feild for each repsectively are alice, tutor, game.
```java
private boolean alive;
private Person tutor;
private Game game;
```
### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!
		//Here the exact order matters as there is a specific nomenclature heirarchy that Java requires. In all 		instances where the order is altered, the code does not resolve.

### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.
	//While I previoulsy thought that this was not neccesary in Java but more of a convention among coders, it seems 	to be the case when declaring fields. A tip I will be sure to keep in mind moving forward.


### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.
	//private int status; (almost forgot the semicolon smh)

### Exercise 2.16
* To what class does the following constructor belong?
	//As seen in the TicketMachine example, the constructor belongs to Student as they share the same name.
```
public Student(String name)
```

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
	//The constructo has two parameters seen inside of the parenthesis seperated by a comma. The typs respectively 		are string and double.
```
public Book(String title, double price)
```

### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?
	//Not quite sure as this is quite ambiguous and up to the user. But my best guess would be that the types would 	resemble those of the parameters in the constructor above.
* Can you assume anything about the names of its fields?
	//Again not definitively as this will be up to the user or project. However, I can guess that they could be 		things like title and price as listed in the parameters above but could also include things like genre or length 		in pages.
READ upto and INCLUDING section 2.15 of this chapter.
