![Disclaimer:](https://networks.imdea.org/wp-content/uploads/2021/09/media-file-code-900x500.png "I do not own this picture.")
# Christian Alameda's Portfolio

Hello, my name is Christian Alameda! I am a Computer Science student who is looking for a position that will ensure healthy growth and refinement of my current skills while also expanding my knowledge and abilities in a challenging and friendly work environment.

## Degrees & Certificates
- Bachelor of Science Degree in Computer Science, (Expected Completion 2024)
- Associate of Science Degree in Computer Science, 2022
- Associate of Arts Degree in General Studies with Emphasis in Language and Rationality, 2022

## Contact Details
- Phone: (209) 496-5686
- Preferred Email: [cdalamed@gmail.com](cdalamed@gmail.com)
- Stanislaus State University Email:  [calameda@csustan.edu](calameda@csustan.edu)
- MJC Student Email: [christian956514@my.yosemite.edu](christian956514@my.yosemite.edu)
- GitHub: [https://github.com/ChristianAlameda](https://github.com/ChristianAlameda)
- LinkedIn: [https://www.linkedin.com/in/christian-alameda-a76039253/](https://www.linkedin.com/in/christian-alameda-a76039253/)

### Programming Langauges that I'm Comfortable with:
- Python
- C++
- R
- SQL
- MongoDB

### Operating Systems and Software that I'm Comfortable with:
- Windows 10
- Raspberry Pi
- Linux
    - Bash Shell programming
- Microsoft Office Suite of Applications
    - i.e. Word, Excel, Powerpoint
- Visual Studio
- Git
- PuTTY
- VMWare
- Adobe Photoshop Elements

### A Quicklook
Made a quick calculator game in C++ 
``` C++
#include <iostream>
#include <vector>
using namespace std;
int main() {
    vector<int> numOfOveralls;
    float taxxedNumber;
    int b;
    cout << "Enter how many overalls you want: " << endl;
    cin >> b;
    int overallPrice;
    for (int i = 0; i < b; i++) {
        cout << "Enter overall: " << i + 80 << "'s price: ";
        cin >> overallPrice;
        numOfOveralls.push_back(overallPrice);

    }
    cout<< "--------------------------------------"<<endl;
    for (int i = 0; i < numOfOveralls.size(); i++)
    {
        cout << "Overall: " << 80 + i << " : " << numOfOveralls[i] << endl;
        taxxedNumber = numOfOveralls[i] * .90;// will be the tax on the item
        cout << "Overall: " << (80 + i) << "'s price after tax: " << taxxedNumber << endl;
        cout<< "----------------------------------"<<endl;
    }
    cout << "All done!";
    return 0;
}
```
Developed a menu creation website that allowed restaurants to create and edit their menus so that they can print them all out and have them the way the want. I was partnered with two other partners for this project, Yahir and Yumong. They were both tremendous partners and I'm lucky to have them as good friends and colleagues.
```python
import csv
from entry import Entry
from menuabstract import * #inheriting abstractmethods

#This class will contain all of our functions that have to do with the inventory
class Menu(menuAbstract):
    #Yumong 5-27
    #Making a list for the menu
    def __init__(self):
        self.__list_meal = []
      
    def search_meal(self,meal):  #Returns other values in accordance with meal name
        #__list_meal is dependent on create inventory, since we are only putting in one line with the
        #
        for i in self.__list_meal:
            if i.get_meal() == meal:
                return i
        return None

    # This is a search function that returns a list of
    # entries with the same type
    # take the type, compare the type of every entry to the given type
    def search_type(self, type):
        a = []
        for i in self.__list_meal:
            if i.get_type() == type:
               a.append(i)
        return a

    #yahir 29 - 45
    def print_menu(self):  #prints the menu in its entirety
        print(
            "       [Meals], [Calories], [Ingredients], [Food Types], [Prices]"
        )
        for i in range(len(self.__list_meal)):
            print("Meal " + str(i + 1) + ": " + str(self.__list_meal[i]))

    def add_menu(self, restaurant, new_item):  #will add onto the menu, may have to add onto list and append that into the file
        self.__list_meal.append(new_item)  #appends the user input to the end of the list

    def remove_menu(self, restaurant, meal):  #will delete all items that make up the meal inputted by the user
      search = self.search_meal(meal)  # running meal into search_meal and putting that variable into another variable
      if search == None:
          return self.not_found()
      else:
          self.__list_meal.remove(search)
          
    def write_back(self, restaurant): # writing back list to file
      with open(restaurant, "w") as csvfile:
          csvwriter = csv.writer(csvfile)
          for meal in self.__list_meal:
            meal_list = [meal.get_meal(), str(meal.get_calories()), meal.get_ingredients(), meal.get_type(), str(float(meal.get_price()))]
            csvwriter.writerow(meal_list)
            
    # Yumong Lee 47-54
    # Allows the user to choose from a row and edits that whole row

    def edit_inventory(self, meal, calories, ingredients, type, price):
      shop = self.search_meal(meal)
      if shop ==None:
        return None
      shop.set_calories(calories)
      shop.set_ingredients(ingredients)
      shop.set_type(type)
      shop.set_price(price)
      return shop

    def create_inventory(self, restaurant): 
      #read in the file
        with open(restaurant, "r") as csvfile:
            csvreader = csv.reader(csvfile)
            for line in csvreader:
              #make an object that will be able to distinguish between the items in the row
                entry = Entry(
              )  # Sets the Meal, Calories, Ingridients, Type, and Price
                entry.set_meal(line[0])
                entry.set_calories(int(line[1]))
                entry.set_ingredients(line[2])
                entry.set_type(line[3])
                entry.set_price(int(float(line[4])))
#we want to entry to be our linked list now instead of our list
                self.__list_meal.append(entry)  # Appends the menu

    # I believe I need to make a new function which reads restaurant but will simply take all the lines
    # I disliked repeating myself over and over again
    def give_options(self):
        print()
        print("[0] - Exit Program")
        print("[1] - Search")
        print("[2] - Print Menu")
        print("[3] - Add to the Menu")
        print("[4] - Remove from the Menu")
        print("[5] - Edit Menu")
      
      
  # make a function that prints for when user typed something in wrong or its not in our system
    def not_found(self):
        print("The inputed value was either not in our system or mispelled. Please try again.")

```
For more information on this above project you can visit the github repository for the C++: [here](https://github.com/ChristianAlameda/Madden23PriceGager). For the python: [here](https://github.com/ChristianAlameda/Menu-Creation). 
Again, other Projects and their repositories can be found [here](https://github.com/ChristianAlameda?tab=repositories).