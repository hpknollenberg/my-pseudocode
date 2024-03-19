```
START

INIT
    deck = [[Name, Type, ManaValue], [Name, Type, ManaValue], ...58]
    hand = []

    goodHand = [3/4, 2, 2, 1] //[lands, creatures, mv<=lands, mv>lands]
    handCheck = []
    goodHandCheck = false

WHILE goodHandCheck = false
    draw()
    analyze()
    goodHandEvaluator()

Function draw
    FOR 7 cards
        move a card (deck[0]) from deck to hand
    ENDFOR

Function analyze
    FOR each card OF hand
        check typeof.card
        IF typeof.card = land THEN
            handCheck[0] += 1
        ELSE IF typeof.card = creature THEN
            handCheck[1] += 1
        ENDIF
        check manavalue.card
        IF manavalue.card <= numberof.land THEN
            handCheck[2] += 1
        ELSE IF manavalue.card > numberof.land THEN
            handCheck[3] += 1
        ENDIF
    ENDFOR

Function goodHandEvaluator
    IF (handCheck[0] = 3 OR handCheck[0] = 4) AND 
        handCheck[1] >= 2 AND 
        handCheck[2] >= 2 AND
        handCheck[3] >= 1 THEN
            goodHandCheck = true
    ELSE THEN
        mulligan()
    ENDIF

Function mulligan
    FOR 7 cards
        move a card (hand[0]) from hand to deck
    ENDFOR
    randomize.deck
```