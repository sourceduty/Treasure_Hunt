![Treasure Hunt](https://github.com/sourceduty/Treasure_Hunt/assets/123030236/9b821617-11f2-4d6f-936e-4fb9a3ff1781)

To play **Treasure Hunt**, your objective is to find the buried treasure within 35 steps. You start the game 25 steps away from the treasure, but the exact direction is unknown—it could be left, right, forwards, or backwards. 

### ChatGPT Version

Here's how you can play:

1. Choose Your Direction: On each turn, decide whether you want to move left, right, forwards, or backwards.

2. Make a Move: After choosing a direction, you take a step in that direction.

3. Receive Feedback: After each move, I'll tell you how far you are from the treasure and how many steps you have remaining out of the initial 35.

4. Adjust and Continue: Use the feedback to decide your next move. The goal is to reach the exact spot of the treasure within 35 steps.

The objective is to find the treasure in the least number of steps. 

***

### Python Version

```

# Treasure Hunt Game
# Copyright (C) 2024, Sourceduty - All Rights Reserved.

import random

# Game setup
max_moves = 35
moves_made = 0
treasure_distance = random.randint(1, 25)  # Random distance from the player at the start
player_position = 0  # Starting position

# Introduction
print("Welcome to Treasure Hunt!")
print("Find the hidden treasure within 35 moves.")
print("You can move left, right, forward, or backward.")
print("After each move, you'll be told how far you are from the treasure.")

# Game loop
while moves_made < max_moves:
    direction = input("Which direction would you like to move? (left/right/forward/backward): ").lower()
    if direction in ["left", "right", "backward", "forward"]:
        move = random.randint(1, 5)  # Randomize the move's effectiveness
        if direction == "forward":
            player_position += move
        elif direction == "backward":
            player_position -= move
        # 'left' and 'right' don't change the distance to the treasure in this simple text version
        
        moves_made += 1
        distance = abs(treasure_distance - player_position)
        print(f"You are {distance} steps away from the treasure.")
        print(f"Moves left: {max_moves - moves_made}")
        
        if distance == 0:
            print("Congratulations! You've found the treasure!")
            break
    else:
        print("Invalid input. Please type 'left', 'right', 'forward', or 'backward'.")

if moves_made >= max_moves and distance != 0:
    print("Game Over! You've run out of moves before finding the treasure.")

print("Thank you for playing Treasure Hunt!")

```

***
Copyright (C) 2024, Sourceduty - All Rights Reserved.
