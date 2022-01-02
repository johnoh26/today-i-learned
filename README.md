# Today I Learned (TIL)
## Records of my progress as a developer, an investor and a person
### Japanese writer Haruki Murakami has a famous routine that he sticks to.
### Consistently write something everyday, no matter how little.
### This enabled him to be a great writer. 
### Charlie Munger has a mental model of trying to be a little smarter everyday.
### This mental model led him to be a great thinker and investor.
### I wanted to clone their approaches in my journey to become a great developer. 
### In this repo, I wanted to share my journey with whoever is interested.
#### Books to read
- Release it (paper copy)
- Imposter's handbook 1,2
- System design interview by Alex Xu (https://ebin.pub/qdownload/system-design-interview-an-insiders-guide-2nbsped-9798664653403.html)
- Designing Data-Intensive Applications by Martin Kleppmann (http://xfido.com/pdf/designing-data-intensive-applications.pdf)
- Clean architecture by uncle Bob (http://prof.mau.ac.ir/images/Uploaded_files/Clean%20Architecture_%20A%20Craftsman%E2%80%99s%20Guide%20to%20Software%20Structure%20and%20Design-Pearson%20Education%20(2018)%5B7615523%5D.PDF)
- https://understandingdistributed.systems/
- Design Patterns by GOF (http://www.uml.org.cn/c++/pdf/designpatterns.pdf)

------------------------------------------------------------ 2022 ------------------------------------------------------------

Daily goals for the year:
1) 1 Leetcode
2) a Tech Tuesday article or few pages in a book
3) 1 TIL 

1/1 Sat
- Leetcode: Swap nodes in pairs (recursion and iterative solution)
Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)

Example 1:
Input: head = [1,2,3,4]
Output: [2,1,4,3]

Example 2:
Input: head = []
Output: []

Example 3:
Input: head = [1]
Output: [1]

var swapPairs = function(head) {
    // empty node
    if(head == null) {
        return head
    }
    
    // one node
    if(head.next == null) {
        return head
    }
    
    // switch direction
    let next = head.next
    let nextNext = next.next
    next.next = head
    
    // recurse to the next nodes
    head.next = swapPairs(nextNext)
    
    // make next nodes point back
    return next
};

- TIL that how input/output (I/O) devices or peripherals work for computers. For example, when the keyboard is pressed, "interrupts" make the CPU take note of the pressed key and save it to a memory location aka "keyboard buffer" which is a queue like a printer queue where we can see jobs for a printer except this is for the keyboard. All this work is done by the keyboard driver, and the interrupts and keyboard buffer are a part of the computer's operating system (OS). Peripherals also communicate with the computer via the physical layer e.g. HDMI cable or USB drive (Bluetooth?)

------------------------------------------------------------ 2021 ------------------------------------------------------------

Goals for the year:
1) Start Leetcode Explore
2) Start reading Donne Martin's system design primer

12/31 F
- Leetcode: Reverse string (using recursion)
- Tech Tues article on networking: the Open system interconnection 7 layer model. 7 layers are physical (e.g. ethernet or wifi), datalink, network (IP), transport (TCP), session, presentation, application (HTTP)

12/30
- SOLID principles
Single responsibility: do one thing i.e. should have only one reason for the code to change
e.g. CalorieTracker class having a calculateCalories method and a logCalories method violates the principle.
solution: create a Logger class and use the logger class to log calories and remove logCalories method from the CalorieTracker class

Open/closed
open for extension but closed for modification.
e.g. class Problem that has a switch statement and various kinds of problems like multiple choice, true or false, essay, etc.
if we want to add another question type, we have to add a case to the switch statement i.e. modifying the code.
solution: make a class for each type of the problems and each class should have the same method e.g. displayQuestion(). This way, the Problem class will only have the displayQuestion method and the switch statement can be removed. We can add more question types by making more classes without modifying any of the existing code.

Liskov substitution
subclass should be able to substitute the parent class
e.g. if Square inherits from Rectangle and they both have a getArea method, increase a width by 1 of a rectangle will result in higher area but doing the same for a square will result in a greater increase in the area because increasing a width by 1 will also increase the length by 1 for a square, breaking Liskov.
Solution: create another class e.g. Shape that both Square and Rectangle inherit from.
e.g. Bird class having fly and swim methods won't work for a Penguin class, because it can't fly, breaking Liskov.
solution: create a FlyingBird class or SwimmingBird class or FlyingSwimmingBird class. Composition is always preferred for Javascript than inheritance

Interface segregation
everything that implements an interface must implement everything in the interface.
assume the Bird class above is an interface, Penguin won't implement a fly method, breaking the ISP.
solution: break it down like in Liskov; break down ILibraryItem to IBook, IBorrowable, IDvd, etc. you can combine multiple interfaces to form another interface like IBorrowableBook: IBook, IBorrowable. Even though this may result in an empty interface, it is better to create this combining interface so that if instantiated in the main program, that it can reference all the methods from both interfaces.

Dependency inversion
invert dependency by creating a wrapper like a facade pattern
e.g. wrap paypal or stripe API in a PaymentProcessor class so that the existing code depends on the payment processor instead of the Paypal or Stripe Api

source: web dev simplified and Tim Corey on Youtube

12/22
- can use Chrome dev tools Audit function to performance teest the frontend
- polyfill is to bridge the gaps between browsers (i.e. satisfy code's compatibility with different browsers)

12/21
- .Net Core is not .Net and ASP.NET 4.x is now ASP.NET
- I want to test everything about the app. 
  - Frontend (using Devtools and Redux tools for networking, elements and state management, how to performance test a component?)
  - Backend (how to performance test and load test each api?)

12/7
- to start a project, I want to download: Chrome, VS code, npm, node.js, angular, typescript
- CAP theorem states that you can choose two things from Consistency, Availability and Partition Tolerance.
- RDBMS tend to focus on CA and ACID properties while noSQL DBs focus on AP or CP.

12/2
- in javascript, we can use filter to mimic map and vice versa, although the result will be [2,4,6,8,10] vs [undefined, 2, undefined, 4, undefined, 6, undefined, 8, undefined, 10] when we filter even numbers from [1,2,3,4,5,6,7,8,9,10] using filter vs. map.
- can't use filter and/or map to replicate reduce without creating another variable, because the function's signature is different i.e. map and filter return an array but reduce returns a single value
- Javascript has interesting type coersion and conversion system.
- 6 primitive types in JS: number, boolean, null, undefined, string, symbol and 1 complex type: object
- in JS, things are truthy or falsey, but truthy is not equal to true. Truthy means can be coerced to being true.
- falsey things are empty string ("" or ''), 0 (-0 and 0n), null, undefined and NaN, and the rest are truthy
