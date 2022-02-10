Background

Connect Four is a classic board game where players take turns trying
 to create a line of four of their own pieces without being blocked by their
 opponent. The game ends when one of the two players successfully lines up four of
 their pieces horizontally, vertically, or diagonally and wins, or in a draw if
 the 7-column, 6-row grid is filled without either player successfully connecting
 four pieces.

----------------------------------------------------------------------------------

player '.rand()' turn start
until player 'human'  blocks player '.rand()'
  swap turns between: 'human', '.rand()'
end

block: when '.rand()' || 'human' has seq-3-tkns
  swap turns between: 'human', '.rand()'
    then '.rand()' makes seq || p1 makes p2-tkn on 'top/left': seq-3-p1-tkns

endgame: when p1 || p2 seq-4 tokens
  with: seq-4 tokens (define): 'vert', 'horz' 'diag'

    isequiv?: 'win' => true
  
  draw: when all slots full && no-seq-4 tokens

  slots: 7-cols x 6-rows
  
endgame isequiv 'win' || 'draw'

-----------------------------------------------------------------------------------

Iteration One

connect_four.rb: equiv play p1 turn start

  1. chomp in p1 FIRST input (allow only A ||... B,..G) (return repeated annoying
 instruction if ~(A-G)
    a. drop token
  2. ruby rando select A-G
    b. drop token

  do the above until FIRST seq-3 p1 || p2 condition reached


Iteration Two

Iteration Three

Iteration Four
