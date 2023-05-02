Download Link: https://assignmentchef.com/product/solved-comp1210-activity9-inheritence
<br>
<strong>Goals: </strong>

By the end of this project you should be able to do the following:

<ul>

 <li>Derive subclasses (or child classes) from a base (or parent) class</li>

 <li>Use the protected modifier for inheritance</li>

 <li>Use the super reference to refer to a parent class</li>

 <li>Create an abstract class</li>

 <li>Override methods in child classes</li>

</ul>




<strong>Directions: </strong>

Don’t forget to add your Javadoc comments for your classes, constructor, and methods in this activity.




For this assignment, you will need to create a class called InventoryItem that represents an inventory item in a store. InventoryItem should have the following characteristics:




<strong>InventoryItem </strong>

<ul>

 <li>Variables:

  <ul>

   <li>A <strong>String</strong> called name using the protected visibility modifier o A <strong>double</strong> called price using the protected visibility modifier o A private <u>static</u> <strong>double</strong> called taxRate (initialized to 0)</li>

  </ul></li>

 <li>Constructor:

  <ul>

   <li>Sets the values for the instance variables name and price:</li>

  </ul></li>

</ul>

public InventoryItem(String nameIn, double priceIn)

<ul>

 <li>Methods:

  <ul>

   <li>public String getName() {

    <ul>

     <li>Returns the customer name o public double calculateCost() {</li>

     <li>Returns the price including tax: price * (1 + taxRate)</li>

    </ul></li>

   <li>public static void setTaxRate(double taxRateIn){

    <ul>

     <li>Sets the tax rate</li>

    </ul></li>

   <li>public String toString() {

    <ul>

     <li>Return a String representation with name and price with tax Example: “Computer: $789.02”</li>

    </ul></li>

  </ul></li>

</ul>

return name + “: $” + __________();




Ï¼ÏÏInventoryItem.setTaxRate(0.08);

Ï¼ÏÏInventoryItem item1 = <strong>new</strong> InventoryItem (<strong>“Birdseed”</strong>, 7.99);

Ï¼ÏÏitem1

ÏÏÏÏBirdseed: $8.6292

Ï¼ÏÏInventoryItem item2 = <strong>new</strong> InventoryItem (<strong>“Picture”</strong>, 10.99);

Ï¼ÏÏitem2

ÏÏÏÏPicture: $11.869200000000001

<strong>       </strong>

Be sure to unfold these objects on the workbench to verify the field values.

<strong>             </strong>

<strong>ElectronicsItem </strong>

<ul>

 <li><u>In a new file</u>, create a class called ElectronicsItem that inherits from InventoryItem. Electronics items will have all of the characteristics of Inventory items and will take into account shipping costs.</li>

</ul>

public class ElectronicsItem extends InventoryItem {




<ul>

 <li><u>Add a <strong>protected</strong> <strong>double</strong> instance variable for the <strong>weight</strong> of the item.</u> Then add a public constant to represent the shipping cost per pound:</li>

</ul>

public static final ________ SHIPPING_COST = 1.5;




<ul>

 <li>Add a constructor to ElectronicsItem that takes a <strong>String for name (nameIn)</strong>, a <strong>double for price (priceIn)</strong>, and a <strong>double for weight (weightIn)</strong>. Invoke the constructor for InventoryItem using the reserved word super: super(nameIn, priceIn);</li>

</ul>




Add code to set the weight of the item. Now compile this class.




<ul>

 <li><strong><u>Override</u></strong> the calculateCost method to take into account shipping.</li>

</ul>




ÏÞßà<strong>public</strong> <strong>double</strong> calculateCost() {

Â¹Ä¹¹Ï<strong>return</strong> <strong>super</strong>.calculateCost() + (SHIPPING_COST * weight); ÏÏ©}




Ï¼ÏÏInventoryItem.setTaxRate(0.08);

Ï¼ÏÏElectronicsItem eItem = <strong>new</strong> ElectronicsItem(<strong>“Monitor”</strong>, 100, 10.0); Ï¼ÏÏeItem

ÏÏÏÏMonitor: $123.0ÏÏÏ

<strong> </strong>

<strong>OnlineTextItem </strong>

<ul>

 <li><u>In a new file</u>, create a class to represent an online text item that users can buy (such as an electronic book or journal article). This class does not need to be instantiated as it is just a concept that represents a number of items, so it is an <em><u>abstract</u></em> class (more on abstract classes on Wednesday in class):</li>

</ul>

public abstract class OnlineTextItem extends InventoryItem {




<ul>

 <li>Write a constructor that will only call the constructor of the parent class (InventoryItem) using the super reserved word:</li>

</ul>




ÏÞßà<strong>public</strong> _____________(String nameIn, <strong>double</strong> priceIn) {

ÏÏ¨¹¹Ï<strong>super</strong>(_________, ____________); ÏÏ©}

<ul>

 <li>These items are not taxed, so you’ll need to override the calculateCost method to only return the price. <strong>The price variable has been inherited from InventoryItem</strong>:</li>

</ul>




ÏÞßà<strong>public</strong> _____________calculateCost() {

Â¹Ä¹¹Ï<strong>return</strong> price;

ÏÏ©}

<strong> </strong>

<strong> </strong>

<strong>OnlineArticle </strong>

<ul>

 <li>Because we cannot instantiate OnlineTextItem, we will need to create subclasses that inherit from OnlineTextItem. <u>In a new file</u>, create the class OnlineArticle which is a electronic text that keeps track of word count in addition to everything that is done by OnlineTextItem and InventoryItem:</li>

</ul>

public class OnlineArticle extends OnlineTextItem {     private int wordCount;




<ul>

 <li>As with your other classes, you will need a <strong>constructor</strong> with parameters for nameIn and priceIn that calls the constructor of the parent class and also <strong>initializes wordCount to 0</strong>.</li>

 <li>Add a <strong>setWordCount</strong> method to set the wordCount variable.</li>

</ul>

<strong>OnlineBook </strong>

<ul>

 <li><u>In a new file</u>, create the class OnlineBook which will need to inherit from OnlineTextItem and will need to include a variable for the author’s name:</li>

</ul>

public class OnlineBook extends OnlineTextItem {    protected String author;

<ul>

 <li>As with your other classes, you will need a <strong>constructor</strong> with parameters for nameIn and priceIn that calls the constructor of the parent class and also initializes the author String to “Author Not Listed”.</li>

</ul>




<ul>

 <li><strong><u>Override</u></strong> the toString method so that the author’s name is listed after the name of the book in the format “book name – author’s name : $price (see interactions output below).</li>

</ul>




<ul>

 <li><u>Add a setAuthor method to set the author’s name </u>and then try the following in the interactions pane:</li>

</ul>

Ï¼ÏÏOnlineBook book = <strong>new</strong> OnlineBook(<strong>“A Novel Novel”</strong>, 9.99);

Ï¼ÏÏbook

ÏÏÏÏA Novel Novel – Author Not Listed: $9.99

Ï¼ÏÏbook.setAuthor(<strong>“Jane Lane”</strong>);

Ï¼ÏÏbook

ÏÏÏÏA Novel Novel – Jane Lane: $9.99ÏÏÏ




<strong>InventoryApp – driver program with the main method </strong>

<ul>

 <li>In a new file, create the class InventoryApp as your driver program and add a main method that does the following: o Sets the tax rate to 0.05 by calling the static method InventoryItem.setTaxRate(0.05). Then instantiates and prints each of the following four objects using variable names <em>item1</em>, <em>item2</em>, <em>item3</em>, and <em>item4</em> respectively:</li>

</ul>

o <strong>InventoryItem</strong> – name: Oil change kit; price: $39.00 o <strong>ElectronicsItem</strong> – name: Cordless phone; price: $80.00; weight: 1.8 lbs o <strong>OnlineArticle</strong> – name: Java News; price: $8.50; wordcount: 700 words o <strong>OnlineBook </strong>– name: Java for Noobs; price: $13.37; author: L. G. Jones Compile and run the program in canvas mode .  After the canvas window opens, click <strong>View</strong> on the canvas toolbar and then select the check box for “Show Types in Viewer Labels”.  Now <em>single step</em> the program, then drag the objects onto the canvas shown in Figure 1 below.  Unfold each of the objects in the debug tab to see the details of each field.  Figure 2 shows <em>item4</em> unfolded in the debug tab.  Notice that the symbol in front of each field is color-coded: <em>green</em> indicates the field  was declared in the OnlineBook class (i.e., the type of item4); <em>orange</em> indicates the field was inheritited from the parent or super class which shown at the end of the field description.  Also, note that <em>taxRate</em> is underlined to indicate that the variable is <em>static</em>.

<strong>             </strong>

<strong>Figure 2.  The variable item4 (unfolded) in the debug tab. On the canvas, the Detailed viewer can be used to display the same information as shown in the debug tab. </strong>

<strong> </strong>

<strong> </strong>

<strong>Project File (5%) </strong>

<ul>

 <li>Create a project file named InventoryApp and then add all of your java files above.</li>

 <li>Click on the UML diagram to generate the class hierarchy.</li>

 <li>Right-click in the UML diagram and select Layout &gt; Tree Down then click All. Your UML class diagram should be similar to the one in Figure 3.</li>

</ul>

<strong> </strong>

<strong>Figure 1.  Canvas with the four objects created in the main method. The variables item1, item2, item3, and item4 are shown using the default <em>Basic</em> viewer. </strong>

<strong> </strong>

<strong>Figure 3.  UML class diagram for InventoryApp. </strong>

<strong> </strong>