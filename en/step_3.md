## Recording exercise

+ Create a new project and give it a name such as `GetFit`.

+ Find the TextBox component in the Palette (it's in **User Interface**) and add it to your app, along with a Label and a Button. Add a label, two textboxes and a button.

+ Change the **Text** property of the label to `Track your exercise here!` and of the button to `Enter`.

+ To arrange the textbox and the button side by side, drag a **HorizontalArrangement** onto the screen and place the components inside it.

![](images/s3HorizontalComponents.png)

+ Find the **Hint** property for the textbox and type `Minutes`. This will appear faintly in the textbox if the user hasn't typed anything in yet, so they know what to type.

+ Check the box that says **NumbersOnly** so that only a number can be entered.

![](images/s3HintNumsOnly.png)

So the user can type in the number of minutes they exercised for. Now you want to save that information when they press the button.

+ The first thing you'll need is to create a **local** variable to store the text value in. Grab the `initialise local name to` block from **Variables** and slot it into a `when Button Click` block.

+ Then click where it says `name` and instead type `mins` to name your local variable.

![](images/s3LocalVars.png)

+ Take out a `Textbox.text` block and attach it onto the variable to store the text.

Now, this only lets you save one exercise session – but you want to store more than that! So, you'll create a **list**.

+ At the top of your code, add an `initialize global name to` block, naming it `minutesList`. Then find the `create empty list` block from **Lists** and use it to initialise your list.

![](images/s3CreateEmptyLists.png)

+ From **Lists**, take the block `add items to list` and put it into your local variable block. 

You need to attach two things to this block: the list you want to add something to, and the "something" you want to add: that is,  the **item**.

+ Hover over the name of your global list variable and grab the `get global minutesList` block that appears. Attach this to the `list` attachment of the `add items to list` block.

![](images/s3GetGlobalList.png)

+ Next do the same with the local variable, `mins`, to attach a `get mins` block onto the **item** part of `add items to list`.

![](images/s3AddItemToList.png)

