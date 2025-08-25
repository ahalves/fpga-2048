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
