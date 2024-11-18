# Pseudocode for Fantasy Attack (Space Invaders Reskin)

Team Members: Lily Wright, Miranda Torres-Martinez Client: Ms. Kennedy/ Ms. Charlie Date: 11/18/24

## Initialize Game

    START
        SET screen width and height
        CREATE knight (player) at the bottom center of the screen
        CREATE a grid of dragons (enemies) at the top in rows and tiers
        SET knight's lives to 3
        SET knight's score to 0
        CREATE an empty list for arrows (knight's projectiles)
        CREATE an empty list for fireballs (dragons' projectiles)
        SET game state to "RUNNING"

## Game Loop

    WHILE game state is "RUNNING":
        CLEAR the screen
        DRAW knight, dragons, arrows, fireballs, score, and lives

        # Handle Knight Movement
        IF left key is pressed AND knight is not at the left edge:
        MOVE knight left
        IF right key is pressed AND knight is not at the right edge:
        MOVE knight right

        # Handle Shooting
        IF shoot key is pressed:
            CREATE a new arrow at knight's position
            ADD the arrow to the list of arrows

        # Move Arrows
        FOR each arrow in arrows:
            MOVE arrow upward
            IF arrow goes off-screen:
                REMOVE the arrow

        # Move Dragons
        FOR each dragon:
            MOVE dragons horizontally
            IF dragons reach screen edge:
                MOVE all dragons downward
                REVERSE horizontal direction

        # Dragon Fireballs
        RANDOMLY select dragons to shoot fireballs downward
        FOR each fireball in fireballs:
            MOVE fireball downward
            IF fireball goes off-screen:
                REMOVE the fireball

        # Collision Detection
        FOR each arrow:
            IF arrow collides with a dragon:
                REMOVE the arrow and dragon
                INCREMENT knight's score

        FOR each fireball:
            IF fireball collides with knight:
                REMOVE the fireball
                DECREMENT knight's lives

        # Game Over Conditions
        IF any dragon reaches the knight's position:
            SET game state to "GAME OVER"
        IF knight's lives == 0:
            SET game state to "GAME OVER"

        # Victory Condition
        IF all dragons are destroyed:
            SET game state to "VICTORY"

        REFRESH the screen

## End Game

    IF game state is "VICTORY":
        DISPLAY "Victory! You have slain all the dragons!"
    ELSE IF game state is "GAME OVER":
        DISPLAY "Game Over. The castle has fallen."
    DISPLAY final score
