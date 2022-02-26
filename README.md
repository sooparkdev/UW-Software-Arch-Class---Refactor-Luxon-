# INFO 443 Project 2 Luxon Software 

## About the Luxon Software
<p><strong> 1) What is the software system, and what does it do? </strong></p>
<p>Luxon is a JavaScript library where it allows software developers to work with dates and times when writing JavaScript code.</p>

<p><strong> 2) Who created the software, and who currently "maintains" it? (Was it developed by a large company or an independent developer? Who seems to be in charge of approving changes to its code/architecture?) </strong></p>
<p>Luxon was created by an independent developer, Isaac Cambron (icambron on GitHub), after working on a different date and time-related Javascript library and identifying potential areas of improvement. Luxon is maintained and collaborated on by a community of 170 contributors with it being an open source software.</p>

### 4 | Styles & Patterns
<p><strong>Architectural Style</strong></p>
Luxon Package doesn’t follow any specific architectural style since it’s a Javascript library that relies on API, meaning that the user will send a specific request to the system and in turn get the result carried out by the library’s various functions, classes and methods. 

<p><strong>Patterns</strong></p>
<p>One design pattern Luxon uses is the <strong>Template Method pattern</strong>, in which a “template” class with abstract operations is overridden by subclasses that define more concrete behavior for the operations. In Luxon, this is evident in the Zone class and subsequent subclasses of Zone:FixedOffsetZone, IANAZone, InvalidZone, and SystemZone (all found in the zones folder inside src). The parent class, Zone, creates the overall class and includes many abstract methods, such as getting the type and name of the object. For Zone, the return value of these methods are all “Zone is an abstract class”. The subclasses then take these functions and override their behavior to provide specific responses, such as the actual object type or the timezone format. The purpose of using this pattern is to create a general “template”, almost like a wireframe, where the subclasses then fill in the holes to form more concrete classes and complete the desired actions. This pattern also helps reduce code repetition, as any shared behavior between the subclasses can be consolidated in the Zone parent class.
</p>
<p> The second design pattern embedded in Luxon is the <strong>Prototype Design Pattern</strong>, a creational design pattern that lets programmers copy existing objects without making the code dependent on their classes. In Luxon, this is evident in the Datetime class when it creates a Clone method for “setters” to use to create a new object while only changing some of the properties. We can see this particularly with a setter class called setZone using Clone to create a new Datetime object (copy along all its old properties: Zone, Locale, Invalid, etc), and then specify that if the time is not in the same time zone, this class could create a new prototype of the old Datetime object in order to report different local times and consider DSTs when making computations. The purpose of this pattern is to reduce the number of subclasses that only differ in the way they initialize their respective objects. This pattern also helps get rid of repeated initialization code in favor of cloning pre-built prototypes. 
</p>
