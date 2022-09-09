# How to make a cup of coffee using an Aeropress

## Process Initial Draft:
I *get* the aeropress(plunger, brew chamber, and filter cap), one aeropress filter, one coffee cup, one liquid measuring cup (one cup *minimum*), electric kettle with temperature control, kitchen scale, coffee (16 grams ground), water (* 0.6  liter minimum* for kettle), one teaspoon, and one timer.

Put the aeropress filter in the filter cap and screw it clockwise on the brew chamber.

Pour *at least* 0.6 liters of water in the electric pitcher but *no more* than 1.6 liters.  Press power *button* followed by temperature control *increment* button until the screen reads 175 degrees *if* it reads higher then *decrement* down to 175 degrees.

Place the aeropress on the scale, zero the scale, and weigh out 16 grams of coffee beans directly into the brew chamber, *if* I weigh too much, I put them back in the bag of coffee *else if* I weigh too little, I add more coffee to the scale, *else* I proceed to the next step.

Add water and *stop* if water exceeds top of brew chamber.  Stir the coffee for about 10 seconds and then press down on the plunger until coffee no additional liquid comes out.

---

## About:
- Coffee is a beverage that is derived from two basic ingredients: water and roasted coffee beans.
    - Roasted coffee beans can be sourced pre-ground or whole-bean.  Whole-beans should be ground prior to use in order to extract the most compounds.
    - Note that water quality will have a direct impact on the quality of the final product.  This means if you don't like the taste of your tap water then you should consider filtering your water or using store bought water.
- The other factors involved include: time, water temperature, brew method, technique, as well as coffee bean origin, grind size, age (roast date until consumption).
- Coffee can be brewed using various methods but for this case we will focus on hot water immersion brewing using an Aeropress.


## Use Case: 
As a coffee drinker, I want to make a quality cup of hot coffee.

---

## INIT: Coffee Brewing Variables

1. aeropress(brew chamber) = **aeroPress**
    - **Array** initially containing brew chamber
    - Hollow gray cylinder
    - Has gold numbers from 1 (octagonal base) to 4 (top) used for coffee and water dosing
    - Filter cap with filter attach to this component
    - Contains the coffee and water during brewing process
    - Plunger is inserted when brewing is completed, this action forces coffee out
2. Plunger = **aeroPlunger**
    - Gray cylinder with a black, rubber cup at the end
    - Inserted into the brew chamber through the end opposite of the octagonal end
        -Inserted rubber cup side down
    - Used to force the brewed coffee through the filter and into the cup
3. Aeropress filter cap = **aeroFilterCap**
    - **Array** initially containing filter cap
    - Houses the filter and attaches to the octagonal end of the brew chamber
    - Prevents coffee grounds from passing through to the cup
4. Aeropress filter = **filter**
    - Small, white, paper disc used to filter out grounds
    - Placed inside of the filter and screwed into the brew chamber
5. Coffee cup = **coffeeCup**
    - Instrument used to hold final coffee product
    - *Properties*
        - minCapacity = 8 oz
6. Liquid measuring cup = **measureCup**
    - Instrument used to measure water and fill the kettle
    - *Properties*
        - minCapacity = 8 oz
7. Kettle = **electricKettle**
    - Appliance used to heat water
    - Has a control panel
    - Has a display
    - *Properties*
        - powerSource = electric
        - minCapacity = 0.6 liter
        - maxCapacity = 1.6 liter
8. Kettle Control Panel = **kettleControlPanel**
    - Contains two buttons, a "+temp" (increment) and a "-temp" (decrement) button used adjust water temperature
9. Kettle Display = **kettleDisplay**
    - An electronic display that shows desired temperature and if water is at desired temperature (preheated)
10. Kitchen scale = **scale**
    - Small scale used to measure ingredient weights
    - Has a control panel
    - Has a display
11. Scale Control Panel = **scaleControlPanel**
- Contains two buttons, a zeroize (exclude) weight of item currently on scale and a button that toggles between grams and ounces
12. Scale Display = **scaleDisplay**
    - An electronic display that shows desired temperature and if water is at desired temperature (preheated)
    - *Properties*
        - powerSource = battery
13. Coffee = **coffee**
    - Coffee beans in a bag that were bought from a grocery store
    - *Properties*
        - grind type = preGround
14. Water = **water**
    - Water in liquid state
    - *Properties*
        - source = tap
        - temperature = ''
15. Teaspoon = **teaspoon**
    - Utensil used to sture the coffee during brew process
16. Timer = **timer**
    - Item used to track time lapse during brew process
17. Electric Outlet = **electOutlet**
    - Power source for electric kettle

---
START:

GET Coffee Brewing Variables

IF coffee >= 16 grams AND water >= 0.6 liters THEN

    FUNCTION makeHotWater
        
        PLUG electricKettle into electOutlet

        FUNCTION addWater
            GET measureCup
            
            PRECONDITION: water is < measureCup.maxcapacity AND water is < electricKettle.maxcapacity
            WHILE water is < electricKettle.minCapacity
                INCREMENT water
            ENDWHILE    
        END FUNCTION     
        
        PRECONDITION: water.temperature is < 175 degrees
        WHILE kettleDisplay READs < 175 degrees
            INCREMENT kettleControlPanel temperature by pressing temp+ button 
        ENDWHILE

        FOR each time you check the kettleDisplay and it DOES NOT EQUAL "preheated"
            wait one minute
        ENDFOR 
    END FUNCTION

    FUNCTION aeroAssembly

        PLACE filter inside aeroFilter (SHIFT)

        ATTACH aeroFilterCap to aeroPress octagonal side (PUSH)
            WHILE aeroFilter is loose
                turn clockwise
            ENDWHILE   
    END FUNCTION
    
    FUNCTION measureCoffee
        
        PLACE aeroPress on scale with aeroPress.aeroFilterCap facing down
        
        WHILE scaleDisplay DOES NOT EQUAL 0
            press zeroize on scaleControlPanel
        ENDWHILE
            
        WHILE scaleDisplay < 16 grams
            INCREMENT coffee
        ENDWHILE   
    ENDFUNCTION

    FUNCTION brewCoffee
        PLACE aeroPress on coffeeCup with aeropress.filterCap facing down
        
        WHILE aeropress water level DOES NOT EQUAL 4
            add hot water from electricKettle
        ENDWHILE

        STIR coffee AND water inside aeroPress with spoon for 10 seconds

        INSERT aeroPlunger rubber cup facing down, inside of aeroPress

        WHILE aeroPress contains liquid
            PRESS aeroPlunger down gently
        ENDWHILE
    END FUNCTION 

    REMOVE aeroPress from coffeeCup

    WHILE coffeeCup DOES NOT EQUAL empty
        drink brown liquid
    END WHILE   
ELSE IF coffee < 16 grams AND water >= 2 cups THEN

    GET coffee from grocery store OR GET coffee from local coffee shop
ELSE IF coffee > 16 grams AND water < 2 cups THEN

    GET water from grocery store
ELSE 
    GET water AND coffee from grocery store
ENDIF

//END PROGRAM
