# Test Plan for Fantasy Attack (Space Invaders)

Team Members: Lily Wright, Miranda Torres-Martinez Client: Mrs. Kennedy/ Ms. Charlie Date: 11/18/24

## 1. Test Plan Overview

- **Objective**: Ensure the game functions as intended, focusing on player actions, dragon behaviors, collisions, scoring, and overall gameplay.
- **Scope**: Testing will cover initialization, core gameplay mechanics, collision detection, user interface, and game state transitions (Victory/Game Over).
- **Exclusions**: Extended features such as multiplayer modes or additional levels (if not implemented).

## 2. Features to Be Tested

1. **Initialization**:
   - Game starts with the knight positioned at the bottom of the screen.
   - Dragons are correctly positioned in rows and tiers.
   - Score and lives are displayed and set to initial values.

2. **Player Controls**:
   - Left and right movement of the knight.
   - Shooting arrows upward.
   - Restrictions on movement (e.g., knight stays within the castle wall boundaries).

3. **Dragon Behavior**:
   - Horizontal movement of dragons.
   - Vertical descent after reaching screen edges.
   - Random fireball attacks from dragons.

4. **Projectile Mechanics**:
   - Arrows move upward and disappear off-screen.
   - Fireballs move downward and disappear off-screen.

5. **Collision Detection**:
   - Arrows hitting dragons (removes dragon and arrow, increases score).
   - Fireballs hitting the knight (removes fireball, reduces lives).
   - Dragons reaching the castle wall (triggers Game Over).

6. **Game States**:
   - Victory condition: All dragons defeated.
   - Game Over condition: Lives reach 0 or dragons reach the castle wall.

7. **User Interface**:
   - Score increments when dragons are hit.
   - Lives decrement when hit by fireballs.
   - Game Over or Victory screen displays correctly.

## 3. Test Environment

- **Hardware**: PC/Console/Device running the game.
- **Software**: Game build, appropriate operating system.
- **Inputs**: Keyboard, mouse, or game controller.
- **Screen Resolution**: Test at various resolutions.

## 4. Test Cases

| **Test Case ID** | **Description**                       | **Expected Result**                                                                 | **Pass/Fail** |
|-------------------|---------------------------------------|-------------------------------------------------------------------------------------|---------------|
| TC01              | Verify game starts correctly         | Knight, dragons, score, and lives are displayed; game is ready to play.             |               |
| TC02              | Test left movement of knight         | Knight moves left and stops at screen edge.                                         |               |
| TC03              | Test right movement of knight        | Knight moves right and stops at screen edge.                                        |               |
| TC04              | Test shooting arrows                 | Arrows fire upward from the knight’s position and disappear off-screen.             |               |
| TC05              | Test arrow collision with dragon     | Arrow removes dragon, arrow disappears, and score increments.                       |               |
| TC06              | Test fireball collision with knight  | Fireball removes one life and disappears.                                           |               |
| TC07              | Test dragon movement horizontally    | Dragons move as a group and reverse direction at screen edges.                      |               |
| TC08              | Test dragon vertical descent         | Dragons descend toward the castle wall when reaching the edge.                      |               |
| TC09              | Test Game Over (castle breached)     | Game Over triggers when dragons reach the castle wall.                              |               |
| TC10              | Test Game Over (lives depleted)      | Game Over triggers when all lives are lost.                                         |               |
| TC11              | Test Victory condition               | Victory triggers when all dragons are defeated.                                     |               |

## 5. Testing Tools

- **Manual Testing**: Primary method for gameplay mechanics.
- **Automation Tools**: For regression testing (if applicable).
- **Bug Tracking**: Use tools like JIRA, Trello, or Bugzilla.

## 6. Test Schedule

- Day 1–2: Initial setup and smoke testing.
- Day 3–5: Core gameplay mechanics testing.
- Day 6–7: UI and state transition testing.
- Day 8: Final regression and performance testing.

## 7. Assumptions

- Game build is stable for testing.
- Inputs and devices are functioning as expected.

## 8. Acceptance Criteria

- All test cases pass.
- No critical or major bugs remain.
- Gameplay is smooth and meets design expectations.
