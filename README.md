# Problems occurred:
# 1. Why is there a x-axis scroll bar at the bottom of the screen? Even 'overflow-x-hidden' doesn't work.
   
   When your content gets tall enough to need a Vertical Scrollbar, that scrollbar takes up physical space (usually about 15px-17px wide).
   The Fix:
   Change w-screen to w-full.
   
# 2. Why is the 'trending' card's bottom line (which is 42) not aligned with the 32 cards' bottom line?
  Left Side: You have a Title (<p>) PLUS a Grid set to h-full (100% height).
  Math: Title Height + 100% Parent Height = More than 100%.
  Result: The left cards are actually spilling out past the bottom of the container.
  Right Side: You have a Flex container set to h-full.
  Math: Exactly 100% Parent Height.
  Result: The "Trending" card stops exactly at the bottom of the container.
  The Fix: You need to tell the Left Grid to take "whatever space is left" instead of "100% of the parent."

  The Solution Code:
  Update the Left Column:
  Make the container flex flex-col and the grid flex-1 (grow to fill).
