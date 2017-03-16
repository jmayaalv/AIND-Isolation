# Heuristics Analysis

## Synopsis

 The following analysis displays the performance of 3 heuristics applied to the isolation taking `ID_IMPROVED` as a baseline.
 The implementation of alphabeta includes a order   

## Heuristics

### heuristic_weighted_moves
     Calculates the weighted difference between players legal moves.  
     Described by the formula:  `w1 * p1_moves - w2 * p2_moves. To select the best performant values for w1 and w2 I have run the tournament with different values. 
     Here different AI techniques could help to make the process smoother.   
     
### heuristic_weighted_moves_ratio
     Calculates the weighted ratio of the difference between players legal moves. It uses the same weights found on `heuristic_weighted_moves` but instead of finding the difference it calculates the ratio.
      It follows the formula: w1 * p1_moves / w2 * p2_moves

### heuristic_weighted_moves_ratio_adjusted
     Similar to the `heuristic_moves_ratio` but it gets adjusted with the amount of positions left in the game. 
     Described by the formula: ()
  