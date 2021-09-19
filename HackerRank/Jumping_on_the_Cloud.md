# Prompt
There is a new mobile game that starts with consecutively numbered clouds. Some of the clouds are thunderheads and others are cumulus. The player can jump on any cumulus cloud having a number that is equal to the number of the current cloud plus  or . The player must avoid the thunderheads. Determine the minimum number of jumps it will take to jump from the starting postion to the last cloud. It is always possible to win the game.

For each game, you will get an array of clouds numbered  if they are safe or  if they must be avoided.
# Summary:
- input: an array contain 0 & 1
      + 0: cumulus
      + 1: thuderheads (avoid)
- output: iteger - minimum jumps from start to end of array
- each jump can increase current index 1 or 2

# Approach
 - use a for loop from index = 0
 - check element ===0? -> skip 1 jump to that index
 - increase counting

# Solution
## Solution1:
 ```js
 function findMinJump(clouds){
   let count =0;
   for(let i=0; i<clouds.length-1; i++){
     if(clouds[i]===0){
       i++
     }
     count++
   }
   return count

 }
 ```
