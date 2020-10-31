# **Java**

Following are the **pre-requisites** to get started with Java Programming

1. Download & install JDK on your machine
2. Set the path
3. Download a IDE or code editor (add extensions if needed)
4. And you're ready to go!

**Java.lang package**

- It provides classes that are fundamental to the design of the Java programming language.

```java
import java.lang.*;

// this is necessary and is imported automatically in modern IDEs.
```

```java
import java.util.Scanner;
```

- In Java everything is wrapped inside a class (including the main function)
- It is advisable to keep the filename same as the name of the class that contains main function

## Naming conventions in Java

- Java follows the following naming conventions as per tradition
  1. For class name
     - **C**lass**N**ame - 1st letter of each word in class name is capital //PascalCase
  2. For method name
     - method**N**ame() - camelCase is used
  3. For variable name
     - variablename / variable_name / variableName - snake_case/camelCase is used
  4. Constant/Final names
     - **CONSTANTNAME** - All capital letters are used

## Basic structure of a java program

```java
public class ClassName {
      public static void main(String[] args) {
          statement;
      }
  }
```

### Print Statements

- There are 2 types of print statements

  ```java
      System.out.print("Cursor stays on the same line.");
  ```

                                AND

  ```java
      System.out.println("Cursor moves onto the next line");
  ```

### Input Statement

- Firstly, import 'Scanner' class from 'java.util' package
  ```java
   import java.util.Scanner;
  ```
- Then create a object of Scanner class using following syntax

  ```java
   Scanner object_name = new Scanner(System.in);
  ```

  **Note:** Here 'Scanner' word on the LHS is the name of the class 'Scanner' & 'Scanner()' is the constructor method of that particular class

  - The 'System.in' part of the statement instructs the compiler to take the input from console
  - Use the **object_name** to access methods of 'Scanner' class

    - eg.
      ```java
      int num = object_name.nextInt();
      ```
    - eg.
      ```java
      String name = object_name.nextLine()
      ```
    - eg.

      ```java
      BigDecimal money = object_name.nextBigDecimal();

      //Note: BigDecimal has higher precision
      ```

* Example Program

  ```java
  public class ClassName {

          public static void main(String[] args) {

              System.out.print("Enter your name: ");
              Scanner x = new Scanner(System.in);
              String name = x.nextLine();
              System.out.println("Hi " + name + "!");

          }

      }
  ```

  ## Data Types

  - Java is a statically typed programming language, which means you need to do declare variables with specific data type before you use 'em

    1.  **Primitive Data Types**

        - **boolean**

          - Syntax :

            ```java
            bool variable_name = literal; //(true / false)
            ```

        - **byte**

          - Syntax :

            ```java
            // (unicode characters + no(s) b/w -128 to 127) (size - 1 Byte)

            byte variable_name = literal;
            ```

        - **character**

          - Syntax :

            ```java
            // (all unicode characters) (size - 2 Bytes)

            char variable_name = literal;
            ```

        - **short int**

          - Syntax :

            ```java
            // (-32768 to 32767) (size - 2 Bytes)

            short variable_name = literal;
            ```

        - **integer**

          - Syntax :

            ```java
            //(integers) (size - 4 Bytes)

            int variable_name = literal;
            ```

        - **long int**

          - Syntax :

            ```java
            // (integers) (size - 8 Bytes)

            long variable_name = literalL;

            //  example
            long x = 567817267867L;

            ```

          - **_Note_**: You need to add 'L' at the end if the long literal if it's beyond the scope of original integer value

        - **float**

          - Syntax :

            ```java
             // (Floating point no(s)) (size - 4 Bytes)

             float variable_name = literal;

             // example
             float x = 56.657f ;
            ```

          - **_Note:_** 'f' at the end is necessary

        - **double**

          - Syntax :

            ```java
            // (Floating point no(s)) (size - 8 Bytes)

            double variable_name = literal;
            ```

    2.  **Objects**

        - **String**

          - Syntax :

            ```java
            String object_name = literal;
            ```

        - **Integer**

          - Syntax :

            ```java
            Integer object_name = literal;
            ```

        - **Double**

          - Syntax :

            ```java
            Double object_name = literal;
            ```

            **_NOTE_**: object types covers almost all primitive data types (just confirm)

          - **We can use the properties of these classes using '.' operator**

            - eg.

              ```java
                  System.out.println(Integer.MIN_VALUE);
                  System.out.println(Double.MAX_VALUE);
                  System.out.println(Double.isNan(Math.sqrt(-1)));
              ```

    - **Constants**

      - Syntax :

        ```java
        final datatype CONSTANTNAME = literal;

        // 'final' is the keyword for declaring constants
        ```

      - **_Note_**: For **_global declaration_** of constant use following syntax

        ```java
        public static final datatype CONSTANTNAME = literal;

        // public - so that all the classes can access it

        // static - so that there's no need to create instance of the class in that particular class
        ```

    - **Typecasting**

      - Example

        ```java
        int a = 5, b = 2;
        ```

        - If we do a/b and store the result in a double variable we get int result instead of double

        ```java
        double x = a/b    // Result => 2
        ```

        - This is because both dividend and divisor are int this case

        - To overcome this problem we add the desired '(datatype)' in front of each member of the expression since '(datatype)' is a unary operand

        - i.e.

        ```java
        double x = (double) a/b //Result => 2.5
        ```

      - **Converting a string to a**

        1. **integer value**

           - eg.

             ```java
             String x = "100";   // 100 is a string here
             int a = Integer.parseInt(x);    // 100 is a no. here
                             OR

             Integer a = Integer.valueOf(x);
             ```

        2. **double value**

           - eg.

             ```java
             String y = "5.25";
             double b = Double.parseInt(y);
             ```

## Strings

- Some properties of string class

  - Consider the following string as a reference string
    ```java
    String str = "sohan";
    ```

  1. **charAt(** _index_ **)**

     - returns the character at specified index
     - eg.

       ```java
       System.out.println(str.charAt(3));        //a
       ```

  2. **length()**

     - returns length of the string
     - eg.
       ```java
       System.out.println(str.length());         //5
       ```

  3. **concat("** _text goes here_ **")**

     - concatenates the string passed as argument to the specified string
     - eg.

       ```java
       String z = "vaigankar ";

       z.concat(str);        //vaigankar sohan
       ```

  4. **contains("** _string_ **")**

     - checks for the presence of the string passed as an args in the specified string and returns boolean value
     - eg.

       ```java
       System.out.println(z.contains("han"));         //True
       ```

  5. **indexOf("** _string_ **")**

     - returns the index of the starting character of the string specified
     - eg.
       ```java
       System.out.println(z.indexOf("so"));           //10
       ```

  6. **toUpperCase()**

     - converts the string characters to uppercase letters
     - eg.
       ```java
       System.out.println(str.toUpperCase);
       ```

  7. **toLowerCase()**

     - converts the string characters to lowercase letters
     - eg.

       ```java
       System.out.println(str.toLowerCase);
       ```

  8. **strip()**

     - removes white spaces from the beginning and ending of the string
     - **_stripLeading()_** - removes white space from the beginning of the string
     - eg.

       ```java
       string x = "   some text here   \n  ";
       System.out.println(x.strip);
       ```

  9. **substrings(** _beginIndex_ **,** _endIndex_ **)**

     - cuts a part of the string from beginIndex (must be specified) through endIndex (optional).
     - **_Note_**: if endIndex is not specified the substring goes till end of the original string
     - eg.
       ```java
       System.out.println(z.substring(10));      //sohan
       ```

  10. **repeat(** _no_of_times_ **)**

      - repeats the string for the times specified
      - eg.

        ```java
        System.out.println(str.repeat(10));
        ```

  11. **equals("** _string_ **")**

      - checks if 2 strings are equal and returns boolean value
      - eg.

        ```java
        System.out.println(str.equals(z));      //false
        ```

## Comparison Operators

- this includes ' ==, !=, <, >, <=, >= '

## Logical Operators

- this include ' &&, ||, ! '

## Switch Case

- Syntax :

  ```java
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
  ```

## Ternary Operator

- this is kinda similar to if-else

  - Syntax :
    ```java
    exp ? if_true : if_false
    ```

## Loops

1. **while loop**

   - Syntax :

     ```java
         while(condition)
         {
             statement;
             update++;
         }
     ```

2. **do while loop**

   - Syntax :

     ```java
         do
         {
             statement;

             update++;

         } while(condition);
     ```

3. **for loop**

   - Syntax :

     ```java
         for(initialization; condition; update)
         {
             statement;
         }
     ```

4. **for each loop**

   - _for each loop_ is similar to _for loop_ but size of the list/array or basically end condition is not required and loop will visit each element one-by-one from starting index and will stop when the array/list is fully traversed
   - Syntax :
     ```java
         for(initialization :  array_name / list_name)
         {
             statement;
         }
     ```
   - eg.

     ```java
         for(int  element = list_name)
         {
             System.out.println(element*10);
         }
     ```

## Arrays

- **Properties of Arrays**

  1. **_length_**

     - returns the length of the array.
     - Syntax :

       ```java
       array_name.length
       ```

- **1-D Arrays**

  - Syntax :

    ```java
    data_type[] array_name = new data_type[size];       //for user input

                        OR

    data_type [] array_name = {value1, value2, ...};     //hardcoding values
    ```

  - **Arrays.toString(** _array_name_ **)**

    - to display values/status of array
    - **_Note_**: _import java.util.Arrays;_ to use the this function
    - Syntax :

      ```java
          System.out.println(Arrays.toString(array_name));
      ```

    - eg.
      ```java
      Scanner input = new Scanner(System.in);
      int size = input.nextInt();
      int [] array = new int[size];
      for(int i = 0; i < size; i++)
      {
          int temp = input.nextInt();
          array[i] = temp;
      }
      ```

  - There are predefined useful methods for sorting arrays and various other things in Arrays package, just make sure to import following

    ```java
        import java.util.Arrays;
        import java.util.ArrayList;
    ```

    - Here are few frequently used functions

      1. **Array Sort**

         - sorts the array in ascending order (Quick sort)
         - Syntax :

           ```java
           Arrays.sort(array_name);
           ```

      2. **Array Parallel Sort**

         - sorts array in ascending order
         - Syntax :

           ```java
           Arrays.parallelSort(array_name);
           ```

      3. **Array Equals**

         - checks if the 2 arrays are equal and returns true if they're equal
         - Syntax :

           ```java
           Arrays.equals(array_name1, array_name2)
           ```

         - eg.
           ```java
            if(Arrays.equals(array_name1, array_name2))
               {
                   System.out.println("Equal!!")
               }
           ```

      4. **Array Fill**

         - replaces all the elements of array with fill value
         - Syntax :

           ```java
           Arrays.fill(array_name, value);
           ```

         - eg.
           ```java
           String [] array = new String[10];
           Arrays.fill(array, "");       // empty character
           ```

      5. **Array asList**

         - converts array into a list
         - Syntax :

           ```java
           Arrays.asList(array_name);
           ```

         - eg.

           ```java
           List<DataTypeClass> list_name = Arrays.asList(array_name);

           //Note: data_type should be same  as that of the array and don't forget to import 'java.util.List'
           ```

- **2-D Arrays**

  - Syntax :

    ```java
        data_type[][] array_name = new data_type[row_size][col_size];       //for use input

                                OR

        data_type [] array_name = {{col1}, {col2}, ...};     //hardcoding values
    ```

  - Arrays.toString(array_name)

    - to display values/status of array
    - **_Note:_** _import java.util.Arrays;_ to use this function
    - eg.

      ```java
      System.out.println(Arrays.deepToString(array_name));
      ```

  - eg. of a 2-D array

    ```java
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
    ```

  - **_Note_**: In case of 2-D Arrays 'length' property alone gives the no. of rows, to find the no. of cols use

    ```java
        array_name[index].length

        // Here, index == index of row
    ```

- **Array List**

  - list is very similar to array but it's size can be dynamically increased / decreased unlike arrays which is fixed when declared
  - **_Note_**: _import java.util.List;_ when using list (mandatory)
  - We don't need to specify the size of the list while declaring
  - Syntax :

    ```java
        List <DataTypeClass> list_name = new TypeOfList<DataTypeClass>();
    ```

  - **_Note_**: There are many type of lists like _ArrayList_ & _LinkedList_ and depending on the list you choose, you should specify the '_TypeOfList_' and _import 'java.util.TypeOfList;_ - Here, we're refering to ArrayList. So,

    ```java
    import java.util.ArrayList;

    List<DataTypeClass> list_name = new ArrayList<DataTypeClass>();
    ```

  - **Accessing elements of list**

    - Similar to arrays , list element can be accessed by
    - Syntax :

      ```java
          list_name[index];
      ```

  - **Displaying whole list at once**

    - Actually there are many ways of doing this but the following is pretty straightforward
    - Syntax :

      ```java
              System.out.println(Arrays.toString(list_name.toArray()));
      ```

      - Basically, the above syntax first converts list to array using method 'toArray()' and then uses 'toString()' to display the entire array

    - **Iterating through a list**

      - **_Note_**: for each loop can be used here
      - eg.

        ```java
        List<Integer> list_name = Arrays.asList(5, 3, 2, 6, 3);       // initializing list values using arrays

        for(int i = 0; i < list_name.size(); i++)
        {
            list_name.set(i, list_name.get(i) * 10);    //Updating list elements, i.e. multiplying by 10
            System.out.println(list_name.get(i));   // displaying list elements
        }
        ```

    - **Nested Lists**

      - Syntax :

        ```java
            List<List<DataTypeClass>> main_list = new ArrayList<List<DataTypeClass>>();

            List<List<Integer>> main_list = new ArrayList<List<Integer>>();

            main_list.add(Arrays.asList(5, 3, 2, 6, 3));
            main_list.add(Arrays.asList(8, 3, 4, 2, 4));
            main_list.add(Arrays.asList(45, 57, 68, 97, 34));
        ```

      - To **iterate through the Nested Lists**

        - **_Note_**: The nested list is of the type 'List<integer>' and not simply 'int'
        - Syntax :

          ```java
          for(List<Integer> list_no : main_list)        //Accessing Nested Lists from main_list
          {
              for(int element : list_no)              //Accessing elements of nested list
              {
                  System.out.print(element + "\t");
              }

              System.out.println();
          }
          ```

    - **Converting List to Array**
        - Syntax :

            ```java
            int[] array_name = new int[list_name.size()];

            for(int i = 0; i < list_name.size(); i++ )
            {
                array_name[i] = list_name.get(i);
            }

            System.out.println(Arrays.toString(array_name));
            ```

    - **List Methods**

        1.  **add(** *value* **)** OR **add(** *index* **,** *value* **)** 
            - appends element to the list at specified index
            - Syntax :  

                ```java
                list_name.add(value); 
                
                        // OR

                list_name.add(index, value);
                ```

        2.  **get(** *index* **)** 
            - returns the element at specified index
            - Syntax :

                ```java
                list_name.get(index);
                ```

        3.  **set(** *index* **,** *value* **)** 
            - updates the specified index with passed value
            - Syntax :  
                    
                ```java
                list_name.set(index, value);
                ```

        4.  **size()** 
            - returns the size of the array
            - Syntax :

                ```java
                list_name.size();
                ```

        5.  **isEmpty()**
            - checks if the list is  empty or not by returning boolean value
            - Syntax :

                ```java
                list.isEmpty();
                ```

        6.  **remove(** *index* **)** 
            - removes element from the list present at specified index
            - Syntax : 
                
                ```java
                list.remove(index);
                ```

        7.  **clear()** 
            - removes everything from the list
            - Syntax : 
                
                ```java
                list_name.clear();
                ```

    - Using 'Collections' tool properties on list
        1. **sort(** *list_name* **)** 
            - sorts the list in ascending order
            - Syntax :   
                
                ```java
                Collections.sort(list_name);
                ```

        2. **reverse(** *list_name* **)** 
            - reverses the order of elements
            - Syntax :

                ```java
                Collections.reverse(list_name);
                ```

## Class and Object

- Syntax :

    ```java
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
    ```

    - **Encapsulation**
        - wrapping of data members & member functions inside a class such that not all the data is publicly accessible
        - the key idea here  is to use 'getter' & 'setter' methods for getting data from class and  setting data to class  data members and member functions resp.
        - ***getter method*** - usually combines the various fields of class and returns
        - ***setter method*** - don't return value (usually void) as it is used to set/update values of different fields of a class
        - eg.
        
            ```java
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
            ```
    - **Creating a List of Objects**
        - Syntax :

            ```java
            List<ClassName> object_name = new TypeOfList<ClassName>();
            ```

        - eg.

            ```java
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
            ```

    - ***Note***: Static methods are class methods.
        - i.e. they can be accessed directly using ClassName of the Class in which they defined inside any other class 
        - Syntax for defining : 

            ```java
            public static return_type methodeName()          
            {
                statement;
            } 
        - Syntax for calling :

            ```java
            ClassName.staticMethod()
            ```

            - Otherwise, we've to call method using instant method and to call such methods one  has to create object of the class where method  is to be called
                - Syntax for calling :

                    ```java
                    obj.methodeName();
                    ```
                - Syntax for definition: 

                    ```java
                     normal (w/o static keyword)
                    ```

  - Taking custom types as function arguments

    - eg.
            
        ```java
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
        ```

  - **Method Overloading**

    - same function name but different args (different types or different no. of args)
    - return_type  can be  same  or different, it won't matter.

    - eg. 
        ```java
        void methodOne(int x);  // Method Overloading

        int methodOne(int x):   // Not Method Overloading

        void methodOne(String x, int y);    // Method Overloading

        int methodOne(String x);    // Method Overloading

        void methodOne(int x, int y, int z);   // Method Overloading

        int methodOne(int x, double w):  // Method Overloading
        ```

  ## Method Overriding

    - Changing the definition of the method in a derived class
    - for method overriding just put @Override keyword above method definition in sub class
    - Syntax :

        ```java
            @Override
            public return_type methodName()
            {
                statement;
            }
        ```

  ## Pass by value & Pass by reference

    - search more about this topic

  ### ***Note***: Most methods in Java are 'Virtual' by default except static methods and private methods

  - ### **Inheritance**

    1. Single Inheritance
        - A single derived class is inherited from base class
        - Syntax :

            ```java
                public class Base {
                    data_members & memberFunctions();
                }

                public class derived extends  Base {
                    statement;
                }
            ```

  - **Abstract Classes**
    -  Abstract class is class of something that doesn't exist... it is more like a class of characteristics
    - Syntax :

        ```java
        public abstract class ClassName {
            body;
        }
        ```

  - **Abstract Methods**
    - when a method  is made abstract it cannot be defined or  have a body. It's designed to be overridden
    - ends with ';' and is usually declared inside abstract class
    - Syntax :

        ```java
        public abstract void methodName();
        ```

  - **Polymorphism**
    - important  stuff

  - **Constructors**
    - Constructor is a special member function which is used to initialise a object
    - gets invoked automatically when object is created
    - if parameterised constructor is defined then default constructor should be compulsorily defined
    - always public
    - name same as class name

    1. **Default Constructor**
        - Syntax :

            ```java
            public ClassName()
            {
                statement;
            }
            ```

    2. **Parameterised Constructor**
        - Syntax :
            ```java
            public ClassName(data_type var_name1, data_type var_name2)
            {
                statement;
            }
            ```
        - Syntax to call parameterised constructor :
            ```java
                ClassName obj = new ClassName(arg1,arg2);  //pass the args to the parameterised constructor
            ```

    3. **Copy Constructor**

  - **Super keyword**
    - used to access/invoke  members of base class from derived class
    - Syntax :
        
        ```java
        super.methodeName();        // that methodName can be replaced by any particular data_member or memberFunction of base class
        ```

  - **Interface**
    - interfaces are very similar to classes but interfaces are specifically used to define behaviour and  are then implemented
               
  - **final methods**
    - prevents overriding of a method in further derived classes
    - syntax:

        ```java
        public final return_type methodName()
        {
            statement;
        }
        ```
  - **final class**
    - prevents class from extending further
    - Syntax :
        
        ```java
        public final class ClassName{
            body;
        }
        ```

  - **Enumeration**
    - learn more about this