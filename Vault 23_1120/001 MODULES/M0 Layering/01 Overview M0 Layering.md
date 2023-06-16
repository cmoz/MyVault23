This lecture is about providing an orientation for the course and introducing the notion of layers. It is important to understand that we can work **one layer at a time** to manage the scale and complexity of performing such a simple task as updating a notification count that gets drawn over an app icon on a screen.

# Learning outcome

* Explain the concept of layering in computer systems and apply it to examples of systems in computer organization, and programming  languages. (High-level LC)

# Key concepts to cover (lecture plan)

* Start with a high-level behaviour such as a notification circle appearing on an icon
	* Network event causes an increment in the number of notifications.
	* Piece of code to execute and set a flag into memory;
	* this is also true for keystrokes, touch, mouse clicks, timer events.
* Triggers the execution of small pieces of sequential code (handlers)
	* They read memory, execute some logic, write to memory.
	* Show a simple C statement that increment a variable
	* Show how this statement looks like at the assembly level
	* Show how assembly becomes machine code
* Look at the top-level architecture with CPU/RAM, control unit.
	* Looks at the execution cycle
	* Look how a machine instruction connects to the architecture
* Descend into a block such as multiplexer, RAM unit, Adder.
	* Look at the layout of a small multiplexer as a collection of gates
	* How it applies to opcode
	* How it applied to RAM addresses
* Zoom into a ram cell with 8 stored states
	* Look into the way a single bit is stored 

# Formative assessment


# Summative assessment
None