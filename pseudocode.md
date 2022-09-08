# How to make a cup of coffee using an Aeropress

## Process Initial Draft:
I *get* the aeropress(plunger, brew chamber, and filter cap), one aeropress filter, one coffee cup, one liquid measuring cup (one cup *minimum*), electric kettle with temperature control, kitchen scale, coffee (16 grams ground), water (* 0.6  liter minimum* for kettle), one teaspoon, and one timer.

Put the aeropress filter in the filter cap and screw it clockwise on the brew chamber.

Pour *at least* 0.6 liters of water in the electric pitcher but *no more* than 1.7 liters.  Press power *button* followed by temperature control *increment* button until the screen reads 175 degrees *if* it reads higher then *decrement* down to 175 degrees.

Place the aeropress on the scale, zero the scale, and weigh out 16 grams of coffee beans directly into the brew chamber, *if* I weigh too much, I put them back in the bag of coffee *else if* I weigh too little, I add more coffee to the scale, *else* I proceed to the next step.

Add water and *stop* if water exceeds top of brew chamber.  Place plunger inside of brew chamber and Set timer to two minutes

---

## About:
- Coffee is a beverage that is derived from two basic ingredients: water and roasted coffee beans.
    - Roasted coffee beans can be sourced pre-ground or whole-bean.  Whole-beans should be ground prior to use in order to extract the most compounds.
    - Note that water quality will have a direct impact on the quality of the final product.  This means if you don't like the taste of your tap water then you should consider filtering your water or using store bought water.
- The other factors involved include: time, water temperature, brew method, technique, as well as coffee bean origin, grind size, age (roast date until consumption).
- Coffee can be brewed using various methods but for this case we will focus on hot water immersion brewing using an Aeropress.


## Use Case: 
< As a coffee drinker, I want to make a quality cup of hot coffee.
---

## INIT: Coffee Brewing Variables

1. aeropress(brew chamber) = ##aeroPress##
    - #Array# initially containing brew chamber
    - Hollow gray cylinder
    - Filter cap with filter attach to this component
    - Contains the coffee and water during brewing process
    - Plunger is inserted when brewing is completed, this action forces coffee out
2. Plunger = ##aeroPlunger##
    - Gray cylinder with a black, rubber cup at the end
    - Inserted into the brew chamber through the end opposite of the octagonal end
        -Inserted rubber cup side down
    - Used to force the brewed coffee through the filter and into the cup
3. Aeropress filter cap = ##aeroFilterCap##
    - Houses the filter and attaches to the octagonal end of the brew chamber
    - Prevents coffee grounds from passing through to the cup
2. Aeropress filter = ##filter##
    - Small, white, paper disc used to filter out grounds
    - Placed inside of the filter and screwed into the brew chamber
3. Coffee cup = ##coffeeCup##
    - Instrument used to hold final coffee product
4. Liquid measuring cup = ##measureCup##
    - Instrument used to measure water and fill the kettle
5. Kettle = ##electricKettle##
    - Appliance used to heat water
    - Has a control panel used to select appropriate tempurature
    - Has a display to show temperature selection and if water is preheated
    - Properties
        - electric
        - minCapacity = 0.6 liter
        - 1maxCapcity = 1.6 liter
6. Kitchen scale = ##scale##
    - Small scale used to measure ingredient weights
    - Has a control panel used to zeroize (exclude) weight of item currently on scale
    - Has a display to view item weight in grams
7. Coffee = ##coffee##
    - Coffee beans in a bag that were bought from a grocery store
    Properties
        - ground
8. Water = ##water##
    - Water in liquid state
    Properties
        - tap
9. Teaspoon = ##teaspoon##
    - Utensil used to sture the coffee during brew process
10. Timer = ##timer##
    - Item used to track time lapse during brew process

---
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


**VARIABLES**

suppliesList: aeroPress, aeropress filter, aeroFilterCap, aeroPlunger, coffeeCup, liquid measuring cup, electricKettle, kettleControlPan, kitchen scale, coffee (16 grams ground), water (0.6 L / minimum), teaspoon, and timer

**ARRAY**

aeroPress = [brewChamber]
aeroFilter = [aeroFilterCap]
