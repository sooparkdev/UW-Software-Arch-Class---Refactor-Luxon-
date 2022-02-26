# INFO 443 Project 2 Luxon Software 

## About the Luxon Software
<p><strong> 1) What is the software system, and what does it do? </strong></p>
<p>Luxon is a JavaScript library where it allows software developers to work with dates and times when writing JavaScript code.</p>

<p><strong> 2) Who created the software, and who currently "maintains" it? (Was it developed by a large company or an independent developer? Who seems to be in charge of approving changes to its code/architecture?) </strong></p>
<p>Luxon was created by an independent developer, Isaac Cambron (icambron on GitHub), after working on a different date and time-related Javascript library and identifying potential areas of improvement. Luxon is maintained and collaborated on by a community of 170 contributors with it being an open source software.</p>

### 4 | Styles & Patterns

<p><strong>Patterns</strong></p>
<p>One design pattern Luxon uses is the Template Method pattern, in which a “template” class with abstract operations is overridden by subclasses that define more concrete behavior for the operations. In Luxon, this is evident in the Zone class and subsequent subclasses of Zone:FixedOffsetZone, IANAZone, InvalidZone, and SystemZone (all found in the zones folder inside src). The parent class, Zone, creates the overall class and includes many abstract methods, such as getting the type and name of the object. For Zone, the return value of these methods are all “Zone is an abstract class”. The subclasses then take these functions and override their behavior to provide specific responses, such as the actual object type or the timezone format. The purpose of using this pattern is to create a general “template”, almost like a wireframe, where the subclasses then fill in the holes to form more concrete classes and complete the desired actions. This pattern also helps reduce code repetition, as any shared behavior between the subclasses can be consolidated in the Zone parent class.
</p>