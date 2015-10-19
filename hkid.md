HKID check digit calculation algorithm
The last digit of HK can be calculated with the first 1 or 2 english letters and following 6 numbers.

HK digit pattern
XX999999C / X999999C

XX/X - 1 or 2 English letters
999999 - 6 numeric characters
C - check digit, 0-9 or A

Use the following algorithm to calculate the check digit

1. Convert English letters to number, using the mapping
A->10, B->11, C->12 .... Z->35

2. Calculate the check sum
*For HKID with 2 English letters
check sum = char[1] * 9 + char[2] * 8 + char[2] * 8 + char[3] * 7 + char[4] * 6 + char[5] * 5 + char[6] * 4 + char[7] * 3 + char[8] * 2

*For HKID with only 1 English letters
check sum = 36 * 9 + char[2] * 8 + char[2] * 8 + char[3] * 7 + char[4] * 6 + char[5] * 5 + char[6] * 4 + char[7] * 3 + char[8] * 2

3. mooderate check sum by 11 and use 11 to minus the value

check digit = 11 - checksum mod 11

Below are samples of valid HKID
B123456(6) 
A182361(5) 
CA182361(1) 
AB123456(9)
ZA182361(3)
AZ182361(6)
XZ182361(8)
ZX182361(6)
XX182361(2)