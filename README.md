# Autumn2018
Exploratory work done in Autumn2018

## Session 1

## Session 2

### Unplugged

Take a pen on a piece of paper. Someone holds the pen. Someone else indicates direction.
Set of instructions: Pen Down / Pen Up / Forward / Turn left xx degrees / Turn right xx degrees
Somone instructs how to draw a square

### In Code

```
import turtle as t

t.pendown()
t.forward(20)
t.left(90)
t.forward(20)
t.left(90)
t.forward(20)
t.left(90)
t.forward(20)
t.left(90)
```

## Looping round

Rather than say: forward, right, forward, right etc. you could just say. "Go forward and turn right and do that 4 times"

### In Code

```
for n_side in range(4):
    t.forward(20)
    t.left(90)
```

### Comments:

`for XX in range(<NN>):` just means: do something NN times and each time give the number NN to the name XX. Everything underneath that you want repeated is pulled right (usually by 4 spaces)

## Giving it a name

Once your friend knew how to draw a square, you could just say to him "draw a square" instead of "go forward and turn right and do it 4 times"

### Code

```
def square():
    for n_side in range(4):
        t.forward(20)
        t.left(90)

square()

t.penup()
t.forward(200)
t.pendown()
square()
```

## Diversifying

Now that we know how to draw a square and to package it up so we can draw more than one square, let's try another shape: a triangle.

Same of sort of idea: go forward and turn, but different turning angle.

### Unplugged

Same again, but with different people. You need to turn by the external angle of the triangle

### Code

```
def triangle():
    for n_side in range(3):
        t.forward(20)
        t.left(120)
    
triangle()
```

## Even more diverse

Now that we have the basic approach, we can put together the code for a pentagon and a hexagon

### Code

```
def pentagon():
    for n_side in range(5):
        t.forward(20)
        t.left(72)

def hexagon():
    for n_side in range(6):
        t.forward(20)
        t.left(60)

pentagon()

t.penup()
t.forward(200)
t.pendown()
hexagon()
```

## Abstraction

Abstraction is the art of seeing the pattern and doing something which works just as well for all kinds of shapes, not just the ones we've built so far. It's like putting things into a function but going a step further and letting that function work for all. Let's take a look at the code we've got:

```
def triangle():
    for n_side in range(3):
        t.forward(20)
        t.left(120)

def square():
    for n_side in range(4):
        t.forward(20)
        t.left(90)

def pentagon():
    for n_side in range(5):
        t.forward(20)
        t.left(72)

def hexagon():
    for n_side in range(6):
        t.forward(20)
        t.left(60)

```

Look at the commonality. In each case we've got very much the same code, with only two things changing: the number of sides -- range(x) -- and the angle of movements -- t.left(x). What if we were to write just one function which you could tell to draw as many sides as you wanted and it *worked out* the angle of turn.

### Code

```
def polygon(n_sides):
    for n_side in range(n_sides):
        t.forward(20)
        t.left(360.0 / n_sides)
```

## Explore

Go further:

* Change the function so you can choose a different length of side
* Try doing it on a tilt (hint: t.setheading)
* Can you do half a polygon
* Create a function called "house" which combines a square and a triangle to form a house
* Challenge: use the turtle to draw your initials

