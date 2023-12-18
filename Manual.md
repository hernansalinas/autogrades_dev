Libraries description in bin folder

To perform the unit test of any function, variable or result we need to instantiate the object add_configuration, and use the following methods:

- add_configuration.append_(nameClass.nameMethod, "name of question", variable, dependence, hint)

      Example:

      - config_.append_("testVariable.test_Equalfloat","x is a float", "x", False)


- add_configuration.append_(nameClass.nameMethod, "name of question", ("name_function1",[params]),("name_function2",[params]), dependence, hint)

      Example:

      - config_.append_function("testOneOneFunction.test_Equalfunctions",\
                        "Create a function that adds two numbers", \
                        ("sum_expected",[1,1]),\
                        ("sum_test8",[1,1]) ,\
                        True, "This is a hint")


- add_configuration.append_(nameClass.nameMethod, "name of question", expected value,("name_function2",[params]), dependence, hint)

      Example:

      - config_.append_function_values("testOneValuesFunction".test_Expectedvalue",\
                        "Test of the function f", \
                        [2,1],\
                        ("sum_test",[1,1]) ,\
                        True)



where:

    - nameClass.nameMethod: This class inherits from the object  unittest.TestCase in the libraries of this program.
    - "name of question": Comment for the user to show in the html box.
    -  "variable" : Define the name of variable as string.
    - "dependence": dependence is true if the question has dependence on a previous question, or false if it doesn't have dependence
     - "hint": If the user wants to define help for the unit test. It is not necessary to define.
     
     - The function can be defined as a tuple with 2 elements, the first value is a string with the name of the function and the second is a list with the input parameters of the function
     - the expected value can be defined as a constant, list, tuple, dictionary etc.


Different methods can be used if you add new methods for the following classes:

  - testVariable
  - testOneOneFunction
  - testOneValuesFunction

You can use the documentation https://docs.python.org/3/library/unittest.html to use assert functions or define your own comparative methods.


# List and short description of classes used:
### Classes

- testVariable: This class has the methods to identify if the variables are defined, are strings or floats. 
- testOneOneFunction: This class has the methods to perform the comparison between two functions 
- testOneValuesFunction: This class has the methods to perform the comparison with some expected value and the evaluation of the function at some value

- StatePointsV1(): Define the state of each test that you perform
- add_configurations: Define the configuration for the runTest_v1 class
- html_generation: Generation of html

### Functions
- extract_message: extract one part of the error in the unit test 
- runTest_v1: run unit test, 



Recommended architecture for the files.


```Markdown

Test_labs
--------libUnitTest1.py
--------Labs
        -----Lab01
             --Lib_test1.py
             --test_1.py # it is recommended to encrypt
         -----Lab02 
             --Lib_test2.py
             --test_2.py # it is recommended to encrypt

Labs_student/
--------Labs01/notebook.ipynb 
--------Labs02
--------Labs03
--------Labs04
--------Labs05
--------Labs06

%run libs/libUnitTest1.py
%run test/test01.py
