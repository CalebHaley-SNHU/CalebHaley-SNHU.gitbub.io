# Welcome to Caleb Haley's GitHub Page

## Professional Self-Assessment

When I started at SNHU, I did not have any real experience with software development, I had tried to teach myself C++ but ultimately, I did not have good luck.  After failing a few certification exams, I decided I would go back to school for the subject, and I am happy that I did.  Throughout my time in school, I have more than just how to code, I have learned how to develop software.  As time has gone on, I have found a new passion in robotics and AI, fields that I never even considered going into.  Since graduating, I still continue to learn new skills as a developer, currently I am working on my C#.NET skillset which is proving successful in pushing out working applications.

I grew up as a computer nerd, anything that was computer related I was interested in.  It took me some time to find my path to software development, my first degree was in Criminal Justice, and this is where my software fascination began.  In my time in the Criminal Justice program, we learned about software that could predict where the next crimes were most likely to occur, using past crime data to make predictions.  I thought this concept was impossible at the time, but having learned a little bit about software development, I know now that it just takes a little data, math, and the right developer.  

I originally had trouble thinking of projects to use to help hone my abilities and skills in software development, so I went back through applications that I had made in school and re-wrote them in other languages and repurposed some.  Once I started approaching regular problems different and asking myself how a program could make the problem less burdensome, I found that I have too many project ideas.  A program I am currently working on is a simple Java swing frame program that can be used to take the current lumber price per thousand and reprice a user's current stock of product.  I currently work in the lumber industry and calculating this takes me about an hour or two per week of redundant math, just sitting with a calculator converting board feet to lineal feet.  Why not let the computer do the computing? 

Some languages that I am confident and comfortable with are: Java, Python.

Some languages I have limited experience with are: C#, C++, MySQL, .NET, HTML, CSS 


**Briefly describe the program. What is it? When was it created?**

The original program was created in IT-145 and it was a Zoo Monitoring System which was written in Java.  The program would output a menu for the user to select an option on what they wanted to monitor, and the program would read a text file and give the data to the user.  I decided to re-write the program in Python and read JSON files.  I had a JSON file containing some pellet data from work that I repurposed for the program.  This program now outputs a menu for the user to select an option on what they want to monitor, and the program reads a JSON file and gives the data to the user.  The major differences are that rather than spitting out whatever is in the text file, this program finds the data the user is looking for all from within one file.


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
        
        
        # While the user does not want to quit...
        while (userInput != 3) {
           
	   # Print Menu
            System.out.println("Do you want to monitor an animal, habitat, or exit?");
            System.out.println("1. Animal ");
            System.out.println("2. Habitat");
            System.out.println("3. Exit");
            System.out.print("Enter your selection: ");
            userInput = scnr.nextInt();
            System.out.println();

	    # Monitor Animal
            if(userInput == 1){
	    	# Open the animals file
                zooFile= new FileInputStream("animals.txt");
                animalDetails = new Scanner(zooFile);
                System.out.println("Which animal would you like to monitor?");
                i = 0;
		# Keep reading until there is no more
                while (animalDetails.hasNextLine()){
                    animalLine = animalDetails.nextLine(); 
		    
		    # If we find details, display them
                    if(animalLine.contains("Details")){
                        i++;
                        System.out.println(i + ". " + animalLine);
                    }
                }
		# Close the file
                zooFile.close();
                
		# Get user inputs
                System.out.print("Enter your selection: ");
                detailsInput = scnr.nextInt();
                System.out.println();
		#Open animals file
                zooFile= new FileInputStream("animals.txt");
                animalSubDetails = new Scanner(zooFile);
                i = 0;
                while (animalSubDetails.hasNextLine()){
                    animalLine = animalSubDetails.nextLine(); 
                    if(animalLine.contains("Animal")){
                        i++;
                    }
		    
		    # If we get an urgent message, let the user know
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
			# No warning, keep going
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
            
	    # Habitats Selection
            else if(userInput == 2){
	   	# Open file
                zooFile= new FileInputStream("habitats.txt");
                habitatDetails = new Scanner(zooFile);
                System.out.println("Which habitat would you like to monitor?");
                i = 0;
		# Keep reading the next lines until there are no more
                while (habitatDetails.hasNextLine()){
                    habitatLine = habitatDetails.nextLine(); 
                    if(habitatLine.contains("Details")){
                        i++;
                        System.out.println(i + ". " + habitatLine);
                    }
                    
                }
		# Close flie
                zooFile.close();
		
		# Get input
                System.out.print("Enter your selection: ");
                detailsInput = scnr.nextInt();
                System.out.println();
		# Open file 
                zooFile= new FileInputStream("habitats.txt");
                habitatSubDetails = new Scanner(zooFile);
                i = 0;
                while (habitatSubDetails.hasNextLine()){
                    habitatLine = habitatSubDetails.nextLine(); 
                    if(habitatLine.contains("Habitat")){
                        i++;
                    }
		    
		    # Alert user on warnings
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

**Briefly describe the program. What is it? When was it created?**


The original program was created in IT-145 and it was a system that would ask the user how many apples and oranges they had, and how many they are required to have, then calculate the difference.  I wanted to make the program easier to use for the end-user so I put data into a hash table which contained previous years sales, then the program would ask the user what they would want to calculate and prompt the user for how many of an item they have, then get the last year’s sales data and compare the two numbers.


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


