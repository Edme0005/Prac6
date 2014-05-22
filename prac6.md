Prac6
=====
If we break the system into main parts:
-	Baggage check-in.
-	Baggage carrousel.

Check-in system is easily tested, the system can:
-	Set Destination (gate, localised within airport)
-	Associate barcode with destination.
-	Print label.

This is easily unit tested and would require very little hardware to test, could be tested without airport being online.
The baggage carrousel requires much more testing and has a greatly increased complexity over other parts of the system. Would require hardware nearly before starting to allow for adequate testing to be performed during development. 
-	Start small, track a bag down a single conveyor belt.
-	Have 2 conveyor belts that track each other’s load, slowing or stopping the first when the second is full.
-	Move on to multiple tracks with off ramps, and work on diverting bags onto a different track.
-	Combine the last 2, making sure bags are still diverted even when 1 track gets full.
-	Continue to build up from here, continuously adding functionality while ensuring original functionality still works.

The three most important types of tests:
-	Unit – of each of the tracks functionality: monitoring, tracking, routing, error handling (stuck bags), congestion control, etc.
-	Integration – to ensure the tracks function together.
-	Prototyping – the hardware is a major factor on how the system will work.

Three types of testing that you think to be much less important:
-	System tests - will be necessary, but require everything to be complete and if major errors are discovered here it will be too late. This should defiantly be performed but only as a final integration test, and should only be intended to catch minor errors or errors in the building of the system, not any design issues.
-	Low volume beta tests – These will not stress the system adequately, and provide similar issues as above. A high volume test will be beneficial to properly stress test the system, but is difficult to implement in this situation.
-	Informal code reviews – This will provide little assistance on its own as most of the issues will be around the actual hardware of the system and not so much code errors.

The main problem with such a large complicated hardware-driven development is that once the system is built and in place it’s too late to test and change its design. The system needs to be built around its design and limitations, not the other way around. It is essential to test, find these limitations and design solutions as early as possible, and ensure that major physical limitations are found before the whole system is implemented.
