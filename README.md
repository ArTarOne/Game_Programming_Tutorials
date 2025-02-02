# Game_Programming_Tutorials

C++ Game Programming practice using content from [Beginning C++ Game Programming](https://www.amazon.co.uk/Beginning-Programming-Premier-Press-Development/dp/1592002056/ref=sr_1_10?s=books&ie=UTF8&qid=1529356234&sr=1-10&keywords=Michael+Dawson)


## Essentials

Integrated Development Environment (IDE) for C++ : 
    
 * [Bloodshed Dev-C++](https://sourceforge.net/projects/orwelldevcpp/) (*Used by the book*)
 * Visual Studio Enterprise 2017 32/64-bit (Multilanguage)
 * [gamedev.net](https://www.gamedev.net/)
 * [programgames.com](http://programgames.com/)
    
## Notes

### Chapter 1 - Types, Variables, and Standard I/O: Lost Fortune
- **Page 9**: Employing using a Directive
    - **using namespace std** is used so that the *std::* prefix is not required when calling operations such as *cout* and *cin*.
- **Page 13**: Understanding order of operations (BODMAS)
- **Page 15**: Understanding Type Modifiers
    - *short* and *long* can be assigned when creating primitive data types. Short will reduce the amount of storage space required for a variable, whereas using *long* will increase the amount of storage space required for the variable. 
    - *short* and *long* can *int*. *Long* can modify *double* data types.
    - **Range Modification:** An integer may be *signed* or *unsigned* whilst it is created (only works for int data type). A *signed* int is one which will accept both negtive and positive values, whereas its unsigned counterpart will only accept positive values.
- **Page 20**: Defining new names for datatypes
    - **typedef** *unsigned short int* ushort;
        - keyword **typedef** is used to create a new datatype *ushort* which acts as an alias for the native type '*unsigned short int*' datatype. Allows developers to use alias to shorten the names of these datatypes.
- **Pages 23-24**: Pre- and Post-fix Value Incrementation
    - *Prefix*: ++lives
    - *Postfix*: lives++
    - In practice:
        - Where int lives = 3;
        - *int bonus = ++lives * 10;*
            - Increments a value *before* the evaluation of an expression, such that the value of the variable *lives* will increase by 1 before it is multiplied by 10. In this case lives = **4**. So *4 * 10 = 40*.
        - *int bonus = lives++ * 10;*
            - Increments a value *after* the evaluation of an expression, such that the value of the variable *lives* will increase by 1 after the evaluation of an expression. In this case lives = **3**. So *3 * 10 = 30*. The value 30 will be stored in the int variable *bonus*. After this line of code the value of the variable *lives* will increase from 3 to 4.
- **Page 24**
    - When an integer exceeds it maximum value it will *wrap around* to the lowest value.
    - When an integer is decreased below its minimum value it will *wrap around* to its highest value.
- **Page 27**: Enumerations
    - enum difficulty { NOVICE, EASY, NORMAL, HARD, UNBEATABLE};
        - Starting from the value on the left {0,1,2,3,4}
        -Initialise a variable using the following syntax: difficulty *myvar* = NOVICE; (or any other enum variable from the list).
    - enum ship{FIGHTER = 25, BOMBER, CRUISER = 50, DESTROYER = 100};
        - Value of *BOMBER* is *26* as it is equivalent to the previous value (FIGHTER which is 25) plus 1 = 26.
- **Page 29**: Strings
    - The use of *cin* to get user input only works with *strings* that have no whitespace in them (e.g. tabs and spaces). Use of streams can be used to compensate for this. **Be cautious of the limitations of strings in c++**.
    
### Chapter 2 - Truth, Branching, and the Game Loop: Guess My Number
- **Page 39**: If-Statements
    - Non-zero values (including negative values) equate to *true* in an if-statement, therefore, code will be executed within the code block. *0*, on the other hand, equates to *false* in an if-statement, and therefore the compiler will skip and avoid executing the code.
- **Page 44**: Switch Statements
    - Strings **do not** work with switch statements in C++. Integers, chars and enumerators do however.
- **Page 48**: Do-while Loops
    - Guarantees that the loop body (within the *do* body) is executed *at least* once.
- **Page 52**: *Continue* Reserved / Keyword
    - Use the C++ reserved word *continue* to skip the value of an incrementing variable in a while loop, as the program goes straight to the top of the loop (therefore, the statement *cout << count << endl;* will never run).
- **Page 57**: Understand the Order of Operations
    - In C++, logical NOT (!) has a higher level of precedence than logical AND (&&), which has a higher level of precedence than logical OR (||).
- **Page 60**: Random Number Generation
    - *cstdlib* library for the use of the rand() method.
    - *rand()* function will generate a random number, however it will start from the beginning of a large book of predetermined random numbers. *Seed* the random number generator with the following piece of code: *srand(time (0))*. The function uses the current time to generate a unique number that is used to change the starting position of the random number generator *every time* the program commences. **IMPORTANT: Without seeding a random number generator, the same series of random numbers will be generated by the program every launch**.
- **Page 61**: Random Number Range 
    - Generate a range of random numbers by using the modulus operator (%).
    
### Chapter 3 - For Loops, Strings, and Arrays: Word Jumble
- **Page 71**: For-loop structure
    - for (*initialisation*; *test*;*action*){
        statement;
    }
- **Page 75**: Nesting for-loops
    - Inner-most for loop will be executed in full for each iteration of the outer loop.
- **Page 76**: Object Properties.
    - *Data Members* are the object *instance variables*.
    - *Member Functions* are the object *operations*.
- **Page 79**: String object initialisation
    - Strings can be instantiated in three different ways:
        1) **string word1 = "Game";**
        2) **string word2("Over");**
        3) **string word3(3, '!');** (*Equivalent to "!!!"*)
- **Page 81**: Empty Strings
    - *string::npos* is a special constant used as a condition for an empty string. 
- **Page 87**: C-Style Strings
    - C-style strings (cstrings) are character arrays that terminate with a *null character*. Unlike strings, c-style strings have a *fixed* length. In C++, cstrings work seamlessly with strings.
- **Page 92**: Enumerator trick
    - *Enumeration lists* can be used as a convenient way to store the number of elements. can be used in several situations, such as defining the amount of difficulty levels within a game.
    - Example: enum *difficulty* = {EASY, MEDIUM, HARD, **NUM_DIFF_LEVELS**}. NUM_DIFF_LEVELS = *3* which is equivalent to the amount of game difficulty levels. 

### Chapter 4 - The Standard Template Library: Hangman
- **Page 100**: Vectors
    - Dynamic arrays (similar to ArrayLists in Java). An array that can grow or shrink as required.
- **Page 107**: Iterators
    - Two main types of iterators: *iterator* and *const_iterator*
    - An *iterator* is a value that identifies a particular element within a container (such as a vector list). They are not elements but are used to refer to them.
    - Analogous to a post-it note that can stick to an element within a container.
    - Once assigned to an element within a container, the iterator can be used to access or modify them.
    - A *const_iterator*, unlike an *iterator*, cannot modify the element to which it refers. The const_iterator has read-only access unlike its *iterator* counterpart, therefore it is much more limited, but safer to use when navigating around a vector.
- **Page 109**: *iterator/const_iterator end()* member function
    - The end() member function returns an iterator than is *one past* the last element of the vector.
    - Dereference Operator (*) is used to display the value that the iterator currently refers to (and not the iterator itself).
- **Page 110**: Changing the value of a vector element
    - A vector element can be changed using an iterator (not a const_iterator) with the following syntax: **myIterator = "my_string";* this will modify the value of the element the iterator currently refers to.
    - **Accessing member functions of elements using an iterator**:
        - Dereference the iterator and surround with parenthesis as such: *(*myIterator).size()*. This will call size() member function belonging to the string object that the iterator currently refers to.
        - Alternative syntax for *(*myIterator).size()* is *myIterator->size()*. Both get the amount of characters from the string object, however, the latter is prettier.
- **Page 112**: Standard Template Library (STL) Algorithms
    - STL Algorithms can be used to randomize, sort and merge highscore vectors.
- **Page 114**: Random Shuffle
    - *random_shuffle(starting_index, ending_index);*: A useful method for shuffling elements within a container.
- **Page 117**: Reallocating memory within vecotr lists
    - *capacity()* vector member function is used to check how many vector elements the vector list can store. 
    - *size()* vector member function is used to check how many elements are currently occupying the vector list.
    - If the amount of elements currently within the vector exceeds the capacity, the capacity is doubled automatically as the program reallocates memory.
    - *reserve()* member function is used to increase the capacity to a container with a set value.
- **Page 118**: *Sequential* versus *Associative* containers
    - Sequential containers allow you to retrieve values in a *sequence*, whereas associative containers allow you to retrieve values using *keys*.
    - A vector is an example of a sequential container.
- **Page 119**: Planning your Programs
    - Using Pseudocode and Stepwise Refinement (Refining steps to make them more specific).
- **Page 125**: *If I can use the subscripting operator, ([i]), with vectors why would I ever need to use iterators?*
    - There are several reasons for using iterators over subscripting for values within a sequential container (such as a dynamic vector array):
        1) Many of the vector member functions (operations) require iterators (such as insert() and erase()).
        2) Standard Template Library (STL) algorithms require iterators.
        3) You cannot use the subscripting operator with most of the STL containers, therefore you are going to have to use iterators sooner or later.
        
### Chapter 5 - Functions: Mad Lib
- **Page 131**: Declaring, Defining and Calling Functions
    1) Declare functions by using *function prototyping*. This is *before* the main() method.
        - **Format:** return_type| function_name | (parameters)
        - You do not have to explicitly mention parameter names in the function declaration, however it is a best practise to do so to make the code clearer and easier to decipher.
    2) Define functions *before or after* the main method. Defining functions before calling them allows you to skip the declaration stage. Defining functions includes writing the code within the code body of curly braces.
    3) Calling the function takes place *within* the main method. When calling methods parameters are filled with *arguments* that allow the function to run. This is a process commonly known as *abstraction*, as the entire function does not have to be written manually within main - without concern for the physical write-up of the method.
- **Page 137**: Encapsulation
    - No variable created within a function can be accessed outside of the function. Details of the function is hidden as the details are *encapsulated* in a function. This heightens the effect of abstraction.
- **Page 138**: Scopes
    - Two main scope types in C++. *Global* and *Local*.
    - Everytime a double curly brace is used this defines a new scope for the program. Any variables created within this scope is not visible to code outside; therefore, the variable falls under a *local* scope. 
    - Functions and nested functions (using curly braces within a function defines another scope).
- **Page 147**: Default Arguments
    - Default arguments are specified within *function prototypes*, e.g. (int asknumber(int high, int low = 1);).
    - Once you specify a default value for a value in the function prototype, ALL remaining values must be assigned a value (e.g. void setDisplay(int height, int width, **int depth = 32**, **bool fullScreen = true**;)).
    - When calling functions with default values. Once you omit a value you must omit the remaining default values from the function call.
- **Page 150**: Overloading Functions
    - Create functions with two functions with the same names with different *parameter lists*.
    - If the *return type* is the only varying factor between two functions with identical names, this will throw an error.
- **Page 152**: Function Inlining
    - A code tweak technique used to boost performance of code.
    - Makes a copy of a method when the function is called so that the profiler does not have to navigate to the function and run code outside of the main() method for consecutive calls.
    - Very effective when running small one or two line code statements. Inlining with large code is ineffective, hindering the performance of the program, since the code is duplicated.
    - The program will decide whether it is beneficial to use function inlining, or whether it is better to simply execute the code by navigating to the function itself. If the complier does not think that inlining will boost performance, it will not inline the function call.
    
### Chapter 6 - Tic-Tac-Toe
- **Page 162**: References
    - A reference provides an alias for a variable. 
    - Use the *reference operator* '&' to create a reference that can be used for another variable.
        - Such as &mikesScore = myScore;
    - You can't assign a reference to another variable if it has already been assigned to one.
- **Page 166-167**: *Passing by Value* Versus *Passing by Reference*
    - Passing by value is transient. It expires once the function ends and only persists within the scope of the function.
    - Passing by reference persists throughout the program. Continuing after a function returns back to the main method.
    - Passing by value copies the variable, whereas passing by reference is efficient as copies are not made; access to the variable is granted.
- **Page 173**: Returning a reference
    - Never return a reference to a local variable from a function outside of main, as the variable does not exist outside the scope of the function (therefore it will not be reached by main()).
- **Page 183**: Making changes to the game board
    - Remove 'const' and call by value to make a copy of the game board that is modifiable. The variable itself is safeguarded from change.
    
### Chapter 7 - Pointers: Tic-Tac-Toe 2.0
- **Page 193**: Creating and using Pointers
    - Declare, initialise and assign pointers to values
        - Declare a pointer with the *null pointer* by setting it to zero: *int* pScore = 0;*. Stating the type of address it can store e.g. string int, char etc. 
        - Assign a pointer to the address of a variable using the *address of*: *pScore = &score;* 
            - Assigns the pointer *pScore* to the memory address of the variable *score*.
    - Retrieve values from a pointer by dereferencing it with *, such as *pScore, which refers to the value stored at the memory address that pScore points to.
    - Modify a value using a pointer by using the dereferencer such as: *pScore += 500;
- **Page 195**: Dereference
    - Used to retrieve the value from a pointer. 
    - **pScore* means 'the object to which *pScore* points'.
    - Never dereference a null pointer.
    - Unlike references, pointers can change what variables they are assigned to during the duration of a program.
        - Simply reassign a pointer using this syntax = pScore = &newScore;
- **Page 196**: Accessing the member function of objects using pointers
    - Use the dereference operator (*) and call the the member functions in the same two ways as an iterator:
        1) (*pStr).size()
        2) pStr->size() **No dereference operator required**
- **Page 198**: Constant Pointer
    - A pointer that can only point to the object which it was initialised to point.
    - Use *const* keyword *after* the type declaration such as: __int* *const* pScore = &score;__. Must be initialised **fully** at the start with the address.
    - Constant pointer **can** change the value to which it points such as: pScore += 500;
    - Constant pointer **can not** change the address of the object to which it points, such as: pScore = &anotherScore is illegal.
    - Can't point to a constant variable.
- **Page 199**: Pointer to a Constant
    - A pointer that can change the value of the object that it is assigned to.
    - Use *const* keyword *before* the type declaration such as: __const int* pScore;__
    - Constant pointer **can not** change the value to which it points such as: pScore += 500; is illegal.
    - Constant pointer **can** change the address of the object to which it points, such as: pScore = &anotherScore
- **Page 200**: Constant Pointer to a Constant
    - Combines the restrictions of a *constant pointer* and a *pointer to a constant*
    - Declaration: **const int* const pBONUS = &BONUS;**
    - Constant pointer **can not** change the value to which it points such as: pScore += 500; is illegal.
    - Constant pointer **can not** change the address of the object to which it points, such as: pScore = &anotherScore is illegal. 
- **Page 207**: Dangling Pointers:
    - A pointer to a *non-existent* object is known as a *dangling pointer*. An invalid memory address such as this, may be caused by deleting an object to which a pointer pointed. 
    - Derefrencing such pointers can lead to disasterous results in the program.
    - To overcome this potential problem in your software code, ensure that you do not return a pointer to a local variable.
- **Page 211**: Relationship between Arrays and Pointers
    - Array names are essentially *constant pointers* (pointers where you can modify the value but **NOT** the address of where the pointer points).
    - By using the *dereference operator* (*) with the array name such as *myArray will allow you to automatically display the element at position 0 in the array. Increment this value such as *(myArray + 1), to output the second item in the array container (at position 1); therefore equivalent to myArray[1].

### Chapter 8 - Classes: Critter Caretaker 
- **Page 220**: Class Structure for object creation (analogous to a blueprint)
    - A C++ object is composed of the following:
        - Class definition
        - Constructor prototype
            - Accepts default values.
        - Constructor definition
            - Occurs outside of the class definition .
            - Use the prefix *class_name::class_name()* (*::* is the *scope resolution operator*).
        - Data member / instance variables
        - Data functions / operations
            - Member function prototype
            - Member function definition 
                - Occurs outside of the class definition.
                - Use the prefix *class_name::myFunction()* (*::* is the *scope resolution operator*).
- **Page 223**: Instantiating Objects from Classes
    - Simply use the syntax: *ClassName myObject;*
    
- **Page 224**: Using Constructors
    - A constructor saves a lot of time when instantiating new objects from a class template, as it provides objects with the values upon creation, rather than manually setting individual instance variables.
    - It is illegal to use a return type for a constructor definition.
- **Page 226**: Member Initializers
    - Use these to set variables in the constructor as a quicker way such as - Critter::Critter(int hunger, int boredom): m_Hunger(hunger){}; || Same as: Critter::Critter(int hunger){ m_Hunger = hunger;};
- **Page 230**: Constant member functions
    - A *constant member function* cannot modify a data member / instance variable of its class or call a non-constant member function of its class - used to protect variables from being modified and altered unintentionally; also makes your intentions clearer to other programmers.

### Chapter 9 - Advanced Classes and Dynamic Memory: Game Lobby
- **Page 247**: Aggregation Relationship
    - Combination of objects, such that one is part of another.
    - An aggregation is a *has-a* relationship, for example, a critter *has-a* name, or a *DragRacer* class that has an *engine* data member (instance variable) that is an *Engine* object. Or a *Zoo* class that is a collection of *Animal* objects.
    - vector<*datatype*> m_Critters. (Create a vector / arraylist called m_Critters)
        - m_Critters.reserve(int spaces);. *Reserve* function is used to allocate space in memory for the amount of objects specified as *spaces*.
- **Page 251**: Friend Functions
    - Can access any member of a class of which is a friend. Create a friend function by listing the function as a *function prototype* within the specified class with the *friend* keyword. Repeat the function prototype outside of the class as a global function *without* the friend function before providing the concrete function definition.
    - Friend functions can access any data member / instance variable of the class even though it is not an official member function of the class; therefore, the function may access private data members of the class.
- **Page 251**: Overloading Operators
    - Operator overloading allows developers to give meaning to built-in operators and customise them with new types that you define.
    - Use the synatax: *operatorX*, where *X* is the operator you wish to overload. For example: ostream *operator<<*(ostream& os);
- **Page 252**: Dynamically Allocating Memory
    - Understand the differences between these two types of memory data structures.
        - **Stack**: When declaring a variable, C++ will allocate the necessary memory for it. When the function that the variable was created in has ended, C++ freed the memory.
        - **Heap** (free store): Memory that persists independently of the function in a program. Programmer must manually free this memory to improve the efficiency of the application. Allows developers to use only the amount of memory you need at any given time. A game that consists of 100 enemies can be allocated the required memory at the start of the game and manually freed at the end. A heap allows developers to gain access to an object in a function even *after* the function ends (without having to return a copy of the object).
- **Page 254**: The *new* operator
    - The *new* operator dynamically allocates memory on the heap and returns its address. 
    - Use the *new* operator followed by the data type of the value that you wish to reserve space for. 
    - For example: int* pHeap = new int;
        - The *new int* part of the statement allocates enough memory on the heap for a single integer and returns the address of that chunk of memory on the heap.
        - The *int* pHeap* part of the statement creates a pointer called *pHeap* which points to the memory address location returned on the heap (returned by *new int*).
        - The pointer *pHeap* can now be used to manipulate the chunk of memory that has been reserved for a single interger variable.
        - *pHeap* points to a piece of memory on the heap, not the stack.
    - Memory can be initialised on the heap at the same time you allocate it by placing a value in parenthesis after the datatype declaration, such as: *int* pHeap = new int(10);* which allocates a chunk of memory on the heap for an int variable and assigns the value 10 to it.
    - Functions that return a pointer to memory addresses are very efficient, as no copies of the object are made. They can be accessed and modified by other functions (such as main()).
- **Page 255**: The *delete* operator
    - Once finished using memory allocated with the *new* keyword, the *delete* keyword must be used to free the data from the heap for future use.
    - **IMPORTANT: EVERY 'new' SHOULD HAVE A CORRESPONDING 'delete' KEYWORD TO RELEASE THE MEMORY!**
        - Write the *delete* statement at the same time as initialising the *new* keyword.
        - After deleting, assign 0 to the variable to remove *dangling pointers*, and assign them to point to a new, valid chunk of memory.
- **Page 264**: Copy Constructor
    - Used to avoid a *shallow* copy when an object is *passed by value*. Essentially this means that the pointer and the copied object both point to the same address containing the string value; they both share references to the same chunks of memory, a change in one object will be reflected in another. When the object is destroyed the address containing the string object is also destroyed from the heap. Resulting in a dangling pointer!
    - To fix this issue a *deep* copy must be made. Essentially this means that the copy constructor creates a new object pointing to *another* memory address which contains the same value.
    - When you have a class with data members / instance variables that point to memory on the heap, you should consider writing a copy constructor that allocates memory for a new object and creates a *deep* copy.

### Chapter 10 - Inheritance and Polymorphism: BlackJack
- **Page 282**: Base Class (Superclass) vs Derived Class (Subclass)
    - Derived class inherits data members / instance variables and data functions / operations from the superclass.
- **Page 286**: Using the *public* keyword
    - *class Boss : public Enemy*. The *public* keyword is used to state that the public data members within the base class are passed to the derived class via inheritance.
- **Page 290**: Base Class Member Functions
    - Extend the functionality of the member function in the base class by overriding the base class method. *Explicitly call* the superclass of the member function within the derived class equivalent of the same member function, and add more content.
    - Example, within the derived class *Boss* 
            - **void attack() const**{**Enemy::attack()**; cout << " And laughs heartily at you.\n"; // override with additional functionality!}
- **Page 291**: Polymorphism
    - A member function / operation that produces different results depending on the *type* of object for which it is being called.
- **Page 294**: Virtual Member Functions 
    - Pointer: Enemy* pBadGuy = new Boss();
        - Structure of pointer declaration: <*Pointer Type*>* pointer_Name = new objectBeingPointedTo();
        - Where the Enemy class is the base class, and Boss is the derived class. The member function void taunt() const; will output results for the *pointer type*: this is *early binding*. Using the *virtual* keyword to create a member function: void virtual VTaunt() const; will result in an output that is called based on the *type* of object being pointed to, not fixed by pointer type: this is *late binding*.
        - **If you have any virtual member functions in a class, you should make the destructor virtual, too!**
- **Page 296**: Abstract Classes
    - *Pure virtual functions* are virtual member functions of a class that end with an equal sign and a 0. Such as: *virtual void Greet() const = 0;*. They are used as a template for the derived class. Pure virtual functions are not defined in the base class. For example, subclasses will find it useful to use the greet class for custom uses, rather than define the concrete definition in the superclass: e.g. A lion roars and an orc grunts.
    - When a class contains at least **one** pure virtual function, the base class is known as an *abstract class*.
    - Abstract classes can be used as the base class for other functions, but it **cannot** be used to instantiate objects!
- **Page 300**: Creating C++ Projects
    - C++ code can be organised into projects with the following structure:
    - **Class Files**: Both header and implementation files constitute a tidy wat of storing a single class.
        - Header Files
            - *Preprocessor directives* which begin with # such as: #ifndef CRITTER_H, #define CRITTER_H and #endif. Together they tell the C++ compiler not to include the Critter definition in your project if it has already been included.
                - #ifndef: If CRITTER_H is not included in the list of directives, the program should skip all of the code that follows, up to an end marker.
                - #define: Include the definition of the CRITTER_H class to the list of symbols.
        - Implementation Files: Contains the implementation for header file functions. Can also include definitions for variables and static members in an implementation file. 
            - Syntax: *#include "Critter.h"*. By using this syntax, it is as though you have manually copied and pasted the code from the critter.h file.
    - Application Files: Contains the main function to execute code.
- **Page 304**: Designing Games
    - Map out *all* classes on paper.
        - Include brief descriptions of each class in a table with the structure:  *Class*; *Base Class*; *Description*;
        (Base class states the superclass for the current class).
    - Draw an inheritance hierarchy for all the classes involved in the project.
    - List data members / instance variables and member functions / operations that you think the classes will have, along with a brief description of each (no need to rewrite the inherited data members). Table format: Members (data members and member functions); description;
- **Page 317**: Type Casting
    - *Type Casting* is used to convert one datatype into another one. One way to achieve this is by using the keyword *static_cast* to return a value with a new type from a value of another type. Specify the type you want between the < and > followed by parenthesis of the value from which you wish to get the new value. For example: *static_cast*<*double*>(5);
    
## TroubleShooting
