# Pseudocode for Fantasy Attack (Space Invaders Reskin)

## Initialize Game

START
SET screen width and height
CREATE player at the bottom center of the screen
CREATE a grid of fantasy creatures at the top
SET player's score to 0
SET player's lives to a specific number (e.g., 3)
CREATE an empty list for Fireblast (player's and creature’s)
SET game state to "RUNNING"

## Game Loop

WHILE game state is "RUNNING":
    CLEAR the screen
    DRAW player, creatures, Fireblast, and score

    # Handle Player Movement
    IF left key is pressed AND player is not at the screen's edge:
        MOVE player left
    IF right key is pressed AND player is not at the screen's edge:
        MOVE player right
    
    # Handle Shooting
    IF shoot key is pressed:
        CREATE a new Fireblast at player's position
        ADD the Fireblast to the list of Fireblasts
    
    #  Move Fireblasts
    FOR each Fireblast in Fireblasts:
        MOVE Fireblast upward (if player's Fireblast) or downward (if creature’s Fireblast)
        IF Fireblast goes off-screen:
            REMOVE the Fireblast
    
    # Creatures Movement
    MOVE creatures horizontally
    IF any creature reaches screen edge:
        MOVE creatures downward
        REVERSE creature horizontal direction
    
    # Creature Shooting
    RANDOMLY select creatures to shoot Fireblasts downward
    
    # Collision Detection
    FOR each Fireblast:
        IF Fireblast collides with creature:
            REMOVE Fireblast and creature
            INCREMENT player's score
        IF Fireblast collides with player:
            REMOVE Fireblast 
            DECREMENT player's lives
    
    # Check Game Over Conditions
    IF any creature reaches the player's position:
        SET game state to "GAME OVER"
    IF player's lives are 0:
        SET game state to "GAME OVER"
    IF all creatures are destroyed:
        SET game state to "WIN"
    
    REFRESH the screen

## End Game

IF game state is "WIN":
    DISPLAY "You Win!" message
ELSE IF game state is "GAME OVER":
    DISPLAY "Game Over" message
DISPLAY final score
