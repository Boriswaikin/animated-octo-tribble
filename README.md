# CS5004 Project 6

#### Overview:

1. We are seeking to replace the data record with computer records where we can keep track of individual animals that are in care. As the sanctuary staff, we have to build the MVC model that provide us the view of the sanctuary, so that we can register new monkey, move the monkey from isolation to enclosure and can be able to view the monkeys' information in enclosure and sanctuary.

#### Feature:

Below is the feature of the program:
1. Register the monkey by inputting the monkey's Name, Species, Sex, Size, Weight, Age and its favourite food. Not require to input the healthiness of the monkey as it is defaulted to be unhealthy. 
1.1 Message would be pop out to warn the user if there is invalid input when creating a monkey, for example:
- The monkey's name is empty
- The monkey's name contains non alphabets
- The name of monkey already exist in the isolation or enclosure
- The size input is less than or equal to zero
- The age input is less than or equal to zero
- The weight input is less than or equal to zero
2. The new monkey being registered would be put in isolation with its picture and the name shown. 
2.1 Message would be pop out to warn the user if adding monkey to a full isolation.
3. For the monkey living in the isloation, its name would be shown in the combobox. It allows us to select the monkey to be moved to enclosure. 
4. Able to move the selected monkey to the enclosure. Once the monkey is moved to enclosure, the monkey would be taken away from the isolation and moved to be shown in the row (enclosure for specific species) according to its species.
4.1 Message would be pop out to warn the uset if no monkey is availale to be moved from isolation to enclosure. 
5. Able to select the list of every enclosure by choosing the specific species.
6. Able to list out the names of the monkeys living in sanctuary in alphabetical order.

#### How to run:

1.Put the jar file to the desktop.
2.Right click, choose "Open With", choose "JavaLauncher(default)".
3.If asked are you sure you want to open it, click "Open".

#### How to use the program:

When open the program, the view of the program named "Primates" will be shown

1.The first row is the monkey's input. Below is the regulation of inputting the attribute
a.Name: Please input the valid name of monkey. Empty name or the name including non alphabets are not allowed
b.Select species of the monkey
c.Select sex of the monkey
d.Size: Please input a valid numeric value. The value has to be greater than zero.
e.Weight: Please input a valid numeric value. The value has to be greater than zero.
f.Age: Please input a valid numeric value. The value has to be greater than zero.
g.Select favourite food of the monkey.
Below is one of the example to input all the valid attributes of the monkey:
Name: Abu 
Species: DRILL
Sex: M
Size: 12.4
Weight: 8.345
Age: 16.2342
Food: EGGS

2. The second row has two buttons and one combobox in between. The first button named "Register Monkey", it allows us to put the monkey to the isolation box once all the valid attibutes of monkey are input. After you clicked the button "Register Monkey", the monkey with picture and its name would be shown in the isolation box. The combobox in between the buttons allow us to select the monkey that is in the isolation. Once the monkey is selected, then we can click the button next to it, which is named "Move to Enclosure", it allows us to move the monkey from the isolation to the speceifc row of the enclosure for species (the monkey will be automatically moved to correct row according to the monkey's species)
4. The third row has one combobox and two buttons. The combox box has the options of eight species. We can select the species and click the button next to it, which named "Specific Enclosure List" to get the list of the monkeys in the specific enclosures that we chose. The list of the monkeys contain the monkey's name, sex and its favourite food. If multiple monkeys are in the enclosure we chose, the monkeys would be sorted in alphabetical order of their name. The last button in the third row is named "Sanctuary List", it allows us to get the list of the names of the monkeys that in the sanctuary. The name list are sorted in alphabetical order.

#### Design/Model Changes:
The original design in Sanctuary class:
parameter: -enclosure: EnclosureHabitat, -isolation: IsolationHabitat
method: 
+ getIsolation(): IsolationHabitat
+ getEnclosure(): EnclosureHabitat
+ listAllMonkey(): String


The new design in Sanctuary class:
parameter: -enclosure: EnclosureHabitat, -isolation: IsolationHabitat
method:
+ getIsolation(): IsolationHabitat
+ getEnclosure(): EnclosureHabitat
+ listAllMonkey(): String
+ createMonkey(String,Species,Sex,String,String,String,Food) : Monkey
+ getMonkeyName(Monkey) : String
+ getMonkeySpeciesValue(Monkey) : int
+ setMonkeyHealthiness(Monkey) : void
+ getAllSpecies() : Species[]
+ getAllSex() : Sex[]
+ getAllFood() : Food[]


Explanation of new method created in Sanctuary class:
As the controller is supposed to talk to one model (sanctuary) only. So new methods are created in sanctuary class to for the purpose of calling constructor/method in monkey class:
1. public Monkey createMonkey(String,Species,Sex,String,String,String,Food): to call the constructor in monkey class to create a monkey object
2. public String getMonkeyName(Monkey): to call the getName method in the monkey class by inputting the monkey object as argument. It would return the name of monkey.
3. public int getMonkeySpeciesValue(Monkey)： to call the getSpeciesValue method in the monkey class by inputting the monkey object as argument. It would return the predefined species value (int) of the monkey.
4. public void setMonkeyHealthiness(Monkey): to call the setHealthiness method in the monkey class by inputting the monkey object as argument. It would change the monkey to be healthy and move the monkey from isolation to enclosure.

As the user is able to select the species, sex and favourite food in the comboBox when creating a monkey and be able to select the species of monkey for the enclosure list. Three methods are created in sanctuary class:
5. public Species[] getAllSpecies(): to return an array to store all the monkeys' species
6. public Sex[] getAllSex(): to return an array to store all the monkeys' sex
7. public Food[] getAllFood(): to return an array to store all the monkeys' favourite food


The original design in Monkey class:
parameter: 
-name: String
-species: Species
-sex: Sex
-size: double
-weight: double
-age: double
-food : Food
-Healthiness: boolean
method: 
+ getName(): String
+ getSpecies(): Species
+ getSpeciesValue(): int
+ getSex(): Sex
+ getSize(): double
+ getWeight(): double
+ getAge(): double
+ getFood(): Food
+ getHealthiness(): boolean
+ setHealthiness(Sanctuary): void


The new design in Monkey class:
parameter: 
-name: String
-species: Species
-sex: Sex
-size: double
-weight: double
-age: double
-food : Food
-Healthiness: boolean
method: 
+ getName(): String
+ getSpecies(): Species
+ getSpeciesValue(): int
+ getSex(): Sex
+ getSize(): double
+ getWeight(): double
+ getAge(): double
+ getFood(): Food
+ getHealthiness(): boolean
+ setHealthiness(Sanctuary): void
+ toString(): String

Explanation of a new method created in Sanctuary class:
As comboBox need to display the name of the monkey that in isolation for user to move it to enclosure, so toString() method is created to return the string representation: "Name: monkey's name".


#### Assumption:
1. The monkey is unhealthy at the time when he/she is registered.
2. Same name of monkey in the sanctuary is not allowed.
3. The monkeys living in the enclosure would live forever.

#### Limitation:
1. The is no memoization on the monkeys in the sanctuary. 
It implies if three monkeys are registered and two are moved from isolation to enclosure. 
When the jar file is closed and is reopened, all monkeys record would be disappeared and we need to re-register the monkeys again.
2, In the isolation view and enclosure view, only the monkey's picture and monkey's name is shown. No other attributes of the monkey are provided. 

#### Citation:
[1] Java Swing How to - Add custom Java objects to JComboBox
http://www.java2s.com/Tutorials/Java/Swing_How_to/JComboBox/Add_custom_Java_objects_to_JComboBox.htm (accessed 9 Dec 2022)

[2] How to Use BoxLayout
https://docs.oracle.com/javase/tutorial/uiswing/layout/box.html (accessed 9 Dec 2022)

[3] How to add multiple panels in JFrame in Java
https://www.codespeedy.com/how-to-add-multiple-panels-in-jframe-in-java/ (accessed 9 Dec 2022)

[4] How to resize JLabel ImageIcon?
https://stackoverflow.com/questions/6714045/how-to-resize-jlabel-imageicon (accessed 9 Dec 2022)
