# How to make a cup of coffee using an Aeropress

## Use Case: 
< As a coffee drinker, I want to make a cup of coffee.
------------------------------------------------
### Initial Draft:
I *get* the aeropress(plunger, brew chamber, and filter cap), one aeropress filter, one coffee cup, one liquid measuring cup (one cup *minimum*), electric kettle with temperature control, kitchen scale, coffee (16 grams ground), and two cups of water (*minimum* for kettle), and one teaspoon, one timer.

Put the aeropress filter in the filter cap and screw it clockwise on the brew chamber.

Pour *at least* 0.6 liters of water in the electric pitcher but *no more* than 1.7 liters.  Press power *button* followed by temperature control *increment* button until the screen reads 175 degrees *if* it reads higher then *decrement* down to 175 degrees.

Place the aeropress on the scale, zero the scale, and weigh out 16 grams of coffee beans directly into the brew chamber, *if* I weigh too much, I put them back in the bag of coffee *else if* I weigh too little, I add more coffee to the scale, *else* I proceed to the next step.

Add water and *stop* if water exceeds top of brew chamber.  Place plunger inside of brew chamber and Set timer to two minutes

---------------------------------------------------------


START:

GET suppliesList

IF coffee >= 16 grams AND water >= 0.6 liters THEN

    function makeHotWater
        pour water in electricKettle
        
        PRECONDITION: waterTempurature is < 175 degrees
        WHILE kettleControlPanel READs < 175 degrees
            INCREMENT kettleControlPanel tempurature by pressing temp+ button 
        ENDWHILE

        FOR each time you check the kettleControlPanel and it DOES NOT EQUAL "preheated"
            wait one minute
        ENDFOR

        water = hotWater   
    
    END FUNCTION
    
    function measureCoffee
        place aeroPress on scale
        
        zeroize scale
        
        PRECONDITION: scale shows that coffeeWeight is < 16 grams
        WHILE coffeeWeight < 16 grams
            INCREMENT coffeeWeight
        ENDWHILE

        
        coffeeDose
    ENDFUNCTION


    function brewCoffee
        PASS IN: coffeeDose
        PASS IN: hotWater
        
        PASS OUT: brewedCoffee
    END FUNCTION 


ELSE IF coffee < 16 grams AND water >= 2 cups THEN

    GET coffee from store

ELSE 

    GET water from store OR faucet

ENDIF

CASE (if taste bad)

FUNCTION aeroAssembly

    Place (SHIFT) filter inside aeroFilter 

    //this means filter + aeroFilterCap

    Attach (PUSH) aeroFilter to aeroPress

    //now have an array called aeropress of [brewChamber with aeroFilter *subarray*]

END FUNCTION

makeHotWater
    PASS IN: water to electricKettle
    PASS OUT: water at 175 degrees
END FUNCTION


function brewCoffee
    PASS IN: coffeeDose
    PASS IN: hotWater
    PASS OUT: brewedCoffee
END FUNCTION


**FUNCTIONS**

brewCoffee 
    PASS IN: coffee
    PASS IN: hotWater
    PASS OUT: 
END FUNCTION    

aeroAssembly

    Place (SHIFT) filter inside aeroFilter 

    //this means filter + aeroFilterCap

    Attach (PUSH) aeroFilter to aeroPress

    //now have an array called aeropress of [brewChamber with aeroFilter *subarray*]
END FUNCTION


**ARRAY**

suppliesList: aeroPress, aeropress filter, aeroFilterCap, aeroPlunger, coffeeCup, liquid measuring cup, electricKettle, kettleControlPan, kitchen scale, coffee (16 grams ground), water (0.6 L / minimum), teaspoon, and timer

**SUBARRAY**

aeroPress = [brewChamber]
aeroFilter = [aeroFilterCap]
