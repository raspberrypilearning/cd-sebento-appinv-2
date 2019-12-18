## Καταγραφή άσκησης

+ Δημιούργησε ένα νέο έργο και δώσε του ένα όνομα, για παράδειγμα `GetFit`.

+ Click on Screen1 under Components and change the Title property to `Track your exercise here!`.

+ Βρες το αντικείμενο TextBox στην περιοχή Palette (κάτω από την ομάδα **User Interface**) και προσθέσέ το στην εφαρμογή, μαζί με ένα αντικείμενο Button.

+ Άλλαξε την ιδιότητα **Text** του Button σε `Εισαγωγή`.

+ Για να τακτοποιήσεις τα αντικείμενα το ένα δίπλα στ' άλλο, σύρε το αντικείμενο **HorizontalArrangement** στην οθόνη (θα το βρείς στην ομάδα **Layout**) και σύρε το TextBox και το Button σε αυτό.

![](images/s3Horizontal.png)

+ Βρες την ιδιότητα **Hint** για το TextBox και πληκτρολόγησε `Λεπτά`. Αυτό θα εμφανιστεί αχνά στο πλαίσιο κειμένου, αν ο χρήστης δεν έχει πληκτρολογήσει τίποτα ακόμα, έτσι ώστε να ξέρει τι να πληκτρολογήσει.

+ Check the box that says 'NumbersOnly' so that only a number can be entered in the TextBox.

![](images/s3HintNumsOnly.png)

Great! The user can type in the number of minutes they exercised for. Now you want to save that information when they press the button.

+ Switch to the Blocks and take out a `when Button.Click` block.

+ The first thing you'll need is to create a **local** variable to store the TextBox value in. Grab the `initialise local name to` block from Variables, and slot it into the `when Button Click` block.

+ Then click where it says `name` and instead type `mins` to name your local variable.

![](images/s3LocalVar.png)

+ Take out a `Textbox.Text` block and attach it onto the `initialise local mins` block to store what's been typed into the TextBox.

Now that you've retrieved this information, you're going to create a **list** to put it in. After all, you want to be able to record lots of exercise sessions!

+ At the top of your code, add an `initialize global name to` block, and name it `minutesList`. Then find the `create empty list` block from Lists and use it to initialise your list.

![](images/s3CreateEmptyList.png)

+ From Lists, take the block `add items to list` and put it into your local variable block.

![](images/s3AddItemsBlock.png)

You need to attach two things to this block: the list you want to add something to, and the 'something' you want to add, meaning the **item**.

+ Hover over the name of your global list variable and grab the `get global minutesList` block that appears. Connect this to the `list` attachment of the `add items to list` block.

![](images/s3GetGlobalList.png)

+ Then do the same with the local variable, `mins`, to attach a `get mins` block to the **item** part of `add items to list`.

![](images/s3AddItemToList.png)

On the next card, you'll add all the list items together to work out the total amount of exercise you've done!
