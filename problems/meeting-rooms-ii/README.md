<!--|This file generated by command(leetcode description); DO NOT EDIT.    |-->
<!--+----------------------------------------------------------------------+-->
<!--|@author    Openset <openset.wang@gmail.com>                           |-->
<!--|@link      https://github.com/openset                                 |-->
<!--|@home      https://github.com/openset/leetcode                        |-->
<!--+----------------------------------------------------------------------+-->

[< Previous](https://github.com/openset/leetcode/tree/master/problems/meeting-rooms "Meeting Rooms")
　　　　　　　　　　　　　　　　
[Next >](https://github.com/openset/leetcode/tree/master/problems/factor-combinations "Factor Combinations")

## 253. Meeting Rooms II (Medium)



### Related Topics
  [[Heap](https://github.com/openset/leetcode/tree/master/tag/heap/README.md)]
  [[Greedy](https://github.com/openset/leetcode/tree/master/tag/greedy/README.md)]
  [[Sort](https://github.com/openset/leetcode/tree/master/tag/sort/README.md)]

### Similar Questions
  1. [Merge Intervals](https://github.com/openset/leetcode/tree/master/problems/merge-intervals) (Medium)
  1. [Meeting Rooms](https://github.com/openset/leetcode/tree/master/problems/meeting-rooms) (Easy)
  1. [Minimum Number of Arrows to Burst Balloons](https://github.com/openset/leetcode/tree/master/problems/minimum-number-of-arrows-to-burst-balloons) (Medium)

### Hints
<details>
<summary>Hint 1</summary>
Think about how we would approach this problem in a very simplistic way. We will allocate rooms to meetings that occur earlier in the day v/s the ones that occur later on, right?
</details>
<details>
<summary>Hint 2</summary>
If you've figured out that we have to <b>sort</b> the meetings by their start time, the next thing to think about is how do we do the allocation? <br>There are two scenarios possible here for any meeting. Either there is no meeting room available and a new one has to be allocated, or a meeting room has freed up and this meeting can take place there.
</details>
<details>
<summary>Hint 3</summary>
An important thing to note is that we don't really care <b>which</b> room gets freed up while allocating a room for the current meeting. As long as a room is free, our job is done. <br><br>We already know the rooms we have allocated till now and we also know when are they due to get free because of the end times of the meetings going on in those rooms. We can simply check the room which is due to get vacated the earliest amongst all the allocated rooms.
</details>
<details>
<summary>Hint 4</summary>
Following up on the previous hint, we can make use of a min-heap to store the end times of the meetings in various rooms. <br><br>So, every time we want to check if any room is free or not, simply check the topmost element of the min heap as that would be the room that would get free the earliest out of all the other rooms currently occupied.

<br><br>If the room we extracted from the top of the min heap isn't free, then no other room is. So, we can save time here and simply allocate a new room.
</details>
