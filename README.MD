Solver
The Solver was implemented as specified in the prompt. The only
time it acts incorrectly is when it receives a tray with more 
than one '\*.' In this case the program will try to replace both
blanks with the same letter instead of trying all the options.
(Example: dst\*slf\* -> dstAslfA.) I decided to use a TRIE to 
store the dictionary with a recursive search function. This 
structure is very fast and can search a word in milliseconds.
The Solver starts by finding all permutations of the tray for
all the substrings. Then all the tiles adjacent to existing 
letters are found(anchors). Then each permutation
is placed at each anchor's row or column letter by letter 
skipping any existing letters. Each permutation is tried in 
different locations within a column or row. As the word
is being placed, a string keeps track of the entire word that 
was formed and checks the dictionary. If there are blanks
in the tray a separate branch is used. The tree has a function
that searches the tree for the potential values of the blanks.
When it encounters an astrix as the
next character, it returns all the children of that node. This 
way the algorithm only attempts values in the blanks that form
real words. The board is a 2D array of board squares. Each 
boardSquare has a temporary, final and best placement letter. 
The temp letter allows the program to try new board 
configurations while the best move letters track the highest 
scoring move. Blanks spaces on the Board are stored as a '#'.
Then the algorithm does cross-checks and scoring.

Scrabble
The scrabble game was implement according to the prompt. To 
play a word click a tile to pick it up and click a tile to place
it. When you are ready to submit your move click submit move. 
If the word is valid the computer will take its turn, if its not
a valid word the tiles will return to your tray, so you can 
retry. Blank tiles can be played by clicking, entering 
the letter you want the blank tile to be, and placing normally.
If the word is not valid then the blank tile is reset. Instead
of making a move you can also switch out your Tiles. This will skip 
your turn and cause the computer to play.
