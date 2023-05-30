# baby-c
so you know python, it sucks so I made it better by giving it a few c features (typing and more defined scopes and macros mainly)


***
```
@
import math
@

/ to obtain the hypotenuse /
def pythag(int a, int b) ret int <=
	int c = a * a;
	int d = b * b;
	return math.sqrt(c + d);
=>
```
/..//transpiled to//../
```
TYPE_ERROR = -1
#Other error codes here
import math

def pythag(a, b):
	c = a*a
	b = b*b
	_ret_ = math.sqrt(c + d)
	if not isinstance(_ret_, int):
		print("TYPE_ERROR function 'pythag' returns " + int + ", instead got " + type(_ret_))
		exit(TYPE_ERROR)
	return math.sqrt(c + d)
```
/ It is important to note the set of @@ in the non transpiled code, this is where macros and pre code definitions go. For example, /

/..//pythag macro//../
```
@
import math
(pythag a b) = ( math.sqrt(a*a + b*b) -> int )
@

int main() ret none <=
	@ test @ print("PYTHAG MACRO DEMONSTRATION");
	int a = input("a: ") -> int;
	int b = input("b: ") -> int;
	int c = (pythag a b);
	print("C = " + c);
=>
```

/ the @ test @ before the print means that unles -test is ran on transpilation it will not be in the final product. /

/..//transpiled to//../
```
import math

def main():
	a = int(input("a: "))
	b = int(input("b: "))
	c = int(math.sqrt(a*a + b*b))
	print("C = " + c)

if __name__ == "__main__":
	main()
```
/ another thing to note is that most the type checking is done at compile time (other than returns) /

/..//for loops//../
```
/ for loops will be transpiled into while loops when possible i.e /

def main() ret none <=
	for(int k iterate 10) <=
		print("Hi!");
	=>
=>
```
/transpiled to:/
```
def main():
	k = 0
	while k < 10:
		print("Hi!")
		k += 1

if __name__ == "__main__":
	main()
```



