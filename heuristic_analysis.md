# Heuristics Analysis

## Synopsis

The following analysis displays the performance of 3 heuristics applied to the isolation game where each player is
restricted to L-Shaped moves. Cells occupied by a player are blocked and positions. The first player with no legal moves 
loses the game.
 
## Benchmarks
 
To measure the performance of the heuristics the `tournament.py` was ran on a 4GHz Intel Core i7 with 16GB of ram, running macOS Sierra.
 
 
## Heuristics
 
 the 3 following heuristics were explored:
  
  ### weighted_moves: ``((weight_p1 * moves_p1) - (weight_p2 * moves_p2)``
  this heuristic the player is penalized by the number of moves of the opponent making it more aggressive. 
    
  ### weighted_moves_ratio: ``((weight_p1 * moves_p1) / (weight_p2 * p2))``
  This heuristic penalizes a player by the number of opponent moves.   
  
  ### weighted_moves_ratio_adjusted: ``((weight_p1 * moves_p1 * blank_spaces) / (weight_p2 * p2))``
  Similar to ``weighted_moves_ratio`` this heuristic penalizes the player with the opponent moves but changes over time
  considering the number of empty spaces in the board. This heuristic tends to be more aggressive against the opponent at the end of the game when there are less blank spaces. 
      
## Results

The following table shows an average percent of wins for each heuristic after running `tournament.py` 3 times.
  
### ID Improved vs weighted_moves
  
| Heuristic                    | Run 1  | Run 2  | Run 3 |  Mean |
| ----------------------------:|-------:| ------:|------:|------:|
| ID Improved                  |  94.29 | 94.29  | 97.14 | 95.24
| weighted_moves_ratio         |  93.57 | 99.29  | 97.83 | 96.89


### ID Improved vs weighted_moves_ratio
  
| Heuristic                    | Run 1  | Run 2  | Run 3 |  Mean |
| ----------------------------:|-------:| ------:|------:|------:|
| ID Improved                  |  97.86  | 96.43 | 95.71 | 96.67 |
| weighted_moves_ratio         |  98.57  | 96.43 | 96.43 | 97.14 |

### ID Improved vs weighted_moves_ratio_adjusted
  
| Heuristic                    | Run 1  | Run 2  | Run 3 |  Mean |
| ----------------------------:|-------:| ------:|------:|------:|
| ID Improved                  |  93.57 | 94.29    95.71 |  94.52
| weighted_moves_ratio_adjusted|  98.57 | 97.86  | 97.86 |  98.10 


### Conclusion

Although all the heuristics seem to be better than ``ID_Improved``, ``weighted_moves_ratio_adjusted`` has higher winner mean and tends to be more consistent after several executions. Therefore, the recommend heuristic is ``weighted_moves_ratio_adjusted``.

Using the amount of blank spaces ``weighted_moves_ratio_adjusted`` to increase the coefficient of the ratio makes the heuristic behave differently through the game. When the game has more open spaces the heuristic will tend to favor defensive moves from the player 
but starts to gets more aggressive towards the end of the game. 
  