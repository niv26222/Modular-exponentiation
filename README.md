# Modular exponentiation (Recursive)
Given three numbers a, b and c, we need to find (ab) % c

Now why do “% c” after exponentiation, because ab will be really large even for relatively small values of a, b and that is a problem because the data type of the language that we try to code the problem, will most probably not let us store such a large number.


Examples:


Input : a = 2312 b = 3434 c = 6789
Output : 6343

Input : a = -3 b = 5 c = 89 
Output : 24


The idea is based on below properties.

Property 1:
(m * n) % p has a very interesting property:
(m * n) % p =((m % p) * (n % p)) % p

Property 2:
if b is even:
(a ^ b) % c = ((a ^ b/2) * (a ^ b/2))%c ? this suggests divide and conquer
if b is odd:
(a ^ b) % c = (a * (a ^( b-1))%c

Property 3:
If we have to return the mod of a negative number x whose absolute value is less than y:
then (x + y) % y will do the trick

Note:
Also as the product of (a ^ b/2) * (a ^ b/2) and a * (a ^( b-1) may cause overflow, hence we must be careful about those scenarios
