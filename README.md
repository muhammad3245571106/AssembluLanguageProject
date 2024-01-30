# Number crushing game on 10x10 matrix
This project is a number-crushing game in which the user can update the location of characters and if some characters of the same ASCII come close to each other and make a group then they'll be crushed and the user will get a score for it.
I built this using Assembly language. 
I work in MASM in Visual Studio with Irvine Library for this project.

# Game Description
Number Crush is a "match-three" game, where the core gameplay is based on
swapping two adjacent random values among several on the game board to make a
row or column of at least 3 matching random values. In this match, the matched
random values are removed from the board, and random values above them fall
into the empty spaces, with new random values appearing from the top of the board.
This may create a new matched set of random values, which is automatically cleared
in the same manner. The game is split into many levels, which must be
completed in sequence.
# LEVELS
## Level 1
Level 1 has a 10x10 board. When a number is swapped with another number, if a combo
exists, the combo is crushed, and dropped, and the score is updated accordingly. Otherwise, the numbers
are swapped back! The board is filled with random numbers from 1 to 5. It has bomb ‘B’ too.
When a number is swapped with a bomb, all of its occurrences are destroyed.
## Level 2
It has a plus shape board with the same functions as level 1. The board is filled with random
numbers from 1 to 4.
## Level 3
It has the same board shape as level 1 but we have blockers ‘X’ too to restrict player
movement.
.
### How to Update SCORE AND MOVES
1) During crushing, the score added depends on the size of the combo. A combo of 3 adds 3 to
the score. A combo of 4 will add 4 and so on.
2) During the explosion, it is different though. The added score depends on how many
occurrences are destroyed and from which location they are destroyed. If a number is at
the bottom, more numbers will have to be dropped from the top and hence more scores.
3) The user is given a total of 15 moves in each level. When all moves are finished, the user is
promoted to a new level and moves are again reset to 15.

### File Handling
• All Individual-level scores will be saved in the file.
• Stores the highest score and player name in the same file.
• Record in a file should look like in the format given below
Ali Raza
Level 1: 20
Level 2: 30
Level 3: 46
Highest Score: 46

### BONUSES
• When a bomb is used, all occurrences of the exploding row/col are first highlighted for a
second, then the explosion proceeds.
• If after swapping, no combo exists, the numbers are swapped back.
• Changed background and look of level 3.
• The string ‘crushing’ is displayed when combos are being crushed and the score is being
updated.
• ‘Explosion’ is displayed when a bomb destroys a row or col in the board.

### Divide and Conquer
You need to write different procedures to help yourself out in this project. You can use some
of these procedures (not mandatory) for performing the game. And you also need to write extra
procedures for complete functionality. The main method should consist of only calling other
procedures.
* populateBoard (.)
It populates the board using random numbers.
drawBoard (.)
This includes drawing borders.
* updateBoard (.)
This function checks for combinations, crushes them, auto-fills, and drops until all the
combos are removed from the array. It makes use of another function checkCombo which is
called in a loop unless and until the value of the ‘crush’ variable is set to 0. 0 means there are no
more combinations in our board array. Vertical and horizontal combos are checked.
* takeInput (.)
It takes input from two cells. Then if cells are adjacent, they are swapped. If no combo is
formed after swapping, the no’s are swapped back.
* initiateBomb (.)
If any no. is swapped with a bomb, it destroys all values of that row or column through
which number is swapped by the bomb.
* drawString (.)
This function draws the player's name, and score, and moves left on the top. Along with this,
it also shows the current level and strings of ‘explosion’ and ‘crushing’.
