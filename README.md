# CS5004 Project 6

#### Overview:

1. We are seeking to replace the data record with computer records where we can keep track of individual animals that are in care. As the sanctuary staff, we have to build the MVC model that provide us the view of the sanctuary, so that we can register new monkey, move the monkey from isolation to enclosure and can be able to view the monkeys' information in enclosure and sanctuary.

#### Feature:

Below is the feature of the program:
1. Register the monkey by inputting the monkey's Name, Species, Sex, Size, Weight, Age and its favourite food. Not require to input the healthiness of the monkey as it is defaulted to be unhealthy. 
2. The new monkey being registered would be put in isolation with its picture and the name shown. 
3. For the monkey living in the isloation, its name would be shown in the combobox. It allows us to select the monkey to be moved to enclosure. 
3. Able to move the selected monkey to the enclosure. Once the monkey is moved to enclosure, the monkey would be taken away from the isolation and moved to be shown in the row (enclosure for specific species) according to its species.
4. Able to select the list of every enclosure by choosing the specific species.
5. Able to list out the names of the monkeys living in sanctuary in alphabetical order.

#### How to run:

Put the jar file to the desktop and click it. No specific argument required to run the jar file 

#### How to use the program:

When open the program, the view of the program named "Primates" will be shown

1.The first row is the monkey's input. Below is the regulation of inputting the attribute
a.Name: Please input the valid name of monkey. Empty name or the name including non alphabets are not allowed
b.Species: Please strictly follow the predefined species as below to input, All letters must be in capital.
DRILL
GUEREZA
HOWLER
MANGABEY
SAKI
SPIDER
SQUIRREL
TAMARIN
c.Sex: Please strictly follow the predefined Sex as below to input, All letters must be in capital.
M
F
d.Size: Please input a valid numeric value. The value has to be greater than zero.
e.Weight: Please input a valid numeric value. The value has to be greater than zero.
f.Age: Please input a valid numeric value. The value has to be greater than zero.
g. Food: Please strictly follow the predefined Food as below to input, All letters must be in capital.
EGGS
FRUITS
INSECTS
LEAVES
NUTS
SEEDS
TREESAP
Below is one of the example to input all the valid attributes of the monkey:
Name: Abu 
Species: DRILL
Sex: M
Size: 12.4
Weight: 8.345
Age: 16.2342
Food: EGGS

2. The second row has two buttons and one combobox in between. The first button named "Register Monkey", it allows us to put the monkey to the isolation box once all the valid attibutes of monkey are input. After you clicked the button "Register Monkey", the monkey with picture and its name would be shown in the isolation box. The combobox in between the buttons allow us to select the monkey that is in the isolation. Once the monkey is selected, then we can click the button next to it, which is named "Move to Enclosure", it allows us to move the monkey from the isolation to the speceifc row of the enclosure for species (the monkey will be automatically moved to correct row according to the monkey's species)
3. The third row has one combobox and two buttons. The combox box has the options of eight species. We can select the species and click the button next to it, which named "Specific Enclosure List" to get the list of the monkeys in the specific enclosures that we chose. The list of the monkeys contain the monkey's name, sex and its favourite food. If multiple monkeys are in the enclosure we chose, the monkeys would be sorted in alphabetical order of their name. The last button in the third row is named "Sanctuary List", it allows us to get the list of the names of the monkeys that in the sanctuary. The name list are sorted in alphabetical order.

#### Design/Model Changes:


#### Assumption:
1. Same name of monkey in the sanctuary is not allowed.
2. The monkeys who live in the enclosure would live forever.

#### Limitation:
The is no memoization on the monkeys in the sanctuary. 
It implies if three monkeys are registered and two are moved from isolation to enclosure. 
When the jar file is closed and is reopened, all monkeys record would be disappeared and we need to re-register the monkeys again.

#### Citation:

