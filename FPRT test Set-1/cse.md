                                                   FPRT CSE TEST {SET- 1}

Question 1:- What is ACID properties and BASE properties?

Answer:-
ACID properties:-

ACID stands for Atomicity Consistency Isolation and Durability.

1. ATOMICITY:-
In atomicity a transaction is an atomic unit. Hence, all the instructions within a transaction will successfully execute, or none of them will execute. The following transaction transfers 20 dollars from ram's bank account to shayam’s bank account. If any of the instructions fail, the entire transaction should abort and rollback.

                            T1
                            Read(A_bal)
                            A_bal -= 20
                            Write(A_bal)
                            Read(B_bal)
                            B_bal += 20
                            Write(B_bal)
             (A transaction to transfer 20 pounds from Ram's account to Shayam's account) 

2. CONSISTENCY :-
In consistency a database is initially in a consistent state, and it should remain consistent after every transaction. Suppose that the transaction in the previous example fails after Write(A_b) and the transaction is not rolled back; then, the database will be inconsistent as the sum of Alice and Bob’s money, after the transaction, will not be equal to the amount of money they had before the transaction.

3. ISOLATION :-
In isolattion if the multiple transactions are running concurrently, they should not be affected by each other; i.e., the result should be the same as the result obtained if the transactions were running sequentially. Suppose B_bal is initially 100. If a context switch occurs after B_bal *= 20, T2 will read the incorrect value of 100 as the updated value will not have been written back to the database. This violates the isolation property as the result is different from the answer that would have been​ obtained if T1 had ​finished before T2.

                    T1              T2
                  Read(B_bal)     Read(B_bal)
                  B_bal*=0.2      B_bal += 20
                  Write(B_bal)    Write(b_bal)

         T1 adds 20% interest to Shayam's savings account and T2 adds 20 pounds to Shayam's account

4. DURABILITY :-
In durability changes that have been committed to the database should remain even in the case of software and hardware failure. For instance, if Shayam’s account contains $120, this information should not disappear upon hardware or software failure.


BASE properties :-
BASE stands for Basically Available, Soft state, Eventual consistency.

BASE is a database design philosophy that prizes Availability over Consistency of operations.Basically available indicates that the system does guarantee Availability, in terms of the CAP theorem. NoSQL databases spread data across many storage systems with a high degree of replication for high degree of Availability.

1. BASIC AVAILABILITY :-
In basic availability the NoSQL database approach focuses on the availability of data even in the presence of multiple failures. It achieves this by using a highly distributed approach to database management. Instead of maintaining a single large data store and focusing on the fault tolerance of that store, NoSQL databases spread data across many storage systems with a high degree of replication. In the unlikely event that a failure disrupts access to a segment of data, this does not necessarily result in a complete database outage.

2. SOFT STATE:-
BASE databases abandon the consistency requirements of the ACID model pretty much completely. One of the basic concepts behind BASE is that data consistency is the developer's problem and should not be handled by the database.


3. EVENTUAL CONSISTENCY:-
 The only requirement that NoSQL databases have regarding consistency is to require that at some point in the future, data will converge to a consistent state. No guarantees are made, however, about when this will occur. That is a complete departure from the immediate consistency requirement of ACID that prohibits a transaction from executing until the prior transaction has completed and the database has converged to a consistent state.


Question 2:- What are the differences between paging and segmentation?

Answer 2 :-

Difference between Paging and Segmentation:

S.NO	                      PAGING	                                                      
1.	In paging, program is divided into fixed or mounted size pages.       	
2.	For paging operating system is accountable.                           	
3.	Page size is determined by hardware.	                                
4.	It is faster in the comparison of segmentation.	                       
5.	Paging could result in internal fragmentation.	                        .
6.	In paging, logical address is split into page number and page            
    offset                                                                     
7.	Paging comprises a page table which encloses the base address            
    of every page.                                                              
8.	Page table is employed to keep up the page data.	                   
9.	In paging, operating system must maintain a free frame                  
    list.  	                                                                  
10.	Paging is invisible to the user.	                                   
11.	In paging, processor needs page number, offset to calculate           
    absolute address.	                                                       


SEGMENTATION

1. In segmentation, program is divided into variable size sections.
2. For segmentation compiler is accountable.
3. Here, the section size is given by the user.
4. Segmentation is slow.
5. Segmentation could result in external fragmentation.
6. Here, logical address is split into section number and section offset.
7. While segmentation also comprises the segment table which encloses segment number and segment offset.
8. Section Table maintains the section data.
9. In segmentation, operating system maintain a list of holes in  main memory.
10. Segmentation is visible to the user.
11. In segmentation, processor uses segment number,offset to calculate full address.




Question 3 :- Explain the OOPS principles.

Answer :-
Object-oriented programming has four basic concepts: encapsulation, abstraction, inheritance and polymorphism. Even if these concepts seem incredibly complex, understanding the general framework of how they work will help you understand the basis of a computer program. Here are the four basic theories and what they entail:

1. Encapsulation
2. Object
3. Classes
4. Inheritance

In detail,

1. ENCAPSULATION :-
    The process of wrapping property and function within a single unit is known as encapsulation.
    Let’s understand encapsulation with an example{ 
//encapsulation example 
class person{ 
    constructor(name,id){ 
        this.name = name; 
        this.id = id; 
    } 
    add_Address(add){ 
        this.add = add; 
    } 
    getDetails(){ 
        console.log(`Name is ${this.name},Address is: ${this.add}`); 
    } 
} 
  
let person1 = new person('Mukul',21); 
person1.add_Address('Delhi'); 
person1.getDetails(); 
}

In the above example we simply create an person Object using the constructor and Initialize it property and use it functions we are not bother about the implementation details. We are working with an Objects interface without considering the implementation details.

2. OBJECT :-
  An Object is a unique entity which contains property and methods. For example “car” is a real life Object, which have some characteristics like color, type, model, horsepower and performs certain action like drive. The characteristics of an Object are called as Property, in Object Oriented Programming and the actions are called methods. An Object is an instance of a class. Objects are everywhere in JavaScript almost every element is an Object whether it is a function,arrays and string.

  Note: A Method in javascript is a property of an object whose value is a function.

Object can be created in two ways in JavaScript:
Using an Object Literal
Using an Object Constructor

3. CLASSES :-
They are blueprint of an Object. A class can have many Object, because class is a template while Object are instances of the class or the concrete implementation.

Before we move further into implementation, we should know unlike other Object Oriented Language there is no classes in JavaScript we have only Object. To be more precise, JavaScript is a prototype based object oriented language, which means it doesn’t have classes rather it define behaviors using constructor function and then reuse it using the prototype.

Note: Even the classes provided by ECMA2015 are objects

Class Example :-{
    // Defining class using es6 
class Vehicle { 
  constructor(name, maker, engine) { 
    this.name = name; 
    this.maker =  maker; 
    this.engine = engine; 
  } 
  getDetails(){ 
      return (`The name of the bike is ${this.name}.`) 
  } 
} 
// Making object with the help of the constructor 
let bike1 = new Vehicle('Hayabusa', 'Suzuki', '1340cc'); 
let bike2 = new Vehicle('Ninja', 'Kawasaki', '998cc'); 
  
console.log(bike1.name);    // Hayabusa 
console.log(bike2.maker);   // Kawasaki 
console.log(bike1.getDetails()); 

}

4. INHERITANCE – It is a concept in which some property and methods of an Object is being used by another Object. Unlike most of the OOP languages where classes inherit classes, JavaScript Object inherits Object i.e. certain features (property and methods)of one object can be reused by other Objects.
Lets’s understand inheritance with example:{
    //Inhertiance example 
class person{ 
    constructor(name){ 
        this.name = name; 
    } 
    //method to return the string 
    toString(){ 
        return (`Name of person: ${this.name}`); 
    } 
} 
class student extends person{ 
    constructor(name,id){ 
        //super keyword to for calling above class constructor 
        super(name); 
        this.id = id; 
    } 
    toString(){ 
        return (`${super.toString()},Student ID: ${this.id}`); 
    } 
} 
let student1 = new student('Mukul',22); 
console.log(student1.toString()); 
}

In the above example we define an Person Object with certain property and method and then we inherit the Person Object in the Student Object and use all the property and method of person Object as well define certain property and methods for Student.
Note: The Person and Student object both have same method i.e toString(), this is called as Method Overriding. Method Overriding allows method in a child class to have the same name and method signature as that of a parent class.
In the above code, super keyword is used to refer immediate parent class instance variable.


Question 4 :- What will happen when you write www.google.com in your web browser ?

Answer 4 :-
This will happen when you write www.google.com in our web browser.
These are tht=e following steps :-

Step 1: 
Request a record
You begin by asking your computer to resolve a hostname, such as visiting 'http://www.google.com' in a web browser. The first place your computer looks is its local DNS cache, which stores DNS information that the computer has recently retrieved.

Step 2: 
Ask the Recursive DNS servers
If the records are not stored locally, your computer queries (or contacts) your ISP's recursive DNS servers. These machines perform the legwork of DNS queries on behalf of their customers. The recursive DNS servers have their own caches, which they check before continuing with the query.

Step 3: 
Ask the Root DNS servers
If the recursive DNS servers do not have the record cached, they contact the root nameservers. These thirteen nameservers contain pointers for all of the Top-Level Domains (TLDs), such as '.com', '.net' and '.org'. If you are looking for 'www.google.com.', the root nameservers look at the TLD for the domain - 'www.google.com'- and direct the query to the TLD DNS nameservers responsible for all '.com' pointers.

Step 4: 
Ask the TLD DNS servers
The TLD DNS servers do not store the DNS records for individual domains; instead, they keep track of the authoritative nameservers for all the domains within their TLD. The TLD DNS servers look at the next part of the query from right to left - 'www.google.com' - then direct the query to the authoritative nameservers for 'google.com'.

Step 5: 
Ask the Authoritative DNS servers
Authoritative nameservers contain all of the DNS records for a given domain, such as host records (which store IP addresses), MX records (which identify nameservers for a domain), and so on. Since you are looking for the IP address of 'www.google.com', the recursive server queries the authoritative nameservers and asks for the host record for 'www.google.com'.

Step 6: 
Retrieving the record
The recursive DNS server receives the host record for 'www.google.com' from the authoritative nameservers, and stores the record in its local cache. If anyone else requests the host record for 'www.google.com', the recursive servers will already have the answer, and will not need to go through the lookup process again until the record expires from cache.

Step 7: 
The Answer!
Finally, the recursive server gives the host record back to your computer. Your computer stores the record in its cache, reads the IP address from the record, then passes this information to the web browser. Your browser then opens a connection to the IP address '72.14.207.99' on port 80 (for HTTP), and our webserver passes the web page to your browser, which displays Google.



MCQ's

1. Which of the following condition is required for a deadlock to be possible?
a) mutual exclusion
b) a process may hold allocated resources while awaiting assignment of other resources
c) no resource can be forcibly removed from a process holding it
d) all of the mentioned

Answer :- (D) all of the mentioned

2. Which one of the following is the deadlock avoidance algorithm?
a) banker's algorithm
b) round-robin algorithm
c) elevator algorithm
d) karn's algorithm

Answer :- (A) banker's algorithm

3. To avoid deadlock ____________
a) there must be a fixed number of resources to allocate
b) resource allocation must be done only once
c) all deadlocked processes must be aborted
d) inversion technique can be used

Answer :- (A) there must be a fixed number of resources to allocate

4. A Process Control Block(PCB) does not contain which of the following?
a) Code
b) Stack
c) Bootstrap program
d) Data

Answer :- (C) Bootstrap program

5. Which of the following is not the state of a process?
a) New
b) Old
c) Waiting
d) running

Answer :- (B) Old

