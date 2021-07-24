# JAVA-GAMEBrick Breaker

Design the traditional brick breaker game with at least the following functionalities:
A bar that moves left and right only by pressing keys on keyboard. Use left and right keys for bar navigation.
A ball that hits the bar and then moves in upward (straight up, left or right) direction and breaks the bricks. (You can replace ball with some other ascii character(s))
Design the game for at least one player and one level.
The time for finishing the game is 2 minutes. If the game ends in 2 minutes the player gets extra points. If it does not end in 2 minutes, the player won’t get any extra points but can keep playing the game.
You can hard-code the position of bricks.
Breaking a brick makes the player earns some points. (you can decide how many)

The brick breaker game needed a way to conveniently store the existence, style, and placement of all the bricks. Since this was implemented in hardware (which tends to be static unlike dynamic programming languages) it made the most sense to have in memory a fixed number of brick memory placeholders. The brick memory placeholders - essentially a 2D array - simply held all the information needed to describe a brick and importantly whether the brick should “exist” or not. The brick memory placeholders were four bytes per brick and there was allocated space for 128 bricks although only 35 were used in the final implementation. 
The brick array consisted of the following: 
4 bits|   4 bits|  9 bits|   10 bits|   9 bits|   Exist Style Blank Hor. Position Vert. Position 

Show on display the total points gained by the player.
The ball movement depends on where it hits the bar.
If the ball does not hit the bar, it falls down (to the end of screen) and the player loses one life. Show on display remaining and total lives.

1) If there were a wall collision, the ball would be placed adjacent to the wall and the velocity would change direction.
 2) Else, if there were a brick collision, the ball would have to bounce appropriately. Bouncing off the sides of the brick was fairly trivial, but corners were much trickier. A simple approximation was used to either treat the collision as a side collision or a 45 degree angle collision.
 3) Else, if there were a paddle collision, the ball would have its velocity directed upward and the paddle’s velocity would be scaled and added to the ball.
 4) Else, the ball would be in free space and acted under a constant pull of gravity. 

The player has a total of three lives.
If the player loses all lives the game ends.
The display should be colorful.
The game should end normally after all bricks are broken by the player. (you should play the game at least once till the end before submitting.)
A sample display is attach as image.
