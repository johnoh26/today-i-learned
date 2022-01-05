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
- [Imposter's handbook 1 & 2](https://bigmachine.io/products/the-imposters-handbook/)
- [System design interview by Alex Xu](https://ebin.pub/qdownload/system-design-interview-an-insiders-guide-2nbsped-9798664653403.html)
- [Designing Data-Intensive Applications by Martin Kleppmann](http://xfido.com/pdf/designing-data-intensive-applications.pdf)
- [Clean architecture by uncle Bob](http://prof.mau.ac.ir/images/Uploaded_files/Clean%20Architecture_%20A%20Craftsman%E2%80%99s%20Guide%20to%20Software%20Structure%20and%20Design-Pearson%20Education%20(2018)%5B7615523%5D.PDF)
- [Understanding distributed systems](https://understandingdistributed.systems/)
- [Design Patterns by GOF](http://www.uml.org.cn/c++/pdf/designpatterns.pdf)

------------------------------------------------------------ 2022 ------------------------------------------------------------

Daily goals for the year:
1) 1 TIL from a Tech Tuesday article or few pages in a book
2) 1 Leetcode

1/6 Th
- 

1/5 W
- TIL 5 design patterns: null object, builder, singleton, facade, command
- null object pattern can be used when you create a class e.g. User which has getUser method that returns user's name. We may have to check if the name is null every time we use getUser. Instead, we can create a NullUser class that has "Guest" as name and the getUser function can return it if the name is null. This way, we don't have to add null checks every time we use this method.
- builder pattern can be used when there is a class with 4 properties. Instead of using a constructor to populate those fields, we can use the constructor for required properties and use methods for the rest.
e.g. `class User {
  constructor(name, age, gender, address) {
    this.name = name
    ...
  }
}`

this can lead to an ugly code like this "new User("Tom", null, null, "sesame st"). Instead, say the name is the only required field, we can make methods to set the other properties. 
`class User {
  constructor(name, age, gender, address) {
    this.name = name
  }
  
  setAge(): {
    this.age = age
  }
  ...
}`
this way, we can use 
`let user = new User("Tom")
user.setAge(21)`

- singleton pattern can be controversial and should be used when absolutely adequate. The example used was a logger for the entire application. Create a single instance of a logger class that is used everywhere. Singleton can be dangerous because it can make code hard to test as it may require the use of the singleton, and updates to the singleton can impact a lot of things.
- facade pattern is used to simplify code and centralize the complexity. The example used was a fetch method. We can extract the detailed implementation out by creating a wrapper that gets the required parameters as arguments. Think about using this pattern when we are repeating the same code.
- command pattern is used to do/undo a command or operation. The example used was a calculator class with 4 basic math operations. We could break them apart into a class of its own that has execute and undo methods. The calculator class can have a history property that keep track of what operation we performed with what number so that we can undo them. This can be useful for applications that should provide users to undo an action. 
(This example got me wondering whether a Calculator class with 4 operations would violate the SRP (single resp principle) or does it make sense because the calculator should be able to do those four operations? What is an object in OOP?)

1/4 T
- TIL about URL (uniform resource locator)
- there are various protocols for the internet. HTTP(s): is common, but there are ftp: (for file) and mailto: (for SMTP)
- "//" indicates that the url starts with a domain name
- following the domain name is the location of the resource within that domain

1/3 M
- TIL that when we enter a URL to a browser it goes thru several steps
1) http(s) automatically gets added thesedays and the URL gets parse to get the domain name e.g. google
2) look up the domain's IP address from the DNS (domain name system)
3) makes a GET request to the above IP address
4) the request is routed via various machines e.g. router, switch, load balancer, firewall
5) the request arrives on the server. Server (like Apache or NGINX) sends a response back to where the request came from
6) the browser gets the response and renders the view while continuously making request if instructed
7) as the browser waits for responses, it will render the content that it has received

1/2 Sun
- TIL that OS (operating system) is what glues the pillars (peripherals, networking, memory, storage, processing) of a computer together. Examples are iOS, Windows, OS X, Linux, Unix, etc. Server computers are basically a specialized computer and they use IOS (Cisco) and Junos (Juniper). OS used to be in ROM (read-only memory) in the past but as OS's got larger and ROM can't be overwritten, a boot loader loads the rest of the OS (this process is called booting). How is boot loader getting data from disk when I/O needs an OS? There is a BIOS (basic I/O system) that is saved in flash memory that can handle this process. An OS is largely composed of two parts: (1) kernel and (2) the rest. Different OS's have different features in the kernel. The kernel space can only be accessed by code executing inside the kernel, and this is separate from the user space. User space can be accessed by the end user, running theprograms on top of the OS.

1/1 Sat
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
