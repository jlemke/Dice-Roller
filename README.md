# Dice-Roller
Web service that receives a string consisting of instructions for a dice roll (e.g. "2d6+4")


# Design


2 d 6 + 4

1 d 10 + 5

d 10 + d 6

d is always followed by a number

+-*/ is never last or first

needs to match this pattern
"^(\d*d)?\d+([\+\-\*\/](\d*d)?\d+)*$"

d20+5

20+d4+1d2+5*d20
	replace d4 with random()*4
	replace 1d2 with 1 * random()*2
	replace d20 with random()*20
20+2+1+5*13
	replace 5*13 with 65
20+2+1+65
	add everything together



separate by +-*/d
order of operations
d\d
*
/
+
-

possibly need to make function recursive

public int roll(String instructions) {
	//first check that it works as instructions
	Pattern r = Pattern.compile("^(\d*d)?\d+([\+\-\*\/](\d*d)?\d+)*$");
	Matcher m = r.matcher(instructions);
	
	//if pattern is ok do this
	if (m.find()) {
		
	} else {
		//there was an error
	}
}

#Maybe do these
* an overloaded function where you can send it round down or up
* be able to use () like "d20*(d20+2)"