# Evaluation-assignment

1. Logic Building Task 
Research Facility Security Algorithm 
There is a secure research facility with limited access to top 
tier researchers only. You can only enter into it without tripping 
any alarms. Somehow, you've learned that the checkpoints are about 
to come under automated review, which means that you can trick the 
automated review system.
To trick the system, you'll need to write a program to return the 
same security checksum that the guards would have after they would 
have checked all the researchers through. Fortunately, research 
facility desire for efficiency won't allow for hours-long lines, 
so the checkpoint guards have found ways to quicken the passthrough rate. Instead of checking each and every researcher coming 
through, the guards instead go over everyone in line while noting 
their security IDs, then allow the line to fill back up. Once 
they've done that they go over the line again, this time leaving 
off the last researcher. They continue doing this, leaving off one 
more worker from the line each time but recording the security IDs 
of those they do check, until they skip the entire line, at which 
point they XOR the IDs of all the researchers they noted into a 
checksum and then take off for lunch. Fortunately, the 
researchers' orderly nature causes them to always line up in 
numerical order without any gaps.
For example, if the first researcher in line has ID 0 and the 
security checkpoint line holds three researchers, the process 
would look like this:
0 1 2 /
3 4 / 5
6 / 7 8
where the guards' XOR (^) checksum is 0^1^2^3^4^6 == 2.
Likewise, if the first researcher has ID 17 and the checkpoint 
holds four researchers, the process would look like:
17 18 19 20 /
21 22 23 / 24
25 26 / 27 28
29 / 30 31 32
which produces the checksum 17^18^19^20^21^22^23^25^26^29 == 14.
All researchers IDs (including the first researcher) are between 0 
and 2000000000 inclusive, and the checkpoint line will always be 
at least 1 researcher long.
With this information, write a function solution(start, length) 
that will cover for the missing security checkpoint by outputting 
the same checksum the guards would normally submit before lunch. 
You have just enough time to find out the ID of the first 
researcher to be checked (start) and the length of the line 
(length) before the automatic review occurs, so your program must 
generate the proper checksum with just those two values.
Example 1
Input: solution(0, 3)
Output: 2
Example 2
Input: solution(17, 4)
Output: 14
