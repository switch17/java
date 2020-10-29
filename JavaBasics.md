import java.util.Scanner;
/*
    import java.lang.*; - this is necessary and is imported automatically in modern IDEs.
 - In Java everything is wrapped  inside a class (including the main function)
 - It is advisable to keep the filename same as the name of the class that contains main function
 - Java follows the following naming conventions as per tradition
    1. for class name - ClassName - 1st letter of each word in class name is capital //PascalCase
    2. for method name - methodeName() - camelCase is used
    3. variables name - variablename/variable_name/variableName - snake_case/camelCase is used
    4. Constant/Final names - CONSTANTNAME - Capital letters are used
 */
public class Part1 {
    public static void main(String[] args) {
        /* Print Statement
            # There are 2 types of print statements
              - System.out.print() - cursor stays on the same line where the print statement ends
              - System.out.println() - cursor moves onto the next line when the print statement end */
        System.out.print("Enter your name: ");

        /*  Input statement
              # Firstly, import 'Scanner' class from 'java.util' package
                - import java.util.Scanner;
              # Then create a object of Scanner class  using following syntax
                - Scanner object_name = new Scanner(System.in);
                // Here 'Scanner' word on the LHS is the name of the class  'Scanner' & 'Scanner()' is the constructor method of that particular class
                // The 'System.in' part of the  statement instructs the compiler to take the input from console
              # Use  the   object_name  to access methods of  'Scanner' class
                - eg. int num = object_name.nextInt();
                - eg. String name = object_name.nextLine()
                - eg. BigDecimal money = object_name.nextBigDecimal(); ??Note: BigDecimal has higher precision
                */
        Scanner x = new Scanner(System.in);
        String name = x.nextLine();
        System.out.println("Hi " + name + "!");

        /*  Data Types
             # Java is a statically typed programming language, which means that you need to do declare variables with specific data type before you use 'ém
                1. Primitive Data Types
                    a. boolean - bool variable_name = literal (true / false)
                    b. byte - byte variable_name = literal (unicode characters + no(s) b/w -128  to 127)  (size - 1 Byte)
                    c. character - char variable_name = literal (all unicode characters) (size - 2 Bytes)
                    d. short int- short variable_name = literal  (-32768 to 32767) (size - 2 Bytes)
                    e. integer - int variable_name = literal (integers) (size - 4 Bytes)
                    f. long int - long variable_name = literalL (integers) (size - 8 Bytes)
                            -eg. long x = 567817267867L //Note: You need to add 'L' at the end if the long literal if it's beyond the scope of original integer value
                    g. float - float variable_name = literal (Floating point no(s))(size - 4 Bytes)
                            - eg. float x = 56.657f  //Note: 'f' at the end is necessary
                    h. double - double variable_name = literal (Floating point no(s)) (size - 8 Bytes)

                2. Objects
                    a. String - String object_name = literal
                    b. Integer - Integer object_name = literal
                    c. Double - Double object_name = literal
                    NOTE: object types covers almost all primitive data types (just confirm)

                        # We can use the properties of these  classes using '.' operator
                            -eg. System.out.println(Integer.MIN_VALUE);
                                 System.out.println(Double.MAX_VALUE);
                                 System.out.println(Double.isNan(Math.sqrt(-1)));

              # Constants
                - syntax:
                            final datatype CONSTANTNAME = literal; // 'final' is the keyword for declaring constants

                            Note: for global declaration of constant use following syntax
                                public static final datatype CONSTANTNAME = literal;

                                public - so that all the classes can access it
                                static - so that there's no need to create instance of the class in that particular class

              # Typecasting
                -eg. int a = 5, b = 2;
                     if we do =>        double x = a/b          // Result => 2
                     //In the above  case the dividend and divisor, both are integers and the result is stored in a double variable...
                     //to overcome this problem we add the desired '(datatype)'  in front of each member of the  expression since '(datatype)' is a unary operand
                        i.e.        double x  = (double)  a/b       //Result => 2.5

              # Converting a string to a
                    1. integer value
                        -  eg. String x = "100"; //100 is a string here
                               int a = Integer.parseInt(x); //100 is a no. here
                                                OR
                               Integer a = Integer.valueOf(x);
                    2. double value
                        -  eg. String y = "5.25";
                               double b = Double.parseInt(y);

              # Strings
                   - Some properties of string class
                        eg. String str = "sohan";
                        1. charAt(index) - returns the character at specified index
                            - eg. System.out.println(str.charAt(3));        //a

                        2. length() - returns length of the string
                            - eg. System.out.println(str.length());         //5

                        3. concat("text goes here") - concatenates the string passed as argument to the specified string
                            - eg. String z = "vaigankar ";
                                  z.concat(str);        //vaigankar sohan

                        4. contains("string") - checks for the presence  of the string passed as an args in the specified string and returns boolean value
                            - eg. System.out.println(z.contains("han"));         //True

                        5. indexOf("string") - returns the index of the starting character of the string specified
                            -eg. System.out.println(z.indexOf("so"));           //10

                        6.  toUpperCase() - converts the string characters to uppercase letters
                            - eg. System.out.println(str.toUpperCase);

                        7.  toLowerCase() - converts the string characters to lowercase letters
                            - eg. System.out.println(str.toLowerCase);

                        8. strip() - removes  white spaces from the beginning  and ending of the string
                           stripLeading() - removes white space  from the beginning of the string
                            - eg.   string x = "   some text here   \n  ";
                                    System.out.println(x.strip);

                        9. substrings(beginIndex, endIndex) - cuts a part of the  string from beginIndex (must be specified) through endIndex (optional).
                           Note: if endIndex is not specified  the substring goes till end of the original string
                            - eg. System.out.println(z.substring(10));      //sohan

                       10. repeat(no_of_times) - repeats the string for the times specified
                            -eg. System.out.println(str.repeat(10));

                       11. equals("string") - checks  if 2 strings are  equal  and returns  boolean value
                            - eg. System.out.println(str.equals(z));      //false

               # Comparison Operators  - this include ' ==, !=, <, >, <=, >= '
               # Logical Operators - this include ' &&, ||, ! '


               # Switch Case
                    -  syntax:
                                switch(value) {
                                    case 1:
                                            statement;
                                            break;
                                    case 2:
                                            statement;
                                            break;
                                    case 3:
                                    case 4:
                                    case 5:
                                            statement;
                                            break;
                                    default:
                                            statement;
                                            break;
                                 }

               //Note: 'break' statement exit out of loop.
               //Note: 'continue' statement exits the iteration.

               # Ternary Operator - this is kinda similar to if-else
                    - syntax:   exp ? if_true : if_false

               # Loops
                    1. while loop
                        - syntax:
                                    while(condition)
                                    {
                                        statement;
                                        update++;
                                    }

                    2. do while loop
                        - syntax:
                                    do
                                    {
                                        statement;
                                        update++;
                                    } while(condition);

                    3. for loop
                        - syntax:
                                    for(initialization; condition; update)
                                    {
                                        statement;
                                    }

                    3. for each loop
                        - for each loop is  similar to for lop but size of the list / array  or basically end condition is not required and loop will visit each  element one-by-one from starting index and  will stop when the array/list is fully traversed
                        - syntax:
                                    for(initialization :  array_name / list_name)
                                    {
                                        statement;
                                    }
                        - eg.
                              for(int  element = list_name)
                              {
                                System.out.println(element*10);
                              }

                    # Arrays
                        Properties of Arrays
                            1. length - returns the length of the array. - syntax: array_name.length
                        1. 1-D Arrays
                            - syntax:
                                        data_type[] array_name = new data_type[size];       //for use input

                                                                OR

                                        data_type [] array_name = {value1, value2, ...};     //hardcoding values

                                Arrays.toString(array_name) - to display values/status of array
                                    //Note: import java.util.Arrays; to use  this function
                                    - eg. System.out.println(Arrays.toString(array_name));

                             -  eg.
                                    Scanner input = new Scanner(System.in);
                                    int size = input.nextInt();
                                    int [] array = new int[size];
                                    for(int i = 0; i < size; i++)
                                    {
                                        int temp = input.nextInt();
                                        array[i] = temp;
                                    }

                           # We've predefined useful methods for sorting arrays and various other things in Arrays package,
                             just make sure to import 'java.util.Arrays' & 'java.util.ArrayList'
                                - eg.
                                        1. Arrays.sort(array_name);  - sorts the array in ascending order (Quick sort)

                                        2. Arrays.parallelSort(array_name); - sorts array in ascending order

                                        3. Arrays.equals(array_name1, array_name2) - checks if the 2 arrays are equal and returns true if they're
                                            - eg. if(Arrays.equals(array_name1, array_name2))
                                                    {
                                                        System.out.println("Equal!!")
                                                    }

                                        4. Arrays.fill(array_name, value) - replaces all the elements of array with fill value
                                            - eg. String [] array = new String[10];
                                                  Arrays.fill(array, "");       // empty character

                                        5. Arrays.asList(array_name) - converts array into a list
                                            - eg. List<DataTypeClass> list_name = Arrays.asList(array_name);
                                            //Note: data_type should be same  as that of the array and don't forget to import 'java.util.List'

                          2. 2-D Arrays
                            - syntax:
                                        data_type[][] array_name = new data_type[row_size][col_size];       //for use input

                                                                OR

                                        data_type [] array_name = {{col1}, {col2}, ...};     //hardcoding values

                                Arrays.toString(array_name) - to display values/status of array
                                    //Note: import java.util.Arrays; to use  this function
                                    - eg. System.out.println(Arrays.deepToString(array_name));

                             -  eg.
                                    Scanner input = new Scanner(System.in);
                                    int row_size = input.nextInt();
                                    int col_size = input.nextInt();
                                    int[][] array = new int[row_size][col_size];
                                    for(int row = 0; row < row_size; row++)
                                    {
                                         for(int col = 0; col < col_size; col++)
                                         {
                                            int temp = input.nextInt();
                                            array[col] = temp;
                                         }
                                    }

                               //Note: In the case of 2-D Arrays 'length' property alone gives the no. of rows,
                                        to find the no. of cols use
                                                           'array_name[index].length'
                                        Here, index == index of row

                        #  Array List
                            - list is  very similar to array but it's size can be  dynamically increased / decreased unlike  arrays which is  fixed  when declared
                            //Note: import java.util.List; when using list (mandatory)
                                    - We don't need to specify the size of the list while declaring
                                - syntax:
                                            List <DataTypeClass> list_name = new TypeOfList<DataTypeClass>();

                                            //Note: There are many type of lists like ArrayList & LinkedList and depending on the list you choose, you should specify the 'TypeOfList' and  import 'java.util.TypeOfList;'
                                                    here, we're referring to ArrayList
                                                    So,     import java.util.ArrayList;
                                                            List<DataTypeClass> list_name = new ArrayList<DataTypeClass>();


                                Accessing elements of list
                                    - Similar to arrays  , list element can be accessed by
                                            syntax:
                                                        list_name[index];

                                Displaying whole list at once
                                    - Actually there are many ways of doing this but the following is pretty straightforward
                                        - syntax:
                                                    System.out.println(Arrays.toString(list_name.toArray()));

                                        - Basically, the above  syntax  first converts list to array using method 'toArray()' and then uses 'toString()' to display the entire array

                                Iterating through a list
                                    //Note: for each loop can be used here
                                    - eg. List<Integer> list_name = Arrays.asList(5, 3, 2, 6, 3);       // initializing list values using arrays
                                          for(int i = 0; i < list_name.size(); i++)
                                          {
                                                list_name.set(i, list_name.get(i) * 10);    //Updating list elements, i.e. multiplying by 10
                                                System.out.println(list_name.get(i));   // displaying list elements
                                          }

                                Nested Lists
                                    - syntax:
                                                List<List<DataTypeClass>> main_list = new ArrayList<List<DataTypeClass>>();

                                    - eg. List<List<Integer>> main_list = new ArrayList<List<Integer>>();
                                          main_list.add(Arrays.asList(5, 3, 2, 6, 3));
                                          main_list.add(Arrays.asList(8, 3, 4, 2, 4));
                                          main_list.add(Arrays.asList(45, 57, 68, 97, 34));

                                          // to iterate through the Nested Lists
                                          //Note: The nested list is of the type 'List<integer>' and not simply 'int'
                                          for(List<Integer> list_no : main_list)        //Accessing Nested Lists from main_list
                                          {
                                                for(int element : list_no)              //Accessing elements of nested list
                                                {
                                                    System.out.print(element + "\t");
                                                }
                                                System.out.println();
                                          }

                                Converting List to Array
                                    - syntax:
                                                int[] array_name = new int[list_name.size()];

                                                for(int i = 0; i < list_name.size(); i++ )
                                                {
                                                    array_name[i] = list_name.get(i);
                                                }

                                                System.out.println(Arrays.toString(array_name));

                                - List methods

                                    1.  add(value) / add(index, value); - appends element to the list /  at specified index
                                        - syntax:  list_name.add(value); / list_name.add(index, value);

                                    2.  get(index); - returns the element at specified index
                                        - syntax:  list_name.get(index);

                                    3.  set(index, value); - updates the specified index with passed value
                                        - syntax:  list_name.set(index, value);

                                    4.  size(); - returns the size of the array
                                        - syntax:  list_name.size();

                                    5.  isEmpty() - checks if the list is  empty or not by returning boolean value
                                        - syntax: list.isEmpty();

                                    6.  remove(index) - removes element from the list present at specified index
                                        - syntax: list.remove(index);

                                    7.  clear() - removes everything from the list
                                        - syntax: list_name.clear();

                                  # Using 'Collections' tool properties on list
                                    1. sort(list_name) - sorts the list in ascending order
                                        - syntax:   Collections.sort(list_name);

                                    2. reverse(list_name) - reverses the order of elements
                                        - syntax:   Collections.reverse(list_name);


                # Class and Object
                    - syntax:
                            public class MainClass {
                                public static void main(String args[])
                                {
                                    DummyClass1 dummy1 = new DummyClass();     //creating object of 'DummyClass'
                                    dummy.memberFunction();                     //calling methods of 'DummyClass'
                                }
                            }

                            public class DummyClass {
                                public static void  memberFunction()
                                {
                                    System.out.println("Hi from DummyClass");
                                }
                            }

                    # Encapsulation
                        - wrapping of data members & member functions inside a class such that not all the data is publicly accessible
                        - the key idea here  is to use 'getter' & 'setter' methods for getting data from class and  setting data to class  data members and member functions resp.
                        - getter method - usually combines the various fields of class and returns
                        - setter method - don't return value (usually void) as it is used to set/update values of different fields of a class
                            - eg.
                                public class MainClass {
                                    public static void main(String args[])
                                    {
                                        DummyClass1 dummy1 = new DummyClass();
                                        dummy.setName("So", "han");     //Accessing set method
                                        dummy.getName();                //Accessing get method
                                    }
                                }

                                public class DummyClass {
                                    private String firstName;
                                    private String lastName;

                                    //getter method
                                    public static String getName()
                                    {
                                        return firstName + lastName;
                                    }

                                    //Setter  method
                                    public void setName(String str1, String str2)
                                    {
                                           firstName = str1;
                                           lastName = str2;
                                    }
                                }

                     # Creating a List of Objects
                            - syntax:
                                        List<ClassName> object_name = new TypeOfList<ClassName>();

                            - eg.
                                    public class MainClass{
                                        public static void main(String[] args)
                                        {
                                            String [] firstName = {"Bat", "Iron", "Hanu"};
                                            String [] lastName = {"man", "man","man"};
                                            List<DummyClass> dummy_list = new ArrayList<DummyClass>();   //DummyClass is the custom type
                                            for(int  i = 0; i<3; i++)
                                            {
                                                DummyClass obj = new DummyClass();
                                                obj.setName(firstName[i], lastName[i]);
                                                dummy_list.add(obj);
                                            }

                                            for(DummyClass element: dummy_list )
                                            {
                                                System.out.println(element.getName());
                                            }
                                        }
                                    }

                                    class DummyClass {
                                        private String firstName;
                                        private String lastName;

                                        //getter method
                                        public String getName()
                                        {
                                            return firstName + lastName;
                                        }

                                        //Setter  method
                                        public void setName(String str1, String str2)
                                        {
                                            firstName = str1;
                                            lastName = str2;
                                        }
                                    }

                #Note: Static methods are class methods, i.e. they can be accessed directly using ClassName of the Class in which they  defined  inside any other class
                        - syntax for defining: public static return_type methodeName()
                                                {
                                                    statement;
                                                }
                        - syntax for  calling:      ClassName.staticMethod()

                        Otherwise, we've to call method using instant method and to call such methods one  has to create object of the class where method  is to be called
                            - syntax for calling : obj.methodeName();
                            - syntax for definition: normal (w/o static keyword)

                 # Taking custom types as function arguments
                    - eg.
                                    public class MainClass{
                                        public static void main(String[] args)
                                        {
                                            String [] firstName = {"Bat", "Iron", "Hanu"};
                                            String [] lastName = {"man", "man","man"};
                                            List<DummyClass> dummy_list = new ArrayList<DummyClass>();   //DummyClass is the custom type
                                            for(int  i = 0; i<3; i++)
                                            {
                                                DummyClass obj = new DummyClass();
                                                obj.setName(firstName[i], lastName[i]);
                                                dummy_list.add(obj);
                                            }

                                            DummyClass.getFullName(dummy_list);     //calling static function by passing entire list of objects
                                        }
                                    }

                                    class DummyClass {
                                        private String firstName;
                                        private String lastName;

                                        //getter method
                                        public String getName()
                                        {
                                            return firstName + lastName;
                                        }

                                        //Setter  method
                                        public void setName(String str1, String str2)
                                        {
                                            firstName = str1;
                                            lastName = str2;
                                        }

                                        public static void getFullName(List<DummyClass> dummy_list)     //passing full list of objects
                                        {
                                            for(DummyClass element: dummy_list)
                                            {
                                                System.out.println(element.getName());
                                            }
                                        }
                                    }

                 # Method Overloading
                    - same function name but different args (different types or different no. of args)
                    - return_type  can be  same  or different, it won't matter.

                    - eg. void methodOne(int x);                    - Method Overloading
                          int methodOne(int x):                     - Not Method Overloading
                          void methodOne(String x, int y);          - Method Overloading
                          int methodOne(String x):                  - Method Overloading
                          void methodOne(int x, int y, int z);      - Method Overloading
                          int methodOne(int x, double w):           - Method Overloading

                 # Method Overriding
                    - Changing the definition of the method in a derived class
                    - for method overriding just put @Override keyword above method definition in sub class
                    - syntax:
                                @Override
                                public return_type methodName()
                                {
                                    statement;
                                }

                 # pass by value & pass by reference
                    - search more about this topic

                 //Note: Most methods in Java are 'Virtual' by default except static methods and private methods

                 # Inheritance
                    1. Single Inheritance
                        - A single derived class is inherited from base class
                        -  syntax:
                                    public class Base {
                                        data_members & memberFunctions();
                                    }

                                    public class derived extends  Base {
                                        statement;
                                    }

                    2.



                   # Abstract Classes
                        -  Abstract class is class of something that doesn't exist... it is more like a class of characteristics
                        - syntax:
                                    public abstract class ClassName {
                                        body;
                                    }

                   # Abstract Methods
                        - when a method  is made abstract it cannot be defined or  have a body. It's designed to be overridden
                        - ends with ';' and is usually declared inside abstract class
                        - syntax:
                                    public abstract void methodName();

                   # Polymorphism
                        - important  stuff

                   # Constructors
                        - Constructor is a special member function which is used to initialise a object
                        - gets invoked automatically when object is created
                        - if parameterised constructor is defined then default constructor should be compulsorily defined
                        - always public
                        - name same as class name

                        1. Default Constructor
                            - syntax:
                                        public ClassName()
                                        {
                                            statement;
                                        }

                        2. Parameterised Constructor
                            - syntax:
                                        public ClassName(data_type var_name1, data_type var_name2)
                                        {
                                            statement;
                                        }
                            - syntax to call parameterised constructor:
                                ClassName obj = new ClassName(arg1,arg2);  //pass the args to the parameterised constructor

                        3. Copy Constructor

                    # Super keyword
                        - used to access/invoke  members of base class from derived class
                        - syntax:
                                super.methodeName();        // that methodName can be replaced by any particular data_member or memberFunction of base class

                     # Interface
                        - interfaces are very similar to classes but interfaces are specifically used to define behaviour and  are then implemented
                        -


                     # final methods
                        - prevents overriding of a method in further derived classes
                        - syntax:
                                    public final return_type methodName()
                                    {
                                        statement;
                                    }

                     # final class
                        - prevents class from extending further
                        - syntax:
                                public final class ClassName{
                                    body;
                                }

                      # enumeration - learn more about this


        */
    }
}