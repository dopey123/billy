CIT 249: Java II
Chapter 17
Lab 3
We will create text fields, labels, buttons, radio buttons, and panels in this lab. If you read the lecture notes you
will have noticed that I mention a layout manager called CardLayout. This lab will use that layout, changing
the middle portion of the frame when a specific radio button is pressed. The program will display like this:
The opening screen
If the Draft Horse Radio Button is pressed the middle portion changes
Some components that we will use are:
o JFrame
o JTextField
o JButton
o Container
o JPanel
o Font
o JLabel
o JRadioButton
o CardLayout as our Layout Manager
The last two text fields will be uneditable, meaning that the user will not be able to enter any information within these fields.
Horse class
This class is a base class, superclass to two other classes. It will contain the attributes common to most domesticated horses. Mutator and accessor methods will be included for each attribute, as well as a constructor method.
Open Eclipse and create a new Java project named Chapter17Lab3.
With the project folder selected create a new class named Horse. Do not include the main() method.
Above the class header type the following block comments:
/*
* Superclass of different types of horses.
*/
We will have four attributes common to most domesticated horses. Scroll down to after the opening brace for the class and type:
// attributes
private int idNo;
private String coatColor;
private int age;
private double height;
· Each variable is set to private to prevent an outside class from altering the values of the variables.
We will have a single constructor method with parameters representing the variables. Type:
// constructor
public Horse(int anIdNo, String aCoatColor, int anAge, double aHeight)
{
setIdNo(anIdNo);
setCoatColor(aCoatColor);
setAge(anAge);
setHeight(aHeight);
}
· You will have errors at this point since we have yet to create our mutator methods.
· The value of each variable passed to this method is passed to the correct mutator method. The mutator method will change the value of the correct variable.
Next we'll create our mutator methods. This will eliminate the errors in Eclipse. Type:
// set mutator methods alternating the values of variables
public void setIdNo(int anIdNo)
{
idNo = anIdNo;
}
public void setCoatColor(String aCoatColor)
{
coatColor=aCoatColor;
}
public void setAge(int anAge)
{
age = anAge;
}
public void setHeight(double aHeight)
{
height = aHeight;
}
We complete this class by typing our accessor methods. Type:
// get accessor methods
public int getIdNo()
{
return idNo;
}
public String getCoatColor()
{
return coatColor;
}
public int getAge()
{
return age;
}
public double getHeight()
{
return height;
}
· Accessor methods return the designated variable by accessing the value in memory. It is returned to the point where the method is called.
Save your changes and fix any errors. Do not run this program.
SaddleHorse class
This class will inherit the attributes and methods from the Horse class and will add some attributes specific to saddle horses.
With the project folder selected, create a new class named SaddleHorse. Set the class' superclass to Horse. Do not include the main() method:
Once you click Finish the class will display as:
· Do not be concerned about the error at this time. Do note "extends Horse". Extends simply means to inherit.
Above the class header type the following block comment:
/*
* Program Chapter 17 Lab 3. This class inherits attributes and methods from
* the Horse class
*/
Scroll down to after the class' opening brace. We will create two variables. Type:
private String saddleType;
private String saddleBreed;
In order to eliminate the error we had at the class header we must create a constructor method. Type:
// constructor
public SaddleHorse(int anIdNo, String aCoatColor, int anAge, double aHeight, String
aSaddleType,String aSaddleBreed)
{
super(anIdNo,aCoatColor,anAge,aHeight);
setSaddleType(aSaddleType);
setSaddleBreed(aSaddleBreed);
}
· When you inherit from another class you must include variables from the superclass within your constructor method's parameter list. The parameter list must match that of the superclass' constructor's parameter, in addition to parameters representing variables declared in this class.
· Here the first four variables are values that will be passed to the superclass' constructor method.
The last two parameters will alter the value of variables declared in this class.
· The super(anIdNo, aCoatColor, anAge, aHeight) calls the constructor method in the Horse class, passing to it the values of these variables.
· The last two lines pass values to mutator methods in the class. The remaining code for this class creates the mutator and accessor methods for the two variable declared in this class.
Type:
// set mutator methods
public void setSaddleType(String aSaddleType)
{
saddleType=aSaddleType;
}
public void setSaddleBreed(String aSaddleBreed)
{
saddleBreed = aSaddleBreed;
}
// get accessor methods
public String getSaddleType()
{
return saddleType;
}
public String getSaddleBreed()
{
return saddleBreed;
}
Save your changes and fix any errors. Do not run this program.
DraftHorse class
This class is similar to the SaddleHorse class and will also inherit the attributes and methods in the Horse class.
No explanation will be given since it is like the previous class.
With the project folder selected, create a new class named DraftHorse and set its superclass to Horse.
Do not include the main() method.
At the beginning of the class type the following block comments:
/*
* Program Chapter 17 Lab 3. This class inherits attributes and methods from
* the Horse class
*/
After the class' opening brace type the following declarations that create two new variables:
// additional attributes beyond those inherited from Horse
private String classification;
private String draftBreed;
Like the previous class we must include a constructor method in the same way. Type:
public DraftHorse(int anIdNo, String aCoatColor,int anAge,double aHeight,String
aClassification,String aDraftBreed)
{
// invoke super class constructor
super(anIdNo,aCoatColor,anAge,aHeight);
// set subclass attribute values
setClassification(aClassification);
setDraftBreed(aDraftBreed);
}
We complete the class by typing the mutator and access methods for the two new variables. Type:
// set mutator methods
public void setClassification(String aClassification)
{
classification=aClassification;
}
public void setDraftBreed(String aDraftBreed)
{
draftBreed = aDraftBreed;
}
// get accessor methods
public String getClassification()
{
return classification;
}
public String getDraftBreed()
{
return draftBreed;
}
Save your changes and fix any errors. Do not run this program.
Ch17Lab3 class
In this class we will create our GUI application. It will create a SaddleHorse and DraftHorse object, get values fields and based on the selection of certain radio buttons, pass the values to the constructor methods and download the results to files.
With the project folder selected, create a new class named Ch17Lab3. Include the main() method and set its superclass to javax.swing.JFrame:
After clicking Finish the class will appear as:
We will include a block comment that includes the purpose of the program. Before the import
statement type:
/*
* Program: Chapter 17 Lab 3. This program will create Saddle horses and
* Draft horses. It will also demonstrate the use of the CardLayout layout
* manager.
*/
When you included the JFrame as the superclass the import statement was already included for you.
However we must include other import statements. Type:
import java.awt.CardLayout;
import java.awt.Container;
import java.awt.GridLayout;
import java.awt.FlowLayout;
import java.awt.Font;
import java.awt.Color;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.JLabel;
import javax.swing.JRadioButton;
import javax.swing.JButton;
import javax.swing.SwingConstants;
import javax.swing.ButtonGroup;
import javax.swing.BorderFactory;
import javax.swing.JOptionPane;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
import java.util.ArrayList;
import java.io.FileOutputStream;
import java.io.PrintWriter;
import java.io.IOException;
· We include the import statements for only the classes we need to import. We could use the *
wildcard instead of the name of a class but it will import all classes within a package. It is best
to only import the classes your program requires.
Scroll down to after the opening brace for the class. We will declare several components. Type:
private JPanel horsePanel;
private CardLayout horseLayout;
private JTextField coatColorField,ageField,heightField,horseIDField;
private JTextField saddleBreedField, draftBreedField;
private JLabel coatColorLabel, ageLabel, heightLabel, idLabel,saddleBreedLabel,drafthorseLabel;
private JRadioButton saddleHorseRB, draftHorseRB;
private JRadioButton americanSaddleRB, englishSaddleRB;
private JRadioButton farmingRB,haulingRB;
private JButton addButton, clearButton,closeButton;
· Our components are set to be private for the same reason as in the other classes.
· A JPanel is similar to a JFrame except that it does not have a title bar. Its default layout manager is FlowLayout which aligns components added to the panel from left to right, starting at the left edge.
· The CardLayout is a layout manager which stacks components on top of each other like a deck of cards. Only one component is visible at a time. Normally the component is a panel.
· JTextField objects are text fields.
· JLabel objects are simply text that is displayed.
· JRadioButton objects are radio buttons. These are added to a ButtonGroup so that only one can be active at any given time.
· JButton objects are simply buttons that cause something to occur when pressed.
Next we fill in the information that the main() method is responsible. In GUI applications the main()
method is mainly responsible for creating an instance of the class. It can do other things, which in this case does, but creating the object is the only thing this method must do. Scroll down to after the opening brace for the main() method and type:
Ch17Lab3 frame = new Ch17Lab3();
frame.setBounds(100,100,575,275);
frame.setTitle("Horse Types");
frame.setVisible(true);
· We create our object, set the size of padding for the frame, set the text that will display on the title bar, and most important we set its visibility. If the visibility is not set to true the frame will not display.
· At this point the frame will display when run, although nothing but the title will be evident since
we have not added anything to the frame yet.
Next we create our constructor method. Remember that constructor methods have the exact same
name as the class. After the closing brace for the main() method type:
public Ch17Lab3()
{
Container c = this.getContentPane();
c.setLayout(new GridLayout(5,1));
JPanel upperPanel = new JPanel(new GridLayout(2,4));
JPanel centerPanel = new JPanel(new FlowLayout());
JPanel saddlePanel = new JPanel(new FlowLayout());
JPanel draftPanel = new JPanel(new FlowLayout());
JPanel lowerPanel = new JPanel(new FlowLayout());
horseLayout = new CardLayout();
horsePanel = new JPanel();
horsePanel.setLayout(horseLayout);
· Since this method is quite long I'm breaking it down and explaining the code. Here we create a
Container object. You can create a frame without creating a Container but often it is good to
have one. In some cases it is preferable because of the flexibility creating a Container gives you.
So the more complex the GUI application the better it is to create a Container object.
· We set the layout of the container to GridLayout with 5 rows and 1 column.
· We declare and construct 5 new panels. Since this is the only method that needs access to these panels we simply created them here. No other method can access these panels since they are local to the method.
· We construct the horseLayout to be a new CardLayout.
· We construct the horsePanel to be a new JPanel and set its layout to the CardLayout. 
Let's continue the method by typing:
JLabel logoLabel = new JLabel(" ", SwingConstants.CENTER);
logoLabel.setFont(new Font("Helvetica", Font.BOLD,24));
logoLabel.setText("Horse Types");
c.add(logoLabel);
· We declare and construct a new label that is empty of content and centered on the screen.
· This label font is set to "Helvetica", bolded and set to 24pt.
· It's text is set to "Horse Types". This could have been done when the label was constructed, but I want you to be aware of the method used to change the text on a label.
· The label is added to the container.
· We could have declared this label at the beginning of the program. I chose not to because the label's text and positioning will always be constant.
Let's continue with the constructor method by typing:
//build upper panel
Font fontLabel = new Font("Helvetica",Font.BOLD, 12);
coatColorField = new JTextField(10);
ageField = new JTextField(4);
heightField = new JTextField(4);
horseIDField = new JTextField(3);
coatColorLabel = new JLabel("Horse's Coat Color: ",SwingConstants.RIGHT);
upperPanel.add(coatColorLabel);
coatColorLabel.setFont(fontLabel);
upperPanel.add(coatColorField);
ageLabel = new JLabel("Horse's Age: ", SwingConstants.RIGHT);
ageLabel.setFont(fontLabel);
upperPanel.add(ageLabel);
upperPanel.add(ageField);
heightLabel = new JLabel("Horse's Height: ", SwingConstants.RIGHT);
heightLabel.setFont(fontLabel);
upperPanel.add(heightLabel);
upperPanel.add(heightField);
idLabel = new JLabel("Horse's ID #: ", SwingConstants.RIGHT);
idLabel.setFont(fontLabel);
upperPanel.add(idLabel);
upperPanel.add(horseIDField);
c.add(upperPanel);
· Here we construct the fields and labels that will go into the upperPanel and add them to the panel. We end by adding the panel to the container.
Next we build the centerPanel. Type:
//build center panel
saddleHorseRB = new JRadioButton("Saddle Horse", true);
draftHorseRB = new JRadioButton("Draft Horse", false);
//create a Button Group for horse type buttons
ButtonGroup typeOfHorse = new ButtonGroup();
typeOfHorse.add(saddleHorseRB);
typeOfHorse.add(draftHorseRB);
//add radio buttons to centerPanel
centerPanel.add(saddleHorseRB);
centerPanel.add(draftHorseRB);
c.add(centerPanel);
· two of the radio buttons are constructed. The saddleHorseRB is set to true which means it will be selected by default.
· A ButtonGroup object is created and the two radio buttons are added to it. By adding the radio buttons to a ButtonGroup you are ensuring that only one will be active at a time.
· The ButtonGroup is NEVER added to the container. You add the radio buttons.
· The centerPanel is added to the container.
Continue by typing:
//build saddle horse panel
JPanel leftSaddlehorsePanel = new JPanel(new GridLayout(1,1));
JPanel rightSaddlehorsePanel = new JPanel(new FlowLayout());
saddleBreedField = new JTextField(10);
americanSaddleRB = new JRadioButton("American Saddle", true);
englishSaddleRB = new JRadioButton("English Saddle", false);
ButtonGroup saddleHorseGroup = new ButtonGroup();
saddleHorseGroup.add(americanSaddleRB);
saddleHorseGroup.add(englishSaddleRB);
saddleBreedLabel = new JLabel("Saddle Horse Breed: ");
saddleBreedLabel.setFont(fontLabel);
leftSaddlehorsePanel.add(saddleBreedLabel);
leftSaddlehorsePanel.add(saddleBreedField);
rightSaddlehorsePanel.add(americanSaddleRB);
rightSaddlehorsePanel.add(englishSaddleRB);
saddlePanel.add(leftSaddlehorsePanel);
saddlePanel.add(rightSaddlehorsePanel);
//create border for the panel
saddlePanel.setBorder(BorderFactory.createLineBorder(Color.red));
horsePanel.add(saddlePanel,"Saddle Horse");
· Here we set up the horse panel by creating two panels one set to a layout of GridLayout of 1 row and 1 column, and a second panel with the default FlowLayout layout manager.
· We construct one of our text fields and two more radio buttons and create a ButtonGroup to hold them.
· We construct a label with the text of "Saddle Horse Breed: " and add the text field, labels and radio buttons to either of the two new panels.
· The saddlePanel holds the leftSaddlehorsePanel and the rightSaddlehorsePanel.
· the border is set for the saddlePanel with a red line border and the saddlePanel is added to the
horsePanel. Remember that the horsePanel is set to a CardLayout layout manager.
Next we build the draft horse panel. Type:
//build draft horse panel
draftBreedField = new JTextField(10);
farmingRB = new JRadioButton("Farming Horse", true);
haulingRB = new JRadioButton("Hauling Horse",false);
ButtonGroup drafthorseGroup = new ButtonGroup();
drafthorseGroup.add(farmingRB);
drafthorseGroup.add(haulingRB);
drafthorseLabel = new JLabel("Draft Horse Breed: ");
drafthorseLabel.setFont(fontLabel);
draftPanel.add(drafthorseLabel);
draftPanel.add(draftBreedField);
draftPanel.add(farmingRB);
draftPanel.add(haulingRB);
draftPanel.setBorder(BorderFactory.createLineBorder(Color.green));
horsePanel.add(draftPanel,"Draft Horse");
c.add(horsePanel);
· this is similar to the panel for the saddle horse. Since both are added to the horsePanel we will later write code that will switch the display based on a particular command.
We set up the lowerPanel. Type:
//create buttons for bottom panel
addButton = new JButton("Add");
clearButton = new JButton("Clear");
closeButton = new JButton("Close");
lowerPanel.add(addButton);
lowerPanel.add(clearButton);
lowerPanel.add(closeButton);
c.add(lowerPanel);
· We construct the three buttons and add them to the panel and end by adding the panel to the container.
In the first lab we implemented the ActionListener interface so that we could add event handlers to buttons. In this program we did not do this. We will add listeners a different way. This way is used by most programmers.
Type:
//register frame as listener for events
addButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
addHorse();
}
});
clearButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
clearHorse();
}
});
closeButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
shutDown();
}
});
saddleHorseRB.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
horseLayout.first(horsePanel);
}
});
draftHorseRB.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
horseLayout.next(horsePanel);
}
});
addWindowListener(new WindowAdapter()
{
public void windowClosing(WindowEvent e)
{
System.exit(0);
}
}
);
· The first several has a particular method invoked when the button is pressed.
· Look closely at the code for the saddleHorseRB and draftHorseRB radio buttons. The first() and next() methods are used to determine which panel is displayed. Since the panel for the saddle horse was added first to the horsePanel it is displayed upon loading of the program. If the draftHorseRB is selected the panel is hidden or rather moved down and the panel for the draft horse is displayed.
Close the constructor method by typing the closing, curly brace.
Our next method is the addHorse() method. It will check to make sure all fields are entered and check to see which of two radio buttons are selected. If the radio button for the saddle horse is selected then one method is invoked, or another is invoked. After the closing brace for the constructor method,
type:
private void addHorse()
{
try
{
String coatColor = coatColorField.getText();
String strAge = ageField.getText();
String strHeight = heightField.getText();
String strHorseID = horseIDField.getText();
if(coatColor.length() == 0 || strAge.length() == 0 || strHeight.length() == 0 ||
strHorseID.length() == 0)
JOptionPane.showMessageDialog(this, "Please Enter All Data");
else
{
int age = Integer.parseInt(strAge);
double height = Double.parseDouble(strHeight);
int horseId = Integer.parseInt(strHorseID);
if(saddleHorseRB.isSelected())
{
addSaddlehorse(horseId,coatColor,age,height);
}
else
{
addDrafthorse(horseId,coatColor,age,height);
}
}
}
catch(NumberFormatException e)
{
JOptionPane.showMessageDialog(this,"Age, height and ID must be numeric");
}
}
· You can check the length of a variable by simply checking its length. We assigned values to variables by using the getText() method for JTextFields.
The clearHorse() method simply clears the fields and resets the radio buttons. Type:
private void clearHorse()
{
coatColorField.setText("");
ageField.setText("");
heightField.setText("");
horseIDField.setText("");
saddleBreedField.setText("");
draftBreedField.setText("");
saddleHorseRB.doClick();
americanSaddleRB.doClick();
farmingRB.doClick();
coatColorField.requestFocus();
}
· Using the setText() method we clear the fields.
· The doClick() method is used to click our default radio buttons.
· The requestFocus() method places the cursor on the coatColorField.
The shutDown() method is used to close the program. Type:
private void shutDown()
{
System.exit(0);
}
The addSaddlehorse() method continues where the addHorse() method ended by assigning values to variables that are for only saddle horses. It also downloads all the information to a file. Type:
private void addSaddlehorse(int anIdNo, String aCoatColor,int anAge,double aHeight)
{
ArrayList <SaddleHorse>saddleHorses=new ArrayList<SaddleHorse>();
String saddleBreed = "";
String saddleType= "";
saddleBreed = saddleBreedField.getText();
if(saddleHorseRB.isSelected())
saddleType = "American Saddle";
else
saddleType = "English Saddle";
SaddleHorse aSaddleHorse = new SaddleHorse(anIdNo, aCoatColor, anAge,
 aHeight,saddleType,saddleBreed);
saddleHorses.add(aSaddleHorse);
JOptionPane.showMessageDialog(this, "Saddle Horse added");
for(int i = 0;i<saddleHorses.size();i++)
{
try
{
SaddleHorse nextHorse;
FileOutputStream saddleHorseOut = new
FileOutputStream("SaddleHorse.dat",true);
PrintWriter saddleOut = new PrintWriter(saddleHorseOut);
aSaddleHorse = (SaddleHorse) saddleHorses.get(i);
saddleOut.println("ID #: " + aSaddleHorse.getIdNo());
saddleOut.println("Coat Color: " + aSaddleHorse.getCoatColor());
saddleOut.println("Age: " + aSaddleHorse.getAge());
saddleOut.println("Height: " + aSaddleHorse.getHeight() + " hands high");
saddleOut.println("Saddle Type: " + aSaddleHorse.getSaddleType());
saddleOut.println("Breed: " + aSaddleHorse.getSaddleBreed());
saddleOut.close();
}
catch(IOException e)
{
JoptionPane.showMessageDialog(null,"Please check your input. The id number and age must be whole numbers. The height field must be numeric. All fields must be entered");
}
}
clearHorse();
}
· An ArrayList is constructed.
· There are two new String variables. The first obtains its value by accessing a text field. The second is based on which of two radio buttons are selected.
· A SaddleHorse object is constructed and values of variables are passed to its constructor method.
· The object is added to the ArrayList and a popup message is displayed that a Saddle Horse has been added.
· Using a try/catch block the information is downloaded to a file. When downloading to a file you
must include the code within a try/catch block so an exception can be thrown in situtations where the file wasn't found, the file was corrupt, or something else occurred preventing the download or creation of the file.
Our last method does the same thing as the previous method, but is for draft horses. Type:
private void addDrafthorse(int anIdNo, String aCoatColor, int anAge, double aHeight)
{
ArrayList <DraftHorse>draftHorses=new ArrayList<DraftHorse>();
String draftBreed,classification;
draftBreed = draftBreedField.getText();
if(farmingRB.isSelected())
classification = farmingRB.getText();
else
classification = haulingRB.getText();
DraftHorse aDraftHorse = new DraftHorse(anIdNo, aCoatColor, anAge, aHeight,
 classification,draftBreed);
draftHorses.add(aDraftHorse);
JOptionPane.showMessageDialog(this, "Draft Horse has been added");
for(int i = 0;i<draftHorses.size();i++)
{
try
{
DraftHorse nextHorse;
FileOutputStream draftHorseOut = new FileOutputStream("DraftHorse.dat",true);
PrintWriter draftOut = new PrintWriter(draftHorseOut);
aDraftHorse =(DraftHorse) draftHorses.get(i);
draftOut.println("ID #: " + aDraftHorse.getIdNo());
draftOut.println("Coat Color: " + aDraftHorse.getCoatColor());
draftOut.println("Age: " + aDraftHorse.getAge());
draftOut.println("Height: " + aDraftHorse.getHeight() + " hands high");
draftOut.println("Classification: " + aDraftHorse.getClassification());
draftOut.println("Breed: " + aDraftHorse.getDraftBreed());
draftOut.close();
}
catch(IOException e)
{
JOptionPane.showMessageDialog(null,"Please check your input. The id number and age must be whole numbers. The height field must be numeric. All fields must be entered");
}
}
clearHorse();
}
· One thing to note in both methods is that the values of the different attributes are obtained by calling the accessor methods in the different classes.
· At the end of each method we invoke the clearHorse() method to clear the fields and reset the radio buttons.
Save your changes and fix any errors if necessary. Run and test the program.
If you select the project folder under Package Explorer and right-click and choose Refresh you will see that the .dat files have been created.
Compress the entire project folder into a single zip or rar file and submit.

