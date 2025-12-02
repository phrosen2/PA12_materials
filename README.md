# PA12: Binary Search Trees
## Description/Instructions:
* Your program will take 2 arguments, an input file name and a word to print the depth of as described below.
* You are to write a program that reads a text file (the first argument), finds all the words in them (removing punctuation as below), stores the unique words in sorted order inside a Binary Search Tree and prints out the depth of a requested word (the second argument) in the Binary Search Tree followed by all the words in alphabetical order with the count of how often they appear next to it.
  * The words should be converted to lowercase and only one instance of each word. The punctuation that should be removed include  `.,;?!()[]`
  * You should not store any numbers.
* To keep the list sorted, you should write a binary search method to figure out whether the word is already stored and where to place the word if it is not. This is a requirement.
* For output, the program should print the words found in the text file in alphabetical order and the depth of the word requested.
* If the word was not found, you should return -1.


## Suggested Classes and Structure:
You should probably have your classes and general structure of your program look something like this:
* BST (stands for Binary Search Tree) Class (to hold the tree/nodes)
  * A constructor
  * A deconstructor (so you can delete all nodes)
  * Pointer to the term (as described below)
  * Pointer to the left BST (which is another BST.. acts as a node but is a tree itself)
  * Pointer to the right BST (which is another BST.. acts as a node but is a tree itself)
  * add function
  * getDepth function
  * print function
* Term Class (to hold the terms you find)
  * A constructor
  * counter instance variable
  * string that holds the word
* Various getters/setters for the two above


## Binary Search Trees:
The following is heavily borrowed from https://www.softwaretestinghelp.com/binary-search-tree-in-cpp/.

**Rosen note:** above resource seems decent as an overview, but some of the algorithms have typos/mistakes. I've done my best with the one below to make it consistent. If you are worried about any of the rest, we should talk through it as a class.

Your binary search tree will have to have the following methods with the following algorithms:
```
Insert(node, data)
  Begin
    If (node == null)
      return create node
    Else If(data == node->data)
      increment that node’s count by one
    Else If(data > node->data)
      node->right = insert(node->right,data)
      return node
    Else If(data < node->data)
      node->left = insert(node->left,data)
      return node
  end	
```


##Sample Input/Output:
* Using test.txt file as a test file and running the command ./PA12 test.txt test should yield the following output:
```
3
a 1
are 1
great 1
is 1
small 1
test 2
this 1
wonderful 1
```


* The words are the words in the file and the numbers are how often the words show up.
* Note that if you construct your tree correctly, "this" will have a depth of 0 and that "test" will have a depth of 3.

## Hints/Advice: 
Here are some things to keep in mind:
* Pointers do NOT point to NULL by default. The reason for this is the zero overhead principle. (C/C++ don't do actions that take runtime costs unless explicitly asked to.)
  * This is the same reason why arrays don’t check for out of bound errors.
* The head pointer should always point to the front of the BST. All nodes are treated as it’s own BST.

## Example Inputs/Outputs:
All of the example files can be found in the tests folder. Note that the first line in the outputs is not actually a part of the file, and is used as a description of what the output file is. Your code should output that into std::out.



## How to turn in:
1. git add .
2. git commit -m "your commit message"
3. git push

- reminder to check the autograder on github after your submission.

## Grading Criteria:
test1: Runs the example  ./PA12 test.txt test
test2: Runs with another file. This time, is an excerpt of Menghini’s favorite Star Trek TNG episode, The Inner Light using test2.
test3: Runs with file. This time, is an excerpt of Menghini’s favorite Star Trek TNG episode, The Inner Light using test3.
