1. QUESTION: In LinkedList::deleteFront(), why does it take two separate delete calls instead of one?
   Name exactly what each one frees, and name the two new calls back in the program responsible
   for putting them on the heap in the first place.
1) ANSWER: That function takes two separate delete calls instead of one as it needs to get rid of both the data that the pointer points to and the pointer itself. It first gets rid of the data which leaves the pointer without anything to point to. So then the pointer also gets deleted.
2. QUESTION: ArrayList never had a destructor before today. Explain, in your own words, why switching
   from T data[CAPACITY] to T* data [CAPACITY] is what made a destructor necessary, and what
   would happen if you forgot to write one. Would you get a compiler error? Why or why not?
2) ANSWER: The reason why switching to T* data [capacity] creates a need for a destructor is that T* is a pointer. When we made that switch, it meant that the array was now an array of pointers rather than values. You wouldn't get a complier error because the complier wouldn't check for that. From what I remember, C++ gives the user much more freedom to mess with the memory compared to Java for example.
3. QUESTION: search() and addFront() both take a T*, but they treat that pointer completely differently.
   Explain the difference in terms of ownership: which one is allowed to delete what you hand it,
   and which one is never allowed to?
3) ANSWER: The difference is due to the word const. search() uses the word const so that one can't delete what I hand it. addFront() doesn't use const so it can delete whatever I hand it.
4. QUESTION: You swapped LinkedList<T> for ArrayList<T> inside makeList() and reran main.cpp without
   changing a single line there. What two mechanisms, by name, made that possible?
4) ANSWER: The two mechanisms that allow for this are templates and polymorphism. Templates are like generics in Java so we just build the function using the template. Polymorphism is the idea that a single function (or method in Java) can be used with different types. For example, if a method has a long parameter and the arguments are actually ints, that would still work as an int can fit in a long. 
5. QUESTION: Pick one keyword from the Key Terms glossary that you either had to add today or wouldn’t have
   thought to add on your own (explicit, override, virtual, const, or any other). Describe, in
   your own words and without copying the guide’s wording, the smallest example you can think
   of where leaving it out would cause a real problem. 
5) ANSWER: The word I picked was const. The smallest example I can think of where leaving this word would cause a real world problem is putting in a value and it getting changed. The specific example would be our code. Leaving out the word const might make it so the search function can change the value, which is something we don't want.