Test Plan
=========

Introduction
-----------
The project being tested is the Serval-dna repository.
The process of testing will be fuzz testing the network protocol,
this is the process of passing unexpected data to a layer in an attempt to see how it handles it.
It can either be an unintelligent order of bits that are being flipped,
or it can be a planned out process to ensure all layers or the application are targeted, not just surface layers.
This will require changing two key parts of the programme.

Required Recourses
------------------
Serval-dna repository - with all dependencies necessary to compile it.

What will be tested
-------------------
- The capability of the application to handle incorrect data from the network layer.
- To start the testing will just pass a rudimental series of flipped bits, 
as no fuzz testing has been implemented it is expected to get results.
- As testing continues the testing will be adapted to have a more systematic approach.

The programme will be modified so that the Serval server, will read in a regular packet, then pass it on internally (giving the server the impression that the incoming packet has been flipped).

The necessary changes
---------------------
Config - add options to allow fuzz testing to be set.

packetOkOverlay - add overloaded method for performing fuzz testing if set in config, this is a server side function that will give the illusion that the incoming packet was in a flipped form.

Create new testing file to allow structured testing to be performed.

Test Process
------------
- flip bit.
- if test does not fail, flip another bit.
- if test fails, record the bitstring that failed
- attempt to reproduce it.
- document dump from testframework, the bitstring that failed, and whether it was reproducible.
- continue flipping bits.

Potential modifications
-----------------------
May flip many bits, not just 1 at a time.

May restart if does not fail (until all combinations are finished.)
  Then move onto next level etc.
