# Today I Learned (TIL)
## Records of my progress as a developer, an investor and a person
### Japanese writer Haruki Murakami has a famous routine that he sticks to.
### Consistently write something everyday, no matter how little.
### This enabled him to be a great writer. 
### Charlie Munger has a mental model of trying to be a little smarter everyday.
### This mental model led him to be a great thinker and investor.
### I wanted to clone their approaches in my journey to become a great developer. 
### In this repo, I wanted to share my journey with whoever is interested.
### I don't plan to write on the weekends, because I want this to be a healthy habit not an obsession.

### Books to read
- Release it (paper copy)
- [Imposter's handbook 1 & 2](https://bigmachine.io/products/the-imposters-handbook/)
- [System design interview by Alex Xu](https://ebin.pub/qdownload/system-design-interview-an-insiders-guide-2nbsped-9798664653403.html)
- [Designing Data-Intensive Applications by Martin Kleppmann](http://xfido.com/pdf/designing-data-intensive-applications.pdf)
- [Clean architecture by uncle Bob](http://prof.mau.ac.ir/images/Uploaded_files/Clean%20Architecture_%20A%20Craftsman%E2%80%99s%20Guide%20to%20Software%20Structure%20and%20Design-Pearson%20Education%20(2018)%5B7615523%5D.PDF)
- [Understanding distributed systems](https://understandingdistributed.systems/)
- [Design Patterns by GOF](http://www.uml.org.cn/c++/pdf/designpatterns.pdf)
- pro microservices with .NET 6 (study club at work)

### Blogs
- https://continuations.com/post/149364248835/tech-tuesday-index

------------------------------------------------------------ 2022 ------------------------------------------------------------

Daily goals for the year:
1) 1 TIL from a Tech Tuesday article or few pages in a book
2) 1 commit to side project (changed from 1 leetcode on Feb 10)

3/23 W
- 'Sequence contains more than one element' error in C# indicated a SingleOrDefault method finding multiple DB tables.
- as a SWE 2, the goal is to (1) carry a project from architecting to implementation and (2) minimize PR feedback and future refactors

3/22 T
- my son's first day at school! Send kids to socialize sooner rather than later, altho Covid is a deterrent.

3/21 M - tightening schema and use better indices
- SELECT, JOIN, ORDER BY and GROUP BY can improve by using good indices.
- DB index uses b-tree structure. Learn more about it. (Balanced tree is a generalized form of BST that can have many branches)
- tighten schema via using CHAR instead of VARCHAR and using NOT NULL, etc.

3/18 F - denormalizarion
- create duplicate data/writes to avoid expensive joins especially when the DB is sharded or is using a federation.
- cons: write would take longer, and adds complexity
- SQL tuning via benchmarking and profiling
- benchmarking: simulate a high load situation
- profiling: track performance issues e.g. by using slow query log

3/17 Th - DB Federation
- also called functional partitioning; split up data by function
- pros: smaller DBs leading to more data in memory and higher cache hits; no master DB doing many writes, reducing replication lag and improving thruput
- cons: adds complexity to determine where to read from/write to; can contrain schema; if need to join tables, need to use a server link

3/16 W - sick day

3/15 T - scaling DB
- ACID
Atomicity: transaction succeeds or fails as a whole
Consistency: any transactions result in one valid state to another
Isolation: concurrent transaction should lead to the sam result as if done sequentially
Durability: data once committed, should persist
- replication is one approach: master slave or master master
- master-slave: read and write to master and master writes to slaves. Slave can write to other slaves like in a tree. Slaves help with reads.
- cons: need a logic to promote a slave to replace the master if it fails
- master-master: two masters supporting read and writes. If one fails, the other can take over.
- cons: need to sync up (may affect consistency); need a load balancer.
- replication con: if heavy writes, slaves will be busy relaying writes to help with reads

3/14 M - reverse proxy and microservics
- microsvc vs distributed monolith: microservice should address one or a set of problems (business logic). It can have soft dependency on other service e.g. async calls using message queues.
However, separating services and calling each other over the network is a distributed monolith with the same issues as a monolith.
- reverse proxy can be used to perform heavy operations such as encryption/decryption that is common across servers. It can also be used as a load balancer.

3/11 F - Load balancer
- load balancers are used to direct requests from clients to web servers/DBs
- some stratgies include (weighted) round robin, random, least load, session/cookies
- there are layer 4 and layer 7 load balancers. Layer 4 LB is faster at the expense of less flexibility as it has access to header, IP and port info in layer 4 but can't see more info in layer 7 like the payload, cookies, etc.

3/10 Th - System design, CDN, DNS
- try to maximize thruput given acceptable latency
- content delivery network (CDN) is used to deliver contents more quickly to users, as they are globally distributed.
- pull vs push CDN: push CDN you push content to the CDN and have more flexibility in terms of push timing, expiration, what to push, etc. Pull CDN is easier to use as CDN pulls contents from you. This can lead to slower UX initially until pulled and some redundant traffic from re-queries.
- Domain name system (DNS) translate website names to IP addresses. This way, people don't have to remember IP addresses. Usually provided by ISPs, governments or other tech companies. If subject to attack or down, can lead to a web not easily accessible.

3/9 W - Domain driven design (DDD)
- Domain for an accounting firm would be accounting. It is what the application is trying to achieve.
- subdomain is a grouping of related business processes. Payroll, accounts payable and accounts receivable would be subdomains of the accounting domain.
- HR for an accounting firm would be an ancillary domain.
- Similar business processes form a problem space.
- a group of codes for a subdomain is called a bounded context and they form a solution space.
- program.cs vs. startup.cs: program.cs is run when the application starts and in it, we can call startup.cs where we can configure various things such as middleware, authentication, etc.

3/8 T - Asp.net (chapter 2 of pro microsvcs book)
- MVC pattern has a long history and asp.net incorporated it since WinForms.
- routing as a fourth element was added in asp.net.
- controller is responsible for sending requests to the right model
- view is in charge of binding data to html
- model has business logic
- controller can have validation and logging
- a web framework essentially deals with request to response pipeline.

3/7 M - Stored procedures
- use stored procedures as they are faster, can group multiple operations into an atomic transaction.
- can create a role that have access to certain sprocs and this way a user can't see or alter tables unless they can do those using sprocs.
- cons: business logic in DB access layer and no version control.

3/4 F
- angular change detection basically happens when there is an async operation done.
- angular has 2 change detections: default or OnPush. OnPush only updates the template if the data has changed.
- ref: https://mokkapps.de/blog/the-last-guide-for-angular-change-detection-you-will-ever-need/

3/3 Th (3/2 sick)
- protected C# keyword
- derived classes can access protected members
- protected internal means either derived class or internal to the dll can access the member.
- protected private means it has to be a derived class in the same assembly.
- static constructor gets created only once
- angular life cycle hooks go ngOnChanges, ngOnInit and various Init and Check on Content and View and lastly ngOnDestroy.
- Ukraine is suffering from a war started by Russia under Putin. Markets volatile as uncertainties around politics as well as energy prices grow.
I'm considering whether this is the right time to purchase a home given that my oldest is turning 4. The rate is expected to go up according to Jay Powell due to high inflation.

3/1 T - nullable reference type in C#
- starting in .NET 6, with `<Nullable> enabled </Nullable>`, reference types are not automatically nullable as they were
- do not pass an object straight to logging, as it can be an EF object or another DB object that may contain extra info that should not be exposed.
- e.g. thingToLog.Select(x => new {x.PropertyA, x.PropertyB});

2/28 M - microservices
- monoliths are fine but it has a limit when it comes to scale.
- microservices can scale well horizontally but adds complexity
- each server should not be stateful as a user's request could get served by any server
- deploying all servers at once can be done by Capistrano for Ruby on Rails
- don't want svcs to call other svcs. If there is a common or core code, use a library so that it gets included in the process.
- Separate deployability can be another reason why microservices are preferred along with fault isolation
- distributed monoliths are not desirable but can be a stepping stone toward microsvcs.

2/25 F - startup
- according to YC startup school series the two main lessons are launch quickly and talk to users

2/24 Th - localStorage vs sessionStorage
- localStorage persists between tabs until browser is closed.
- sessionStorage is specific to a tab.

2/23 W - Business object vs. services
- repository layer is to access the database layer. Methods in the repo layer should not contain much logic. Should be simple LINQ-ish methods.
- Business objects (BO) can contain some logic in addition to the repository layer.
- BO allows for the repo layer to change, without changing the BO.
- BO is a place for various methods, and if you break the methods into a separate file per method, it becomes a service (e.g. ClassUpdateService, ClassCreationService, ClassDeletionService, ClassCalculationService, etc.)

2/22 T (M was president's day)
- how to create an InMemoryDB to test repository methods
- for SQL server and entityframework, use EFFORT (entity framework fake objectContext realization tool)
- for cosmosDB, can simply use Moq's Mock<ClassName>(){CallBase: true}; and setup the method from the parent class.
- Note that Mock<ClassName> is not Mock<InterfaceName>

2/18 F - dotnet
- Task.Run() to make a function async
- Task.WhenAll(task1, task2, ...) to make parallel async calls
- combine Task.Run and Parallel.forEach to run async calls in order and parallel (especially when progress status is needed)

2/17 Th - on the job Dotnet
- for interfaces, prefer broad types (e.g. prefer IEnumerable to IList) so that implementation can be a List or Array or something else.
- make services internal and interfaces public unless a service is meant to be used outside of the DLL. This way only the interface is exposed and not the specific implementation, eliminating the chance for confusion.

2/16 W - Jason web token (JWT)
- storing session info in DB increases latency because it needs to make another call from the service to the DB to check whether the session is valid
- using JWT can allow the service to trust the user
- there are other complication e.g. how to deprecate, expire the JWT?
- symmetric vs. asymmetric key: symmetric key is used to encrypt and decrypt while asymmetric key uses one key for encryption and another for decryption. Losing symmetric key can lead to a bad user generating secrets using the key while asymmetric key doesn't allow that.

2/15 T - mocking a lambda expression in C# (2/14 M skipped due to Valentine's day)
- mocking it like `method(x => x.Version == It.IsAny<string>)` does not work. Need to create an expression like `method(It.IsAny<Expression<Func<Output_Name, bool>>>())` for example. To test what goes inside the lambda expression, need to add a callback, and the mock get more involved.

2/11 F - CAP Theorem and ACID properties (from Hussein Nasser's youtube channel)
- CAP theorem states that we can only have two of Consistency, Availability and Partition Tolerance.
- Partition here means there is a networking i.e. communication between partitions
- ACID properties of a database
  - Atomicity: a transaction (which may entail several operations) either fails or succeeds together. 
  - Consistency: Data is consistent in the DB. e.g. the number of likes for a posting in the POSTING table is equal to the number of users that liked that post in the USERS table.
  - Isolation: few levels of isolations exist: (1) read uncommitted, (2) read committed, (3) repeatable read and (4) 
    - read uncommitted: give me all the data
    - read committed: only give me committed data
    - repeatable read: e.g. version the DB so that I can read repeatedly and would get the same result
    - lock: exclusive lock the DB just for my write; shared lock for reads
  - Durability: the data once commited and the DB says "all set", if the power goes out right after, the data should remain. A cache is an example of undurable DB.

2/10 Th - layer architecture
- convert DB object to a CTO even if no modifications are needed.
- this prevents sensitive info in DB from getting leaked.
- conversion in the service layer
- business objects combine various operations in one object whereas a service focuses on one thing and one thing only (SRP)

2/9 W - reflecting in my goal/priority
- I need to prioritie working on side project vs. TIL.
- becoming an expert in tech is not practical. Tech is ever evolving and even if become an expert, what'a the end goal? Teach? Google?
- learn continuously but for me, the reason for learning is to make something that can make people's lives better in some way.
- updated daily goal of 1 leetcode to 1 commit to side project

2/8 T - Address Resolution Protocol (ARP)
- ARP is a mapping between IP address and MAC (media access control) address
- we have the IP address to which we want to send the packets, but we need the MAC address for Layer 2 (layer 2: mac address, layer 4: IP, layer 7: http request)
- send ARP request to the IP address and store the MAC address in the local ARP table
- man in the middle attack and ARP corruption attacks exist

2/7 M - Turing machine
-  think of the Turing machine as a finite state machine with an infinitely long tape
-  it can read/write to the tape
-  it can operate at an arbitrary point on the tap and its behavior depends on the current state and what's on the tape.
-  based on above, it can write to the tape or leave it unchanged, and move to the left or right
link: https://www.youtube.com/watch?v=dNRDvLACg5Q

2/4 F
- Automata means abstract machine; finite state machine (FSM) means a machine that can only have a finite number of states e.g. Espresso machine: On, Off, Brewing and Rest.
- Cosmos DB document doesn't allow having an object as a key. Need to serialize (stringify) the object before using it as a key.

2/3 Th - Visual Studio debugging
- when can't set a breakpoint, start debugging and go to DEBUG -> WINDOWS -> MODULES -> find the DLL in use and see which folders VS looked at to locate the DLL, and copy and paste DLL and PDB to that folder.
- is unit test necessary for the repository layer when there is no business logic? if so, how to correctly test it?

2/2 W - C# basics
- project means a .csproj file
- assembly means a .csproj file compiled in to DLL or EXE
- don't allow more access than is necessary e.g. using `public` for a property when it doesn't need to be is not good practice in principle, but when testing API contracts, each property must be tested and can be a burden.
- XUnit uses the class's constructor for test initialization and Dispose method for test cleanup. For test cases, use [Fact] attribute

2/1 T - C# access modifiers and more
- Abstract class contains one or more abstract methods
- Abstract method has no implementation and has to be overriden
- Virtual method has an implementation but can be overridden

- Interface only has signatures and not implementations
- Sealed prevents further inheritance
- Protected is like Private but can be derived

- Readonly is run-time constant
- Constant is compile time constant

1/31 M
- OData is short for open data protocol. In combination with .NET's web api, we can easily set up OData and use it to query exactly the data required.
- OData can organize data in more powerful server rather than in the client
- Similar functionality as GraphQL but not the same thing. Easier to set up (at least for .NET web api) than GraphQL. No need to deal with Schemas, Resolvers, etc.
link: https://www.progress.com/blogs/rest-api-industry-debate-odata-vs-graphql-vs-ords

1/28 F
- .NET Async Await
  - using "async" keyword creates a state machine, which can be seen by inspecting the IL using ILSPY.
  - using "await" creates different checkpoints the state machine can jump to
  - using an async function with in "main()", for example, requires main to be async, as the method propagates up.
  - source: https://youtube.com/watch?v=il9gl8MH17s (Raw Coding - Async deep dive)

1/27 Th
- prefer saving static data or mapping instead of hardcoding it in the code. In case the data/mapping changes, shouldn't have to change the code; just update the data in the DB.

1/26 W
- encountered `413 EntityTooLargeError` in an api endpoint for the first time. This was due to the cache exceeding its size limit.
- Checklist for future when encountered a bug
  - Check the logging service first for a full set of errors and detailed logs
  - Write reproduction steps
  - Run code locally by pointing at different environments to check whether it is an env issue or config issue
  - redeploy/refresh files related to deployment to see if that does the trick
  - try using a different slot (use Dev slot to point at Staging) to make sure it is not a slot issue
  - at the end of the day, it can only be the feature code, middleware, configuration or storages

1/24 M
- ABAC & RBAC (attribute-based access control vs role-based)
- ABAC is primarility controlled by access policy. Access policies check whether there is an attribute that they are looking for and control access based on it. Once the access policy is set up, it can provide granular access control and flexibility and scalability.
- RBAC indicates that for every user there is a role, and every role has access to certain areas. This method is used much by SMEs (small-medium enterprises), and there are flat RBAC, hierarchical RBAC, etc. but essentially it is role centric. However, this can lead to "role explosions" as admin creates more and more roles to control access at a more granular level.
  - ABAC Pros
    - easier to scale 
  - ABAC Cons
    - higher setup effort 
  - RBAC Pros
    - easier setup 
  - RBAC Cons
    - can get messy as it scales

1/21 F
- about investing: thought about my approach recently. As I have followed Mohnish Pabrai closely and his learning as he shares them on Youtube, I have decided the best use of my time would be to focus on my craft (i.e. coding) and aim to be average (or hopefully a bit above avg) by investing in the broader markets via 401k and a few select Nick Sleep type of investments with competitive advantage and a long runway.
- This way I don't have to actively manage my investments as I have been doing (challenging myself to outperform the market and consuming much time/effort)
- This way I can get better at my job and what I like doing i.e. coding
- This way I may have time for a side project that can help me improve my skills even futher while proxying a out of the money call option, in case it turns into a startup!

1/20 Th
- 2 types of forms in Angular
  - template driven form
    - used for basic forms using <form> tag, to which ngForm gets applied automatically.
    - in the form, bind ngModel to <input> tags and can create a nested form by using ngModelGroup
  - reactive form (programatic form)
    - instantiate a formControlGroup instance and formControl instances for more granular validation and more complex forms
- [Javascript function vs arrow function](https://dmitripavlutin.com/differences-between-arrow-and-regular-functions/#1-this-value)
  - using the function keyword defines its own execution context while arrow function does not.
  - execution context affects the `this` keyword
  - as a result, arrow function can't be used as a constructor
  - function and arrow function can be used as a method in a class, but when using the function keyword and calling the method using setTimeout, for example, could require binding the method back to the object, while the arrow function binds to the outer scope i.e. the class as its scope.
- [LessCSS](https://www.youtube.com/watch?v=5mPEelNaZuc&list=PLLAZ4kZ9dFpNmzIb3XQi5QSFiEpK-UxUg)
  - you can declare a variable and create functions and pass them to reduce repetition of styles.
  - can use conditional operators
  - can import variables and styles from other less files
  - can nest CSS like html and create more readable CSS file


1/18 T (1/17 M MLK Day)
- lexical and dynamic scope: 
   - the lexical scoping indicate when a variable's scope within a function is only defined inside the function, compared to dynamic scoping which can indicate a variable inside the scope as long as the function is running. 
  - For example, within main function, there is a function called firstFunc, and let's say there is a variable called a `scope`. If the programming language we are using uses lexical scoping, the scope will not be able to refer to the variable outside of the firstFunc, unless passed into the function as an argument, whereas in dynamic scoping, we can refer to the variable in the main function outside the firstFunc.
- Arguments to a function can be passed in by value or by reference. 
  - If passed by value, a copy of the argument is created and it doesn't affect the original variable whereas pass by reference passes the reference of the variable to the argument, and consequently, changes to the argument's value will result in the change in original variable's value.
  - For example, in the main program, let's define a variable called `mainVar` and make it equal to a number `5`. Let's say the firstFunc take one argument and changes the value of the argument to `3` and return it. If passed my value, when we call firstFunc(mainVar), firstFunc will return 3 and mainVar will remain as `5` but if passed by reference, it will return 3 and change mainVar to `3`.

1/14 F (week's learning)
- Control structure: if and while are examples of control structures. if statement can be used as a syntactic sugar to create a switch case statement, and while can be used to make a for loop.
- ngModule: use modules to organize the code. imports, exports, providers and declarations are in a module. 
  - imports are for using exported declarations of other modules in the current module, 
  - exports are for code that can be used publicly (by other modules)
  - declarations are for directives, including components and pipes that are created in the current module and can be used by others in the current module.
  - providers are for services so that they can be used for dependency injection in the current module.
- Angular routing
  - use app routing module to specify path and the component the path should lead to. 
  - [Routerlink] can be used with a <router-outlet> to specify where the routed component should show up. 
  - Guards can be used to control access to a certain route. 
  - Use ActivatedRoute via dependency injection to access queryParams.
- Observables have 3 parameters: next, error and complete. 
  - Observables are stream of events that we can subscribe to get notified when an event occurs. 
  - Unsubscribe from observables to prevent memory leak. 
  - Use Rxjs's observables and Angular's httpService for the database layer.
  - use mergeMap to replace nested observables in case of making http request using the data from a subscribed observable.

1/7 F
- after a url is entered into a browser and the ip address is received from the DNS, the three way handshake happens where the client sends the server SYN, the server sends back SYN-ACK and client then sends back ACK.
The three way handshake is used to establish TCP connection. UDP is connectionless and doesn't use the three way handshake, less reliable than TCP.
IP breaks our requests (usually GET, POST, PUT, or DELETE) into packets and sends it over. These packets can arrive at the server out of order or not at all.
TCP uses checksum to make sure that all the packets that were sent have arrived.
Checksum can fail in which case the packet is discarded (any notice back to the client? Retry?)
There's also a small chance that checksum passes despite corruption.
To see how many and where the request packets hop thru, you can open a terminal (for mac) and type something like traceroute google.com
You can make a request faster by using a CDN (content delivery network) or my making fewer packets.

1/6 Th
- When we type a URL into a browser and press enter, it parses it first as explained below. But how do we get the IP address when we type in google.com? 
The answer is DNS (domain name system). The request goes to the 13 root servers and start from the TLD (top level domain) such as .com or .net. Then, the TLD name server points to the name server for the domain e.g. google.com and then from there it looks for the name server of its subdomain e.g. calendar.google.com.
This process of going from TLD to subdomain is called a recursive lookup.
This process is expensive and is alleviated by the use of caches at various levels: ISP, 13 root servers, domain server.
Each TLD has one or more registrar associated who helps people reserve names in that domain

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

12/30 Th
SOLID principles
  
1. Single responsibility
- Do one thing i.e. should have only one reason for the code to change
e.g. CalorieTracker class having a calculateCalories method and a logCalories method violates the principle.
solution: create a Logger class and use the logger class to log calories and remove logCalories method from the CalorieTracker class

2. Open/closed
- open for extension but closed for modification.
e.g. class Problem that has a switch statement and various kinds of problems like multiple choice, true or false, essay, etc.
if we want to add another question type, we have to add a case to the switch statement i.e. modifying the code.
solution: make a class for each type of the problems and each class should have the same method e.g. displayQuestion(). This way, the Problem class will only have the displayQuestion method and the switch statement can be removed. We can add more question types by making more classes without modifying any of the existing code.

3. Liskov substitution
- subclass should be able to substitute the parent class
e.g. if Square inherits from Rectangle and they both have a getArea method, increase a width by 1 of a rectangle will result in higher area but doing the same for a square will result in a greater increase in the area because increasing a width by 1 will also increase the length by 1 for a square, breaking Liskov.
Solution: create another class e.g. Shape that both Square and Rectangle inherit from.
e.g. Bird class having fly and swim methods won't work for a Penguin class, because it can't fly, breaking Liskov.
solution: create a FlyingBird class or SwimmingBird class or FlyingSwimmingBird class. Composition is always preferred for Javascript than inheritance

4. Interface segregation
- everything that implements an interface must implement everything in the interface.
assume the Bird class above is an interface, Penguin won't implement a fly method, breaking the ISP.
solution: break it down like in Liskov; break down ILibraryItem to IBook, IBorrowable, IDvd, etc. you can combine multiple interfaces to form another interface like IBorrowableBook: IBook, IBorrowable. Even though this may result in an empty interface, it is better to create this combining interface so that if instantiated in the main program, that it can reference all the methods from both interfaces.

5. Dependency inversion
- invert dependency by creating a wrapper like a facade pattern
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
