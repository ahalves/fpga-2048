## Log

### Hour 1
**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 1:45 PM - 2:45 PM 

**Description:**

Managed to wrap my head around how the VGA output works... hence we have colors which will be used for each 2048 block.

<img width="728" height="512" alt="Screenshot_20250825_141343" src="https://github.com/user-attachments/assets/30823aaf-a04e-4cc4-83e6-f5f9748e7cec" />

Then moved on to adding a 4x4 game grid with coloring logic based on block value.

<img width="731" height="507" alt="image" src="https://github.com/user-attachments/assets/d6981c05-1df8-4949-ad61-432a7767abba" />

Block value is/will be represented by a number from 0-11, corresponding to the powers of 2 (2^11 = 2048).

---

### Hour 2
**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 3:19 PM - 4:19 PM 

**Description:**

Added border outlines and a default starting position. Added button edge detection logic so that gamepad button down isn't detected every single clock cycle.

<img width="648" height="464" alt="image" src="https://github.com/user-attachments/assets/d905228c-a179-4c2b-80f5-3887393c699b" />


---

### Hour 3

**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 4:19 PM - 5:19 PM 

**Description:**

Working on figuring out and implementing tile movement and merging logic...

Mainly thinking and tinkering around with code here to make sure it actually does what I want it to do: no functional change to previous log :(
```
Check if player pressed button on gamepad.

For each row/column (depending on button) in the grid:
- Make a temporary copy of it
- Reset a "merged" marker for each tile

Process the tiles from top to bottom:
- If a tile isn't empty, move it upward as far as possible until it hits another tile or the top
- If it hits a tile of the same value and neither has merged yet, combine them into one tile with the next value and mark it as merged to prevent further merging in that move

Update the original row/column in the grid with the new positions of the tiles
```
---

### Hour 4

**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 5:19 PM - 6:29 PM 

**Description:**

Fixed a stupid typo with edge triggering buttons... (i can't copy and paste lol)

Finally figured out sliding and merging! (only up so far)

demo of 2 clicks of up showing intended behaviour below:

![Screencast_20250825_183250](https://github.com/user-attachments/assets/147ab493-82fe-460f-b373-328dfa3a6af1)

Next up: do the same for down, left, and right.

---

### Hour 5

**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 6:39 PM - 7:39 PM 

**Description:**

Took way me too long to make it work but it works now! Up, down, left, and right shifts are functional.

![ezgif-7f8672576f71b6](https://github.com/user-attachments/assets/8eebeaac-f37e-4eee-b6b5-8e8d76b12532)

Now it's time to add random 2 and 4 tile addition...

---

### Hour 5

**Date:** 8/25/2025 (mm/dd/yyyy)

**Time range:** 7:57 PM -  PM 

**Description:**

Tile spawning is almost there... I used an 8 bit LFSR to choose from the empty squares on each move and select either a 2 or a 4 tile to spawn there. 

![Screencast_20250825_204502](https://github.com/user-attachments/assets/3108895f-2f33-4b41-8135-33bb07a9e508)

Now I need to compare the grid state after the move to before the move, to check if anything changed, i.e. if it was a valid move...

