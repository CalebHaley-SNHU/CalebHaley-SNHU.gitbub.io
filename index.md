# Welcome to Caleb Haley's GitHub Page

## Professional Self-Assessment

When I started at SNHU, I did not have any real experience with software development, I had tried to teach myself C++ but ultimately, I did not have good luck.  After failing a few certification exams, I decided I would go back to school for the subject, and I am happy that I did.  Throughout my time here, I have learned more than just how to code, I have learned how to develop software.  As time has gone on. I have found a new passion in artificial intelligence, a field that I never even considered going into.  Python is a common language in this field, so I wanted to try to showcase my skills in Python – therefore I re-wrote two of the programs in the language.  I applied data-driven concepts to my programs to showcase my ability to work with data.  AI at its core is all about reading and manipulating data, I wanted to focus a fair amount of effort in doing this.  

Completing this coursework enabled me to showcase some of my strengths along with helping me fine-tune my end goals as a software developer.  I have a passion for artificial intelligence and knowing that I tried to apply skills needed in AI to these programs.  I was able to create data driven applications which is what AI is at its core.  One of the most important skills needed in this field is a strong understanding of data structures and algorithms.  In the first narrative, I take a data file and read that data into variables which allows the program to manipulate the data, this is one of the first steps in an AI system as well.  I wanted to apply skills to these programs that I hope to need when applying for jobs in my field, as I would then have working programs for my ePortfolio.  I know that my previous programs have had pitfalls when it comes to code security, so this time around I worked through the programs using static analysis whenever possible.  This helped show me places where I could have a resource leak or overall improve the performance of the program.  I know this is something that employers will be looking into, so I wanted to showcase my ability to create secure code.  I feel that I also demonstrated my ability in software engineering and databases by breaking down two of the narratives from Java to Python and added functionality like quality-of-life features for the user.

Throughout this course, I have been turning in my code for the narratives at certain milestones where we would receive instructor feedback on the submitted programs.  This works in a similar way that code reviews will work, we have someone else looking at our code and offering us different ways to optimize and polish our programs.  When we get the feedback, we adjust our code and commit the code to our ePortfolio – just like we would do when we finish working on part of a project in the real world, then adding the new code to the working baseline of code.  We have also recorded our own code reviews which was my first code review, with enough practice the result came out well.  If we take a step back and think about the work completed in this course, we have been closely collaborating in a team environment as well as communicating with stakeholders like we would have done in our initial proposals.  

I used my experience in retail to help refine the narratives to be applicable in the real world.  For example, the first narrative reads data from a file and performs operations on the data.  This would allow a retailer to find out how many tons of pellets to order based on ash content, heat rating, and price.  Since these are three major variables in customer sales, we can use them to estimate the sales with a fair amount of accuracy.  The second narrative tells the user how much of a certain item they need to order.  The original program would ask the user for how many items they have and how many they need and perform arithmetic on those items.  Most point-of-sale systems have breakpoints for orders set by managers, if stock gets to a certain point, then more would need to be ordered and the item is flagged.  In the revised program, I took previous years sales data used how many of the item the user has on hand and simply asked the user for how much of the item they have and gave them how many they needed to order.  Lastly, the third narrative dives into aliases or SKUs in the business world.  I created a database that contained abbreviations, those abbreviations could hold product details which we could read into by querying the database.  When someone at a store scans an item, the barcode does not contain the data, but it contains a link to the data.  This is an applicable skill for most point-of-sale development.


## Code Review
A YouTube link of my first personal code review is below, the video was far too large for the GitHub limit and it would need to be broken down into 32 different files.                         
[Link to Code Review](https://youtu.be/mReK4KC2xbs)

## Enhancement 1 Narrative: Software Design and Engineering

**A.	Briefly describe the artifact. What is it? When was it created?**

The original program was created in IT-145 and it was a Zoo Monitoring System which was written in Java.  The program would output a menu for the user to select an option on what they wanted to monitor, and the program would read a text file and give the data to the user.  I decided to re-write the program in Python and read JSON files.  I had a JSON file containing some pellet data from work that I repurposed for the program.  This program now outputs a menu for the user to select an option on what they want to monitor, and the program reads a JSON file and gives the data to the user.  The major differences are that rather than spitting out whatever is in the text file, this program finds the data the user is looking for all from within one file.

**B.	Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in software development? How was the artifact improved?**

I selected this artifact because I thought it would be a good chance to showcase some of the places I have grown.  I wanted to be able to fine tune what data was coming from the file, something that is commonly done in the field.  We do not always want to retrieve entire files, sometimes we just need bits and pieces.  I enjoy working with data and realize I may be drifting that way professionally, so realistically I want a portfolio that will show my ability to work with data – in other narratives I will be able to work with data a little bit more.  Python is one of the languages used commonly with data analysis so I thought it would be fitting to re-write the application in a language that is naturally well-suited for data analysis. 

**C.	Did you meet the course objectives you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?**

I wanted to achieve CS-409-04 which is to demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals.  I took a program that was able to do the task at hand, but in practice it would be rarely seen; and changed it into a program that written in a language recognized by the industry as one of the most widely used data languages and showcased my ability to pull specific data from a file.

**D.	Reflect on the process of enhancing and/or modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?**

The biggest challenge I usually face is biting off more than I can chew.  I always have big, elaborate plans for my programs and at some point, I must realize that I cannot add it all in.  This program was no exception to the rule.  I wanted to add in more data analysis into the program but realized that it was getting overly complex for a user that would just be running a program via command prompt.  Without going back and creating a GUI, some things would just be too hard to do with the user and I found myself losing track of where I was while testing.  I decided to simplify the program to demonstrate the skills that I was aiming for, which I have completed, now I have a working baseline which I can add functions to.  	
This was not something I had done with Python before, I had worked with CSV files in previous courses but had never interacted with a JSON with Python.  This whole program was a learning experience, but it was the learning experience I was aiming for.  I know that Python is used in data science commonly so it would be something that I may need to know in the field.  This program helped engrain some of the practices of using lists and dictionaries in Python for me as well.

### Original Program
``` Java
import java.util.Scanner;
import java.io.FileInputStream;
import java.io.IOException;
public class ZooMonitoringSystem {
    public static void main(String[] args) throws IOException{
      
        Scanner scnr = new Scanner(System.in);

        int userInput = 0;
        Scanner animalDetails = null;
        int detailsInput = 0;
        FileInputStream zooFile = null; 
        String animalLine = "";
        int i = 0;
        Scanner habitatDetails = null;
        String habitatLine = "";
        Scanner animalSubDetails = null;
        Scanner habitatSubDetails = null;
        boolean detailsFound = false;
        
        
        
        while (userInput != 3) {
           
            System.out.println("Do you want to monitor an animal, habitat, or exit?");
            System.out.println("1. Animal ");
            System.out.println("2. Habitat");
            System.out.println("3. Exit");
            System.out.print("Enter your selection: ");
            userInput = scnr.nextInt();
            System.out.println();

            if(userInput == 1){
                zooFile= new FileInputStream("animals.txt");
                animalDetails = new Scanner(zooFile);
                System.out.println("Which animal would you like to monitor?");
                i = 0;
                while (animalDetails.hasNextLine()){
                    animalLine = animalDetails.nextLine(); 
                    if(animalLine.contains("Details")){
                        i++;
                        System.out.println(i + ". " + animalLine);
                    }
                }
                zooFile.close();
                
                System.out.print("Enter your selection: ");
                detailsInput = scnr.nextInt();
                System.out.println();
                zooFile= new FileInputStream("animals.txt");
                animalSubDetails = new Scanner(zooFile);
                i = 0;
                while (animalSubDetails.hasNextLine()){
                    animalLine = animalSubDetails.nextLine(); 
                    if(animalLine.contains("Animal")){
                        i++;
                    }
                    if (i == detailsInput){
                        detailsFound = true;
                        if(animalLine.contains("*****")){
                            String alert = animalLine.substring(5, animalLine.length());
                            int len = alert.length()+12;
                            for (int j = 0; j < len; j++){
                                System.out.print("!");
                            }
                            System.out.println();
                            System.out.println("! WARNING " + alert + " !");
                            for (int j = 0; j < len; j++){
                                System.out.print("!");
                            }
                            System.out.println();
                        }
                        else if(!animalLine.isEmpty()){
                            System.out.println(animalLine);
                        } 
                    }
                    
                }
                if(detailsFound == false){
                    System.out.println("INVALID ENTRY!");
                }                
                zooFile.close();
                System.out.println(); 
            }
            
            else if(userInput == 2){
                zooFile= new FileInputStream("habitats.txt");
                habitatDetails = new Scanner(zooFile);
                System.out.println("Which habitat would you like to monitor?");
                i = 0;
                while (habitatDetails.hasNextLine()){
                    habitatLine = habitatDetails.nextLine(); 
                    if(habitatLine.contains("Details")){
                        i++;
                        System.out.println(i + ". " + habitatLine);
                    }
                    
                }
                zooFile.close();
                System.out.print("Enter your selection: ");
                detailsInput = scnr.nextInt();
                System.out.println();
                zooFile= new FileInputStream("habitats.txt");
                habitatSubDetails = new Scanner(zooFile);
                i = 0;
                while (habitatSubDetails.hasNextLine()){
                    habitatLine = habitatSubDetails.nextLine(); 
                    if(habitatLine.contains("Habitat")){
                        i++;
                    }
                    if (i == detailsInput){
                        detailsFound = true;
                        if(habitatLine.contains("*****")){
                            String alert = habitatLine.substring(5, habitatLine.length());
                            int len = alert.length()+12;
                            for (int j = 0; j < len; j++){
                                System.out.print("!");
                            }
                            System.out.println();
                            System.out.println("! WARNING " + alert + " !");
                            for (int j = 0; j < len; j++){
                                System.out.print("!");
                            }
                            System.out.println();
                        }
                        else if(!habitatLine.isEmpty()){
                            System.out.println(habitatLine);
                        } 
                    }                    
                }
                if(detailsFound == false){
                    System.out.println("INVALID ENTRY!");
                }                  
                zooFile.close();
                System.out.println();
            } 
            else if (userInput == 3){
                break;
            }
            else{
               System.out.println("INVALID ENTRY!");
               System.out.println();
            }
        }
        return;
    }
    
}
```
### Updated Program
``` Python
# Caleb Haley
# CS 499 Capstone
# Southern New Hampshire University
# pelletReader.py

# This program will read data from a JSON file and output the data for the user to see
# The user will be able to select what kind of data they will see from the JSON file using a menu

# import json dependency
import json

# Open the data in file to be read
with open("pellet.json", "r") as string:
    data = json.load(string)
    string.close()


# Defines function to print BTU data
def btu_list(my_dict):
    # Iterate through dictionary if there are still key, value pairs remaining
    for k, v in my_dict.items():
        if isinstance(v, dict):

            print(k + ":")
            btu_list(v)
            continue
        # Finds the brand in JSON file and outputs BTU data
        print("BTU stands for British Temperature Unit - meaning how hot the pellets get")
        print("New England BTU:", str(v[0]['New England'][0]['BTU']))
        print("Okanagan BTU:", str(v[0]['Okanagan'][0]['BTU']))
        print("Maine BTU:", str(v[0]['Maine'][0]['BTU']))
        print("Turman BTU:", str(v[0]['Turman'][0]['BTU']))
        print("Geneva BTU:", str(v[0]['Geneva'][0]['BTU']))
        print("North Idaho BTU:", str(v[0]['North Idaho'][0]['BTU']))
        print("Energex BTU:", str(v[0]['Energex'][0]['BTU']))


# Defines function to print price data
def price_list(my_dict):
    # Iterates as long as key,value pairs are remaining
    for k, v in my_dict.items():
        if isinstance(v, dict):
            print(k + ":")
            price_list(v)
            continue

        print("Price per ton in USD")
        # Finds the brand in JSON and outputs price data
        print("New England price:", str(v[0]['New England'][0]['Price']))
        print("Okanagan price:", str(v[0]['Okanagan'][0]['Price']))
        print("Maine price:", str(v[0]['Maine'][0]['Price']))
        print("Turman price:", str(v[0]['Turman'][0]['Price']))
        print("Geneva price:", str(v[0]['Geneva'][0]['Price']))
        print("North Idaho price:", str(v[0]['North Idaho'][0]['Price']))
        print("Energex price:", str(v[0]['Energex'][0]['Price']))


# Function definition for user menu
def greeting():
    print("Welcome to the Wood Pellet Terminal")
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    print("        Select an option:       ")
    print("1. View Brands")
    print("2. Pellet Pricing in USD")
    print("3. Find Heat content in BTU ")
    print("4. Quit")
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")


# Bool to easy end program if user chooses
programRunning = True

while programRunning:

    # Calls our greeting function that gives user options
    greeting();
    user_choice = input("Select your option\n")
    i = 0

# Test for user input
    # If user inputs 1, show brands
    if user_choice == "1":
        print("Showing Brands...")
        # Iterates JSON by the first index which is where brand is stored
        brand = [print(i) for i in data['brands'][0]]

    # If user inputs 2, show prices
    elif user_choice == "2":
        print("Printing Price List...")
        # Call the price_list function to print data
        price_list(data)

    # If user inputs 3, show BTU (British Temperature Units)
    elif user_choice == "3":
        print("Printing BTU List...")
        # Call the btu_list function to print data
        btu_list(data)

    # If user chooses 4, the program will stop running
    elif user_choice == "4":
        print("Goodbye")
        # Set our bool to false to close the program
        programRunning = False

    # If the user inputs anything else, it is invalid
    else:
        print("Invalid Input")

```

## Enhancement 2 Narrative: Algorithms and Data Structure

**A.	Briefly describe the artifact. What is it? When was it created?**

The original program was created in IT-145 and it was a system that would ask the user how many apples and oranges they had, and how many they are required to have, then calculate the difference.  I wanted to make the program easier to use for the end-user so I put data into a hash table which contained previous years sales, then the program would ask the user what they would want to calculate and prompt the user for how many of an item they have, then get the last year’s sales data and compare the two numbers.

**B.	Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in software development? How was the artifact improved?**

I selected this artifact because the original was extremely simple and clumsy on the user.  I wanted to show how I can accomplish the same task in different ways with varying levels of program depth.  The initial program was a brute force calculating app, and I was able to turn it into something a little more elegant for the user.  This artifact shows my ability to work with different data structures like hash tables and manipulate the data into solving a problem.  This should demonstrate my ability to design and evaluate computing solutions that solve a given problem using algorithmic principles and computer science practices and standards appropriate to its solution, while managing trade-offs involved in design choices (CS-499-03).

**C.	Did you meet the course objectives you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?**

I wanted to achieve the main course objective mainly, however there was a minor goal I was aiming for in this program that I did fall short on.  Initially, I wanted to re-write the program to read data from a text file, this would be the data containing the previous years’ sales data.  Unfortunately, I was unable to pull that off while still receiving accurate results, for some reason it would keep reading December data every few tests.  Instead, I implemented a hash table which shows my ability to work with different data structures, as I had initially aimed this artifact more towards the algorithm side of the narrative.  

**D.	Reflect on the process of enhancing and/or modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?**

In previous courses, I have been introduced to the concepts of certain data structures, but I have never had to implement them on a system of my own or work with them outside of a structured assignment.  I was not familiar with hash tables but after doing research it became clear that using one would be my best chance at this program.  It gave me the ability to cast user input into a variable that I could use to search the dictionary and return the value to the program.  One thing I learned is an appreciation for the Java documentation, I was able to look through documentation at different data structures to find the one that would fit my use in this scenario.  It worked perfectly.  Once I finally broke down and started using the documentation, the program started coming together much better than it was before.  I struggled with this program for a week longer than I initially planned, but I think I was able to take a lot from this narrative.  


### Original Program
``` Java
import java.util.Scanner;

public class StockFruit {
	public static void main(String[] args) {
		// Variable Declarations
		int applesOnHand; // apples currently on hand
		int applesRequired; // apples required to stock
		int orangesOnHand; // oranges currently on hand
		int orangesRequired; // oranges required to stock
		int applesToOrder = 0; // apples to order
		int orangesToOrder = 0; // oranges to order

		Scanner scnr = new Scanner(System.in);

		// input apples on hand
		System.out.println("How many apples are on hand?");
		applesOnHand = scnr.nextInt();

		// input apples that should be in stock
		System.out.println("How many apples should be in stock?");
		applesRequired = scnr.nextInt();

		// input oranges on hand
		System.out.println("How many oranges are on hand?");
		orangesOnHand = scnr.nextInt();

		// input oranges that should be in stock
		System.out.println("How many oranges should be in stock?");
		orangesRequired = scnr.nextInt();

		// determine number of apples needed to order
		if (applesOnHand < applesRequired)
			applesToOrder = applesRequired - applesOnHand;

		// determine number of oranges needed to order
		if (orangesOnHand < orangesRequired)
			orangesToOrder = orangesRequired - orangesOnHand;
		
		// output number of apples that need to be ordered
		if(applesToOrder > 0) {
			System.out.println("Number of apples to order: " + applesToOrder);
		}
		else{
			System.out.println("Number of apples to order: None");
		}
		
		// output number of oranges that need to be ordered
		if(orangesToOrder > 0) {
			System.out.println("Number of oranges to order: " + orangesToOrder);
		}
		else{
			System.out.println("Number of oranges to order: None");
		}
	}
}
```
### Updated Program
``` Java
package StockFruitRevised;

import java.util.Scanner;
import java.util.Dictionary;
import java.util.Enumeration;
import java.util.Hashtable;

public class StockFruitRevised {
	
	// Method definition to print menu of user options
	public static void printMenu() {
		System.out.println("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
		System.out.println("What would you like to do?");
		System.out.println("1. See monthly sales data");
		System.out.println("2. Calculate Apples needed to order");
		System.out.println("3. Calculate Oranges needed to order");
		System.out.println("4. Quit");
		System.out.println("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
	}
	

	// Main function
	public static void main(String[] args) {
		printMenu();
		// Initialize a dictionary to hold apple sales data
				Dictionary<String,Integer> appleSales = new Hashtable<String, Integer>();
				// Input previous sales data into our dictionary
				
				appleSales.put("January", 200);
				appleSales.put("February", 175);
				appleSales.put("March", 150);
				appleSales.put("April", 230);
				appleSales.put("May", 250);
				appleSales.put("June", 300);
				appleSales.put("July", 390);
				appleSales.put("August", 350);
				appleSales.put("September", 200);
				appleSales.put("October", 250);
				appleSales.put("November", 235);
				appleSales.put("December", 190);
				
				// Initialize a dictionary to hold orange sales data
				Dictionary<String,Integer> orangeSales = new Hashtable<>();
				// Input previous sales data into our dictionary
				orangeSales.put("January", 200);
				orangeSales.put("February", 200);
				orangeSales.put("March", 200);
				orangeSales.put("April", 230);
				orangeSales.put("May", 250);
				orangeSales.put("June", 230);
				orangeSales.put("July", 215);
				orangeSales.put("August", 200);
				orangeSales.put("September", 200);
				orangeSales.put("October", 200);
				orangeSales.put("November", 235);
				orangeSales.put("December", 190);
			
		
		// Variable Declarations
		
		boolean programRunning = true;

		Scanner scnr = new Scanner(System.in);
		int userInput = scnr.nextInt(); // Holds user choice
		
		if (programRunning = true) {
			switch(userInput) {
			case 1:
				System.out.println("Entering Sales History...");
				// Ask the user what data they want to see
				System.out.println("Would you like to see Average Apple sales or Average Orange sales?");
				System.out.println("1. Apples");
				System.out.println("2. Oranges");
		
				int userInput1 = scnr.nextInt();
				switch(userInput1) {
				// Case 1 outputs apple sales
				case 1:
					// Enumerate keys and elements
					Enumeration<String> e = appleSales.keys();
					// Keep running if there are more elements
					while(e.hasMoreElements()) {
						String key = e.nextElement();
						// Output key and element
						System.out.println(key + " - " + appleSales.get(key) + " apples");
					}
					break;
				// Case 2 outputs orange sales
				case 2:
					// Enumerate keys and elements
					Enumeration<String> i = orangeSales.keys();
					// Keep running if there are more elements
					while(i.hasMoreElements()) {
						String key = i.nextElement();
						// Output key and element
						System.out.println(key + " - " + orangeSales.get(key) + " oranges");
					}
					break;
				default:
					// Anything else is invalid
					System.out.println("Invalid Input");
				}
				break;
				
			case 2:	// Apples needed to order
				System.out.println("Please type the month by number (January is 1, February is 2, etc.)");
				int userMonthApple = scnr.nextInt();
				String userMonth = null;
				System.out.println("How many apples are on hand?");
				int userCountApple = scnr.nextInt();
				int applesNeeded = 0;
				switch(userMonthApple) {
				// We assign the user input to a string so we can query the dictionary
				case 1:
					userMonth = "January";
					break;
				case 2:
					userMonth = "February";
					break;
				case 3:
					userMonth = "March";
					break;
				case 4:
					userMonth = "April";
					break;
				case 5:
					userMonth = "May";
					break;
				case 6:
					userMonth = "June";
					break;
				case 7:
					userMonth = "July";
					break;
				case 8:
					userMonth = "August";
					break;
				case 9:
					userMonth = "September";
					break;
				case 10:
					userMonth = "October";
					break;
				case 11:
					userMonth = "November";
					break;
				case 12:
					userMonth = "December";
					break;
				}
				
				applesNeeded = (appleSales.get(userMonth));
				applesNeeded = applesNeeded - userCountApple;
				System.out.println("Oranges needed to order based on last years sales: " + applesNeeded);
		
				break;
				
			case 3:	// Oranges needed to order
				System.out.println("Please type the month by number (January is 1, February is 2, etc.)");
				int userMonthOrange = scnr.nextInt();
				userMonth = null;
				System.out.println("How many oranges are on hand?");
				userCountApple = scnr.nextInt();
				applesNeeded = 0;
				switch(userMonthOrange) {
				case 1:
					userMonth = "January";
					break;
				case 2:
					userMonth = "February";
					break;
				case 3:
					userMonth = "March";
					break;
				case 4:
					userMonth = "April";
					break;
				case 5:
					userMonth = "May";
					break;
				case 6:
					userMonth = "June";
					break;
				case 7:
					userMonth = "July";
					break;
				case 8:
					userMonth = "August";
					break;
				case 9:
					userMonth = "September";
					break;
				case 10:
					userMonth = "October";
					break;
				case 11:
					userMonth = "November";
					break;
				case 12:
					userMonth = "December";
					break;
				}
				
				applesNeeded = (orangeSales.get(userMonth));
				applesNeeded = applesNeeded - userCountApple;
				System.out.println("Oranges needed to order based on last years sales: " + applesNeeded);

				break;
				
			case 4:	// Quit
				// Say Goodbye to the user
				System.out.println("Closing program...");
				System.out.println("Goodbye");
				programRunning = false;
				break;
			default:
				System.out.println("Invalid Input");
			}
			
		}
		else {
				System.out.println("Goodbye");
			}

		scnr.close();
	}		
}
```


