# Harvard - CS50

CS50 is the introduction course for computer science students. Originally I wasn't really planning to take it as I'm kinda in an akward position. On the one hand I've been programming quite long and have been working in the Game Industry as a programmer since about 2 year. On the other hand I'm determined to retouch my basics to build myself up from the bottom up. The reason for doing so is that i believe that I come from a non-traditional computer science background and would like to formalise it more in order to make sure that I'm having the right foundations. Missing these fundamentals clearly shows when I fail a simple coding test, while applying for a company.

Therefore it is in my best interest not to skip any course and just go with the flow. It will however allow me to go really quickly through the lectures of courses like this but I should at least go through them. In this document I'll collect my notes and thoughts on the course.

# Week 0 + 1

The first 2 weeks were about kicking the course of with a bang. And seriously, they seem to really do a complete performance during those lectures. With prizes, guest speakers, video's, and what not. It's really fancy and way bigger than I ever got educated, hehe. I suppose it's not a bad way to try to make learning fun, as it should be after all.

Scratch was firstly introduced and later (week 1) the knowledge that was build in scratch (week 0) got transferred to C. They used a lot of side-by-side comparisons on how it is quite similar, and that it all is not that scary, which is true in a sense. It's all still quite high level, but they touch more core knowledge here and there. There is the quick introduction to command line, make, clang, processes, threads, binary, decimal, bytes, bits and algorithms.

In week 1 C got introduced. Students learned the syntax, but it was all still quite high level, especially as a small cs50 module was used to hide gore details such as char pointers to represent strings. A lot of I/O behaviour was also abstracted a way so that students can easily ask a string or number from the user and get it back. There was also a quick and high level overview on the compilation process, practically shown via Clang.

There was some quick command-line fu but nothing fancy and more just core basics. So far so good, and perhaps boring. However I do enjoy the lessons as they are presented in quite a fun way and they have a lot of extra's that make it still worthwhile watching. I do however look forward to the excercices, and hope that the hacker challenges allow me to go as far as I want.

# Week 2

In week 3 we learned about bugs, functions and data representation. This teached about primitive types in C and how float has only a finit amount of possibilities, making it impossible to represent numbers very accuratly when requiring to much detail. ALl in all, it was still rather basic;

I almost forgot, but compilers and their linkers and assemblers also got discussed. We also learned about how to use make in an easy way and how it uses clang automatically with the correct flags when we use `make <program>`. It does surprise me how much job interview questions this first week already answers, if I think back of all the job interviews I did, haha.

# Week 3 + 4

+ Command line arguments, given via the main function `(int argc, char* argv[])`;

## Algorithms

Algorithms were introduced and we started with sorting and search. These are fundamental issues and thus quite a good start. Funny enough I also wanted to review these recently for future job interviews, so it's nice to have them available.

### Sorting

We saw 4 sorting algorithms.

+ Bubble Sort: It has a worst-case working time of O(n^2), and O(1) space requirements

  	 For each position A, starting from the last element until the second
	     For each position B, starting from the first element until the element at position A-1
	     	If the element at position B is bigger than the element at B+1
		   Swap the elements of B and B+1

+ Selection Sort: It has a worst-case working time of O(n^2), and O(1) space requirements

  	 For each position A in a collection
	     Go through all elements, starting from position A uptill the last element (inclusive)
	     Swap the smallest element found with the element on position A
	     
+ Insertion Sort: It has a worst-case working time of O(n^2), and O(1) space requirements

  	 For each element A, starting from the second element uptill the last element (inclusive)
	     For each element B, starting from A-1 until the first element (inclusive)
	     	 If B is smaller than A
		    store A as the element on the right side of B
		 Otherwise move B one position to the right and continue the search

+ Merge Sort: It has a worst-case working time of O(n*log(n)), and O(n) space requirements

  	The Merge Sort algorithm consists of 2 steps:

	1) Recursively divide the collection A in 2 pieces (B & C), until you end up with single elements
	2) In the role back phase you will merge it back into a single collection:
	     For each position i of collection A:
	     	 Do B and C both still contain elements?
		    Pop the smallest element from the first element of B and C and store it at A[i]
		 Otherwise pop the first element of whichever collection that still has elements

### Searching

+ Linear search: Working time of O(n) and O(1) space requirements

  This is the naive approach to find a number and simply consists of going through each element,
  until you found the one that you were looking for;

+ Binary Search: Working time of O(log(n)) and O(1) space requirements

  This is a very quick algorithm, but relies on the fact that your collection is sorted,
  why will be clear once I gave the pseudo code.

      	   + Start with a min and max value that are equal to
	     the first and last position of your SORTED collection;
	   + Compute your current position based on the average of the min and max value;
	   + If the element at that position is equal to your element,
	     you have found it and can stop;
	   + If however it is not equal:
	      + Is the element smaller than what you're looking for?
	         -> Equalize the max value to your current position minus one;
              + Otherwise equalize the minimum value to your current position plus one;
	   + Repeat this process until you found the value AND as long as your min value
	     is less or equal to your current value;

## Shellshock

Shellshock relies on an old bug in Bash, that's recently patched. It works like this:

  + Environment variables get exported (and evaluated) to child bash processes;
  + Functions get exported in environment variables as a smart hack,
    to allow them to be exported as well;
  + Functions get recognised in quite a lax and dodgy way;
    + it will evaluate the entire environment variable's value, if it recognises it as a function, even the part after the termination character `;`;
  + After doing that you can start a new child process, it will load & evaluate all
    exported envirioment values at that point, which will mean it runs your evil code;

As it's now patches you can't do it anymore. I did however question this and wondered why it couldn't be easier.

   > Why wouldn't you simply run the code in the background by appending your code with `&`?
     Your code would still be linked to that session, which means it would stop
     when you stop that session;

   > Why not execute that code directly via `bash -c` ?
     That's not possible as calling shell code is nog legal,
     you can only call commands (such as executables);

## Trusting Trust

This was a fun short intermezzo, where the borders between philosophy and software engineering were quite blurry. The moral of the discussion/article was that you can't trust code that you haven't written yourself. For example if you download a binary to compile your source code, how do you know that it doesn't inject a backdoor that it can misuse in the produced binary.

This is one of the many reasons why I think code should be open source, so that there at least a possibility to detect malware code such as this. Ken Thompson who wrote the paper "Reflections on Trusting Trust" proposes that we need to change the way we present misuse of software/computers more like pitty theft or driving drunk, rather than praizing such as abusers as whiz kids. I certainly can agree with this as the world won't get better from a bunch of Black Hat hackers abusing the world as they seem fit.

## Pointers

Pointers were explained, as the fact that it's a an address that points to an address in memory, which is usually stored as a stack variable. Therefore if you compare 2 c-strings which are pointers that point to the address of the first character of that string, you will get a false result if they are in fact in 2 different memory locations. This is probably not intended and instead you will need to compare the strings character per character, or even better, use STD functionality such as strcmp.

Pointers can be dereferenced via the asterix `*` character and can be created from a variable via the address `&` character.

You can apply arithmetic to pointers, and for example go to the next memory location like this: `a+1`. This is in fact what happens under the hood when you use the array syntax. Therefore `a[1]` is the same as `*(a+1)`. As it respects the rules of number arithmetic you can also do `*(1+a)`, which is why you can also do `[a]1` instead of `a[1]`. Note that I have never seen anyone doing this in the wild, and I think it would be seriously frowned upon.

Pointers are very poweful, which means they are also very dangerous. You can dereference any pointer address, even if you haven't allocated it yourself. If you dereference a pointer that has not been allocated, you get undefined behaviour, usually resulting in a crash.

## Heap Vs Stack

Because they talked about pointers, they were also quickly touching the subject of Heap Vs Stack.

  + The stack is all your local variables that get automatically removed from the stack when you leave their scope. The stack has a finit amount of memory and can be overflown when it gets full, resulting in undefined behaviour which is usual a crash. This can for example happen when you have a recursive function without a base case;
  + The heap is about dynamic memory and has to be managed by the programmer. It can be allocated via `malloc` or `calloc` and HAS to be released via `free`. Not doing so will result in a memory leak. When allocating memory with malloc you will get a pointer as result, which points to the beginning of your freshly allocated memory;

## Struct

Structs allows us to define a more complex type which can cosists of multiple values of the same and different types. The syntax for defining a new type is `type value name`. The syntax for defining a struct is `type struct tag_name { ... } alias_name;` Note that you don't need the tag_name, but in that case the struct won't be able to refer to itself within its own definition.

## Binary Vs Hexadecimal

They also explained that Hexadecimal is a number system that has a base of 16. Which means that with a single character you can have: '0,1,2,3,4,5,6,7,8,9,a,b,c,d,e,f', having a total of 16 different posibilities. Which means that you'll go from f to 10, which is equal to 16 in decimal.

A nible is 4 bits, which means that you have 2 nibles in a byte. A byte can therefore contain 256 different values (2^8). 4 bits can have 16 different values which means that you can represent it with a single hexadecimal character, which means that a byte can be represented by 2 hexadecimal characters.

It is convention to use the `0x` prefix to show that you are using hexadecimal numbers, while you use the `0b` prefix to show that you are using binary numbers. We therefore know that the values of a byte can range from `0x00` all the way up to `0xff`.

## A quick intro to file formats

Finally it was explained that file formats such as BMP (bitmap), can be recognized by software because of their conventional file header, which consists of a continues serious of byte that are layed out according to a predefined layout. This allows the software to get all the inforamtion it needs to know about the BMP file in order to pare it.

## fin

Finally GDB was also explained, which on mac has been replaced with LLDB. This allows you to debug your (c) programs as long as you provide the (debug) symbols for it.

Overall it has been a fantastic course to follow so far. And it's really cool as I'm also making a Lisp implementation in C, following [this awesome book](http://buildyourownlisp.com). Doing this course and that book together really gives me a much better understanding of C, while entertaining me!

# Week 5 + 6

A string was finally explained and how it works in C. It's an array of characters (type char, 1 byte) which is either on the stack (static) or heap (dynamic).

Therefore `malloc` was also highlighted once again, with a warning sign that every malloc should have a matching call to `free`.

Valgrind is a UNIX utility that can help with detecting memory leaks and buffer overflows. A memory leak occurs when memory that got allocated on the heap, never got freed, for whatever reason. A buffer overflow (and underflow) happens when memory gets touched beyond the boundaries of an array you own. This will crash your program with a segmant fault if your lucky and touch unwanted memory of your program if you're unlucky. Again, valgrind might be able to help with this.

The heap grows down and the stack grows up. If they meet each other you're out of memory.

The stack contains all the local variables. This also contains your parameters of the function you're in and the return address to the instruction of the callee, so that the function can continue executing where it left, when the function you're in is finished.

Therefore it can be very dangerous when you have buffer overflows/underflows as those return addresses could be overwritten so that a hacker can run her malicious code. I studied such attacks before in a course about Software Security. I should make a quick summary about such attacks in another document.

## Linked lists

An array is cool, but the problem is that it takes a fixed amount of memory. One solution could be to reallocate that array whenever you need it bigger or smaller, but this would become quite an expensive routine if you need to do it regularly.

A linked list is another data structure which solves this issue as it grows in a constant manner. It achieves this by working with nodes that reference the next node in the list. Therefore you move through the list by accessing pointer to the next node in the current node.

  	 typedef struct node
	 {
		T value;
		struct node* next;
	 }
	 node;

It's however not well suited for random access and therefore you should always add to the front of the linked list whenever possible, rather than in the middle or the end.

Removing is very cheap as it only involves finding the node to be deleted and than reassining its next pointer as the next pointer of the previous node (its parent).

## Hash Table

A hash table is represented by an array and therefore has a fixed capacity. In case you want multiple elements per hash you can store a linked list of values in each slot, rather than a value on its own. This way you're achieving really good performance for accessing, adding and removing elements without to much bad trade-offs.

By doing all of this it combines the best of both worlds. Resulting in practical constant timing for Search, insertion and deleting, while having linear space requirements.

## Trie

Other names for a trie are: digital tree, radix tree or prefix tree.
It's an ordered tree data structure that is used to store a dynamic set or associative array where the keys are usually strings.

An example:
     	       -> G -> E -> L -> A
             /
     	 -> N -> I -> E
       /
     A -> A -> R -> O -> N

An associative example would be where each node has 26 possible children (the alphabet) and a boolean that's set to true whenever all letters that you followed to get here form a word. So in the example above that would mean the the boolean would be true for the letters A, E and N on the complete right. These would indicate that we're having three words in our collection: Aaron, Anie and Angela.

## Stack

A stack is another data collection which can be represented by an Array, a linked list and other types of primitive data collections. It works in a "Last In First Out" principle". This means that whatever you add last, you'll remove first.

## Queue

A queue works similar to the stack, except that you now work with a principle of "First In, First Out", which is more fair in our real world. Again this could be represented by an array, linked list and other primitive data collections.

## Tree

A tree is based on a real tree where you have leafs and branches, therefore the name.
It can be represented by a node that can contain any amount of children nodes. The node is called a branch if it has child nodes and a leaf if has no children and therefore is the end point of a branch. The first node has no parent, has optionally children and is called the root node.

## Binary Search Tree

A Binary Search Tree is a special kind of tree in which each node has only a maximum of 2 children, a left and a right node. It is ordered in a way such that the left node has a value less than or equal to its own value. The right node has a value greater than its own value. This way you can search very easily, and in the exact same way as you would implement binary search for an array.

A Hash Table, Trie, Stack, Queue, Tree and Binary Search Tree are examples of higher-order Data Collections. They are called higher order because they are implemented using lower-order or so-called primitive Data Collections. Examples of primitive Data Collections are an Array and Linked List.

## Reflections on the homework

The homework was quite interesting, but not very challenging. Haven't done the Hacker Challenge yet though. In PSET4 you had to learn to understand the format of a Windows BMP files and its Headers using a provided C Header File that contained the structures that represent the layout of such headers. This was quite interesting, but nothing new due to my experience in the game industry, it was however still very interesting. Another challenge was to recover JPEG files from an erased memory card, which was interesting as it showed just how easy it is to recover deleted pictures. If you know the format of the memory (e.g. FAT) you know the size of the blocks and can therefore easily go through the entire disk and check the first few bytes of each block to see if you're dealing with a picture. You can eventually go even more advanced by implementing a decoder for JPEG files so that you actually know where to stop, but that wasn't needed for this challenge. It might be something they ask you in the hacker edition of PSET4, but I'm not sure.

That challenge was also linked to an article that talked about security related to erasing hard disks and repurposed hard drives. As a user you can for example make sure to overwrite all erased memory with zero characters `\0`. According to some people that isn't enough as it turns out that you can still recover data based on the magnetic fields via special-purpose hardware. Therefore to be really safe you could overwrite the erased memory several times with random characters. You can use free software to speed up this process. Using software does however expose you to possible bugs of that software, so you better make sure that your software does what you think it does.

All in all the homework and lessons are really setup in a very interesting way. They keep to the basics of introducing computer science but they do know how to make it entertaining while doing so. The challenges are at the same time do-able but make you feel like you're doing something that matters, like recovering pictures as if you were working for the forensic department of a police corps. They also really teach the students to learn to Read The Fucking Manual (RTFM), which is really good. I've seen many students in my university and other universitities where even graduates were still clueless and didn't know they should learn to trust and read the manual for whatever they need.

I'm Looking forward to the second half of this course.