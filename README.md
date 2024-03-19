# my-pseudocode

This pseudocode draws cards from a standard Magic the Gathering deck and
analyzes those cards to see whether or not it is a worthwhile hand to keep.

A worthwhile hand is determined as the following:
1. There must be between 3 and 4 lands.
2. There must be at least 2 creatures.
3. There must be at least 2 cards with mana values smaller or equal to the amount of lands.
4. There must be at least 1 card with a mana value greater than the amount of lands.

If it is a worthwhile hand, then the program ends. If it is not a worthwhile
hand, then the program mulligans (shuffles the hand back into the deck and redraws, starting the 
process/program over).