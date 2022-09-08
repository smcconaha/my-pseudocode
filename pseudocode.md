# How to make a cup of coffee using an Aeropress

## Use Case: 
< As a coffee drinker, I want to make a cup of coffee.
------------------------------------------------
### Initial Draft:
I *get* the aeropress(plunger, brew chamber, and filter cap), one aeropress filter, one coffee cup, one liquid measuring cup (one cup *minimum*), electric kettle with temperature control, kitchen scale, coffee (16 grams ground), and two cups of water (*minimum* for kettle), and one teaspoon, one timer.

Put the aeropress filter in the filter cap and screw it clockwise on the brew chamber.

Pour *at least* two cups of water in the water pitcher but *no more* than 8 cups.  Press power *button* followed by temperature control *increment* button until the screen read 175 degrees *if* it reads higher then *decrement* down to 175 degrees.

Place the aeropress on the scale, zero the scale, and weigh out 16 grams of coffee beans directly into the brew chamber, *if* I weigh too much, I put them back in the bag of coffee *else if* I weigh too little, I add more coffee to the scale, *else* I proceed to the next step.

Add water and *stop* if water exceeds top of brew chamber.  Place plunger inside of brew chamber and Set timer to two minutes

---------------------------------------------------------


START:

GET suppliesList

Place (SHIFT) filter inside aeroFilter 

//this means filter + aeroFilterCap

Attach (PUSH) aeroFilter to brewChamber

//now have an array called Aeropress

Place 

IF coffee >= 16 grams AND water >= 2 cups THEN

GET array
INIT brewCoffee

ELSE IF coffee < 16 grams AND water >= 2 cups THEN

// GET coffee from store

ELSE 

// GET water from store OR faucet

CASE (if taste bad)

FUNCTIONS**

function brewCoffee 
    Pass In 

ARRAY

suppliesList: aeropress, one aeropress filter, aeroFilterCap, one coffee cup, one liquid measuring cup, electric kettle with temperature control, kitchen scale, coffee (16 grams ground), and two cups of water, and one teaspoon, one timer

SUBARRAY

aeroPress = [plunger, brewChamber]
aeroFilter = [aeroFilterCap]