	
**Creational**
How objects are created provided flexible and efficient ways to instantiate them without specifying the exact details of creation process.
- abstract factory
	 Provides an interface for creating families of related objects without specifying their concrete classes
		- Type of parent and child pointing same class also known as  inheritance
		- Advantage
			consistency, separation of responsibility, flexibility and loose coupling
- Factory
	 Defines an interface for creating an object, but allows subclasses to decide which class to instantiate
		-     Responsible for creating object based on specified input
			Eg : Role based actions here admin, customer and seller are denoted as sub class, PDF creation, theme
	```
		// Factory function to create a user based on role and user info
		const createUser = (role, userInfo) =&gt; {
		  // Initialize a user object with common properties
		  const user = {
		    name: userInfo.name,
		    password: userInfo.password
		  };
		
		  // Define specific additional information based on the role
		  const specificInfo = {
		    admin: () =&gt; ({ role: 'Admin', key: userInfo.key }),
		    customer: () =&gt; ({ role: 'Customer', address: userInfo.address }),
		    seller: () =&gt; ({ role: 'Seller', shopAddress: userInfo.shopAddress, contact_No: userInfo.contact_No })
		  };
		
		  // Get additional information based on the role provided
		  const additionalInfo = specificInfo[role] ? specificInfo[role]() : null;
		
		  // If an invalid role was specified, throw an error
		  if (!additionalInfo) {
		    throw new Error('Invalid role specified.');
		  }
		
		  // Combine the common user properties with additional role-specific properties
		  return { ...user, ...additionalInfo };
		};
		
		// Create an Admin User instance
		const adminUser = createUser('admin', {
		  name: 'Abhishek',
		  password: 'Abhi1233',
		  key: '#1244534-fadsv34'
		});
		
		// Create a Customer User instance
		const customerUser = createUser('customer', {
		  name: 'John Doe',
		  password: 'Password123',
		  address: '123 Main St'
		});
		
		// Create a Seller User instance
		const sellerUser = createUser('seller', {
		  name: 'Jane Smith',
		  password: 'SellerPass',
		  shopAddress: '456 Market St',
		  contact_No: '123-456-7890'
		});
		
		// Log the Admin User details
		console.log('Admin User:', adminUser);
		
		// Log the Customer User details
		console.log('Customer User:', customerUser);
		
		// Log the Seller User details
		console.log('Seller User:', sellerUser);
	```

	Advantages:
		 abstraction and encapsulation, simplified object creation, code resuability, enhanced readability, error handling
	
- Builder
	 Separates the construction of a complex object from its representation, allowing the same construction process to create different representations
		- Constructs complex object step by step
		- Simplifies Object Construction with Many Parameters
		- supports chaining
		- handle optional parameter gracefully
		- Advantage : method calls sequence of instruction for constructioning object which improves readability
		- Example 
		       Without Builder
```
              	class Car {
				  constructor(make, model, year, color, hasGPS, hasSunroof) {
				    this.make = make;
				    this.model = model;
				    this.year = year;
				    this.color = color;
				    this.hasGPS = hasGPS || false;     // Optional parameter
				    this.hasSunroof = hasSunroof || false; // Optional parameter
				  }
				  describe() {
				    return `${this.year} ${this.make} ${this.model} in ${this.color} color with GPS: ${this.hasGPS} and Sunroof: ${this.hasSunroof}`;
				  }
				}
				// Creating the object
				const car = new Car('Tesla', 'Model S', 2024, 'Red', true, false);
				console.log(car.describe())
```
	         
With Builder
```
	 	
		// Car class remains simple, no complex constructor
		class Car {
		  constructor(builder) {
		    this.make = builder.make;
		    this.model = builder.model;
		    this.year = builder.year;
		    this.color = builder.color;
		    this.hasGPS = builder.hasGPS;
		    this.hasSunroof = builder.hasSunroof;
		  }
		
		  describe() {
		    return `${this.year} ${this.make} ${this.model} in ${this.color} color with GPS: ${this.hasGPS} and Sunroof: ${this.hasSunroof}`;
		  }
		}
		
		// CarBuilder class for step-by-step object creation
		
		class CarBuilder {
		  constructor(make, model) {
		    this.make = make;
		    this.model = model;
		  }
		
		  setYear(year) {
		    this.year = year;
		    return this;
		  }
		
		  setColor(color) {
		    this.color = color;
		    return this;
		  }
		
		  addGPS() {
		    this.hasGPS = true;
		    return this;
		  }
		
		  addSunroof() {
		    this.hasSunroof = true;
		    return this;
		  }
		
		  build() {
		    return new Car(this); // Builds and returns the Car object
		  }
		}
		
		// Creating the object using the builder
		
		const car = new CarBuilder('Tesla', 'Model S')
		  .setYear(2024)
		  .setColor('Red')
		  .addGPS()
		  .build();
		
		console.log(car.describe());	
```
	

		
				


- Prototype
	 Creates new objects by copying or cloning an existing object, avoiding subclassing
		- javascript utilize this design pattern
```
 function Car(make, model) {
  this.make = make;
  this.model = model;
}

Car.prototype.getDetails = function () {
  return `${this.make} ${this.model}`;
}; const car1 = new Car('Toyota', 'Camry');
const car2 = new Car('Honda', 'Accord'); console.log(car1.getDetails()); // Output: Toyota Camry  
console.log(car2.getDetails()); // Output: Honda Accord
```
			
				

- Singleton
	 Ensures a class has only one instance and provides a global point of access to it (base class) and prevents multiple instance
		- Determines how to use inheritance and delegation
		- Advantages: Lazy Initialization (instance will be created when required), Thread safe, double checked locking, static block initialization
		- Use case: logger, cache objects, file system, database pool connection
	    
	 
Behavioural
Object interacted focusing on communication and responsibility
- Chain of Responsibility
	- Pass a request along a chain until a handler processes i
	- pros: Flexible and extensible, separation of concern,
	- cons: hard to debug
	- example: Middleware stacks, validation pipelines, message filtering
```
	 app.use((req, res, next) => { console.log('Auth Check'); next(); });
	  app.use((req, res, next) => { console.log('Logging'); next(); });

```
- command
	- Encapsulate a request as an object, allowing undo/redo and queuing.
	- pros: Supports undo/redo, Commands can be queued and logged.
	- cons: Adds layers of abstraction, Overhead
	- example: job queues, cli tools
```
	class PrintCommand {
	  execute() { console.log("Printing..."); }
	}
	class CommandInvoker {
	  constructor() { this.commands = []; }
	  run(command) { this.commands.push(command); command.execute(); }
	}

```
- interpreter
	- Centralize complex communication between many objects.
	- pros: Reduces direct dependencies, Simplifies object communication
	- cons: Central mediator can become a bottleneck, Harder to scale with complex rule
	- example : WebSocket chat rooms, event hubs, service coordination, Chat server acting as a central hub. 
- observer
	- Notify multiple objects when the state of one object changes
	- Example: event emitter
	- pros: loose coupling, scales well for event driven
	- cons: hard to debug, risk of memory leak
	- use case: chat, notification
- state
	- Allow an object to change its behavior when its internal state changes.
	- pros: Cleaner state-specific logic., Makes transitions explicit
	- cons: Too many state classes if overused,Can add complexity
	- example : Order processing, authentication flows, UI modes.
```
	- class Order {
		  constructor() { this.state = 'pending'; }
		  next() {
		    if (this.state === 'pending') this.state = 'shipped';
		    else if (this.state === 'shipped') this.state = 'delivered';
		  }
		}

```
- strategy
	- Define a family of algorithms, encapsulate each one, and make them interchangeable
	- example: Choosing a payment method at runtime (stripe, razorpay, gpay)
	- pros: easy to switch algorithm
- template
	- Define skeleton of an algorithm, letting subclasses override steps.
	- example : Email sending flow with customizable content,Report generation, workflow engines, abstract controllers.
	- pros: reusable logic, workflow inheritence
	- cons: Difficult to change individual steps independently
```
	- class EmailTemplate {
		  send() {
		    this.connectSMTP();
		    this.compose();
		    this.deliver();
		  }
		  connectSMTP() { console.log("Connecting SMTP..."); }
		  compose() { throw new Error("Must implement compose"); }
		  deliver() { console.log("Email sent"); }
       }

```
- visitor

Structural
how classes and objects are composed to form larger structures — while keeping them flexible and efficient

- adapter
	Converts the interface of one class into another that a client expects
		- class and object
		- Format the data structure according to client needs
		- Example - Database adapter, Plug, system integration
		- Advantage : separation of concern, integration of legacy code, interface compatability
		- cons: performance overhead (slows down response)
- bridge (plugin)
	Separates an object's abstraction from its implementation
	- decouples an abstraction from its implementation so that the two can vary independently
	- Example: Logger abstraction that supports multiple outputs (info, warn, error, debug) here logger acts as abstraction and rest are treated as implementation
```
	   // Abstraction
	   class RemoteControl {
	  constructor(device) {
	    this.device = device;
	  }
	
	  togglePower() {
	    this.device.power();
	  }
	}
	
	   // Implementation
	   class TV {
	  power() {
	    console.log("TV power toggled");
	    }
	   }
	
	// Usage
	const tvRemote = new RemoteControl(new TV());
	tvRemote.togglePower();
```
- composite
	Creates a tree structure of objects, allowing you to treat simple and complex elements uniformly
	 - Folder can file and sub folder files, each can be selected can check size and it can be deleted same like tree object can have leaf and container nodes it can be treated in same way
	 - pros: unified interface, recursive structure,flexibility
	 - cons: overhead
- decorator
	Dynamically adds responsibilities to objects
	 - Add new responsibility to object without altering original structure
	 - example: express middleware, logging wrapper, feature flags, caching layer
	 - Pro: open closed principle, flexibility, modularity
	 - cons: complexity, order of wrappings
```
	 - // Base component
		class Coffee {
		  cost() {
		    return 5;
		  }
		}
		
		// Decorator
		class MilkDecorator {
		  constructor(coffee) {
		    this.coffee = coffee;
		  }
		
		  cost() {
		    return this.coffee.cost() + 2;
		  }
		}
		
		class SugarDecorator {
		  constructor(coffee) {
		    this.coffee = coffee;
		  }
		
		  cost() {
		    return this.coffee.cost() + 1;
		  }
		}
		
		// Usage
		let basicCoffee = new Coffee();
		console.log("Basic:", basicCoffee.cost()); // 5
		
		let withMilk = new MilkDecorator(basicCoffee);
		console.log("With Milk:", withMilk.cost()); // 7
		
		let withMilkAndSugar = new SugarDecorator(withMilk);
		console.log("With Milk & Sugar:", withMilkAndSugar.cost()); // 8
```
- facade
	Provides a simplified interface to a complex system
	 - object that serves as a front-facing interface masking more complex underlying or structural code.
	 - A class that calls those subsystems in the correct sequence, hides complexity, and provides a unified interface
	 - pro: loose coupling, simplifies complex api, reduce dependency on internal subsystem
	 - example: payment processing (sdk like stripe can acts as facade without exposing its internal implementation), 3rd party lib, 
- flyweight
	Enables the efficient sharing of objects with minimal memory usage or improve performance by sharing common data between similar objects.
	 - DOM rendering, Caching, text editors
- proxy
	Provides a placeholder for another object, allowing you to control access or add functionality
		- surrogate or placeholder for another object to control access to it.
		- acts as an intermediary between a client and a target object. It can add behavior such as access control, caching, logging, or lazy initialization