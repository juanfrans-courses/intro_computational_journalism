# Fundamentals of Programming

## Recap
* How did the exercises go? Any findings, trouble, workflow?
* OpenRefine
* Tabula

## Why Programming
* Computers have become part of our everyday life
* They regulate and shape our interactions with the physical and virtual worlds.
* Sensing is cheap and plentiful, and easily deployed.
* Our actions generate vast quantities of digital data.
* New ways of asking questions about the world
* Asking these questions goes through data, code and algorithms
* Computation, Python and Jupyter Notebooks in journalism:
  * [Buzzfeed Github repository](https://github.com/BuzzFeedNews/everything#data-and-analyses)
  * [Buzzfeed - Shoot someone in a major US city, and odds are you'll get away with it](https://www.buzzfeednews.com/article/sarahryley/police-unsolved-shootings?bftw=&utm_term=4ldqpfp#4ldqpfp)
  * [Brian Keegan - The need for openness in journalism](https://nbviewer.jupyter.org/github/brianckeegan/Bechdel/blob/master/Bechdel_test.ipynb)
  * [Nature - Why Jupyter is data scientists' computational notebook of choice](https://www.nature.com/articles/d41586-018-07196-1)
  * [The Economist - Peeling back the curtain](https://medium.economist.com/peeling-back-the-curtain-487bd3be0c47)

## Why Python
* Readability and code sharing (advantages)
* Python in its "Notebook" *framework* (there are many ways of using Python)
* Computation as a tool for finding and telling stories
* Reporting on and reporting with computation
* Every piece of digital technology embeds within it a model of the world ==> some things are easy and others are hard. It forces our world into specific boundaries and constraints

Python is a programming language created by Guido van Rossum. van Rossum began work on Python in the late 1980s and version 1.0 was released in 1994. Python now has a considerable development community. Python is "a high-level general-purpose programming language that can be applied to many different classes of problems."

Those problems include string manipulation -- looking at the words or sentences in a document, say. Python is conversant in network protocols which means you can use it to access web sites and services -- this will help with web scraping or pulling data from Twitter. There are add-ons contributed by the community that let you make wonderful maps and data visualizations, perform analysis on tabular data (but not in a wonky Excel fashion), and access data stored in a variety of different databases.

In the late 1990s van Rossum wrote a proposal entitled "Computer Programming for Everybody". To give you a sense of van Rossum as a designer of technology, consider this passage.

"In the dark ages, only those with power or great wealth (and selected experts) possessed reading and writing skills or the ability to acquire them. It can be argued that literacy of the general population (while still not 100%), together with the invention of printing technology, has been one of the most emancipatory forces of modern history.

"We have only recently entered the information age, and it is expected that computer and communication technology will soon replace printing as the dominant form of information distribution technology. About half of all US households already own at least one personal computer, and this number is still growing.

"However, while many people nowadays use a computer, few of them are computer programmers. Non-programmers aren't really "empowered" in how they can use their computer: they are confined to using applications in ways that "programmers" have determined for them. One doesn't need to be a visionary to see the limitations here."

Later he envisions a world with millions or even billions of computer programmers at various levels of proficiency. His is a world where people are not trained by expert-created platforms, but instead have sufficient facility with computation to help shape the software systems around them.

## Introduction to Jupyter Notebooks
* Code a bit, have a look, code more, come up with ideas, share.
* Jupyter comes from the original core languages that the notebook supported -- Julia, Python and R. New langauges are being created all the time, often tailored to particular kinds of problems. Python is a bit of a generalist, while R is great for statistical computations.
* Open jupyter notebook and explain how it works (double click on a cell and shift-enter to make it run)
* Markdown (pre-language for creating HTML) ==> explain syntax
* Code

## Simple variables and functions
* Math operation `5+3`
* Variables: `p = 5`, `3+p`
* Objects ==> `5` is an object, you can do things to it (can be added, subtracted, concatenated) and has some properties (larger than 4)
* We can also create our own objects
* Python is an **object-oriented language**
* `type()` allows you to get the type of any object
* `type(5)`
* Run through types of other variables (eg. `4/3 + 2.2`)
* There are some basic types and then with the help of other libraries other more custom types
* `p = 'is this going to be any good?`
* `p + ' I hope so.`
* quotations can be single, double, triple, as long as they match at the beginning and end
* Objects have "functions" or particular operations and attributes. To access them, you use the `.`.
* For example:
* `p = 'hello world!'`
* `p.upper()`
* **Print** allows you to "print" a specific variable or result of an operation.
* `print(p.upper())`
* `print(p.lower())`
* `print(p.count("i"))`
* `print(p.replace("t","g"))`
* the `help` function allows you to see what operations or attributes exist to that particular object:
  * `help(type(p))`
* How to import libraries (and sub-libraries)
* You can also render other types of code in your Notebook (R, HTML, UNIX):
```
%%HTML
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Greatest Witch Hunt in the History of our Country! NO COLLUSION! Border Coyotes, Drug Dealers and Human Traffickers are treated better. Who alerted CNN to be there?</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/1088832908494888961?ref_src=twsrc%5Etfw">January 25, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
```

### Exercise 1 - Trump's Tweets
* Load 2019
```
tweetfile = open("trump_2019.txt")
tweets = tweetfile.read()
tweets
```
* Special characters `\n`
* Difference between that and `print`
* Tell us something about Trump's 2019 tweets
* Load 2018 and compare the two through code
* Do something new by checking the Python 3 online documentation

## Simple variables and functions continued
* Floating point errors
* `0.2 + 0.1`

### Booleans:
  * `3>5`
  * `10.0 < 100.0`
  * `"i" in "Juan Saldarriaga"`
  * `"z" in "Donald Trump"`
  * Comparisons vs memberships
  * Booleans help code "branch" depending on whether some condition is true or false
  * We can create more complex tests with `and` `or` `and not`
  * `print("e" in "Jon Levine" and 3 < 5)`
  * `print("z" in "Jon Levine" and 3 < 5)`
  * `print(not "u" in "Donald Trump")`
  * `print(6 > 5 or (2 > 5 and "u" in "Trump"))`

### Exercise 2 - Booleans
* Play around and make sure you understand

### Operators
Technically, all of these symbols (">", "<", "in", "and", "or" and "not") are examples of operators in Python. The simplest kind of operators are arithmetic.
```
print(3+10)
print(100*5)
print(3*(100+2.5))
```
Sometimes operators behave weirdly:
```
print(5*"Tweets ")
print("#LearnToCode"+" tweets")
```
More information about operators can be found [here](http://www.tutorialspoint.com/python/python_basic_operators.htm)

* Other examples:
```
tweet = "#code #100daysofCode #learntocode working on #FreeCodeCamp final challenges for fun"
isg = "g" in tweet
print(tweet)
print("Is 'g' in this post?", isg)
```
```
x = 4.3
y = 100.2
print("Adding x and y to get", x+y)
```
```
w = 5
x = "Trump\t"
y = "Multiplication with strings:\n"
print(y+x*w)
```
* Special characters:
  * `\n`, `\t`
  * `\` is an escape character
  * `print("He said, \"I cannot believe we are looking at Trump's tweets\"")`
  * Unicode:
    * `print("\U0001f63b")`
    * `print("\U0001f601", "\U0000270c", "\U0001f370", "\U0001f423")`
* Dynamic typing: you can reassign variables, it can change type!
```
x = 3
y = x
print("Here x and y are both pointing to the value 3:", x, y)
y = 5
print("But now y points to the value 5, and x is unchanged:", x, y)
```

### Lists
* *Ordered* collection of objects
```
counts = [474,540,679,970,6279,8412,7448,9209,37595,20250]
print("The type of 'counts' is", type(counts), "and its length is", len(counts))
```
* `len()` function
* `len('Juan Francisco Saldarriaga')`
```
print(counts)
counts.append(2767)
print(counts)
```
```
counts.sort()
print(counts)
```
* Very common operations are sorting and retrieving objects
* The first item in a list is in position `0`
```
djt = [
    "Mon Jan 28 18:50:14 +0000 2019",
    "Could someone explain to me why if I tell my kids to 'learn to code' it’s likely sound parenting, but if I told a journalist the same it’s grounds for a @twitter suspension?",
    "1089958848742518785",
    7565,
    31098,
    False,
    "Twitter for iPhone"
]
        
print(djt, "\n")

print("The list has", len(djt), "elements", "\n")

# the first element in the list has index 0
print("The first element:", djt[0], "\n")

# and the fourth has index 3
print("The fourth element:", djt[3], "\n")

# and the last has index -1 -- the negative indices count from the right!
print("The last element:", djt[-1], "\n")
print("The third from the last:", djt[-3], "\n")

# Finally, you can pull more than one element with the : symbol to create a 'slice'
print("From the fourth element to the end:", djt[3:], "\n")
print("Up to but not including the third element:", djt[:2], "\n")
print("From the third up to but not including the fifth element:", djt[2:5], "\n")
```
* You can retrieve objects from a list, you can add (append), you can remove [(del, remove, pop)](https://stackoverflow.com/questions/11520492/difference-between-del-remove-and-pop-on-lists), and you can change values:
```
djt[0] = 6000
print(djt, "\n")

djt[1:4] = [1,10,100]
print(djt)
```
* Certain operations produce lists:
* `split()`
```
line = "Could someone explain to me why if I tell my kids to 'learn to code' it’s likely sound parenting, but if I told a journalist the same it’s grounds for a @twitter suspension?"

# divide into substrings using the space character " " as a breakpoint -- this gives a rough division into words.
rough_words = line.split(" ")
print(rough_words,"\n")

print("There are roughly", len(rough_words), "words in this tweet.")
```
* `print(line.split("e"))`
* 
### Exercise 3 - Lists
Create a list and play with it, remove, add, split, make sure you understand

### List of lists
```
times = [
    ["2019-01-30",2767],
    ["2019-01-29",20250],
    ["2019-01-28",37595],
    ["2019-01-27",9209],
    ["2019-01-26",7448],
    ["2019-01-25",8412],
    ["2019-01-24",6279],
    ["2019-01-23",970],
    ["2019-01-22",679],
    ["2019-01-21",540],
    ["2019-01-20",474]
  ]

print(type(times))
print(len(times))
```
* Remember this for Pandas dataframe
* How do you interact with this one?

### Dictionaries
```
djt = [
    "Mon Jan 28 18:50:14 +0000 2019",
    "Could someone explain to me why if I tell my kids to 'learn to code' it’s likely sound parenting, but if I told a journalist the same it’s grounds for a @twitter suspension?",
    "1089958848742518785",
    7565,
    31098,
    False,
    "Twitter for iPhone"
]
  
djt
```
* They have *keys* instead of *order* ==> we search by word
```
djt = {
     "created_at":"Mon Jan 28 18:50:14 +0000 2019",
     "full_text":"Could someone explain to me why if I tell my kids to 'learn to code' it’s likely sound parenting, but if I told a journalist the same it’s grounds for a @twitter suspension?",
     "id":"1089958848742518785",
     "retweet_count":7565,
     "favorite_count":31098,
     "retweet":False,
     "source":"Twitter for iPhone"
}
```
* What keys does the dictionary contain: `djt.keys()`
* And extract data based on a key: `djt["source"]`
* Explain what a JSON file is ([JavaScript Object Notation](https://www.json.org/))
* Load DTJ tweets:
```
tweetstring = open("djt.json").read()
print(type(tweetstring),"\n")
print(tweetstring)
```
* Import library to deal with JSON objects
```
from json import dumps,loads

tweet = loads(tweetstring)
print(type(tweet))
```
* Twitter [description](https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object) of their JSON.
* `tweet.keys()`
* `tweet["full_text"]`
* `tweet["created_at"]` in UTC
* `tweet["truncated"]`

### Exercise 4 - Exploring dictionaries
* Find something in his tweets
* Find some information about DTJ in his user information from the tweets

## Loops and conditionals
### Conditionals
```
x = "How much snow is outside your window?"

if "snow" in x:
    x = x.replace("snow","ice")
    x = x.upper()
    print(x)
```
* Recal:
```
x = "How much snow is outside your window?"
"snow" in x
```
* Else:
```
x = "How much snow is outside your window?"
if "snow" in x:
    x = x.replace("snow","ice")
    x = x.upper()
    print(x)
else:
    print("This is a lousy tweet about #snowday!")
```
* Nested:
```
x = 300
if x > 25:
    print(x,"is a big number.")
    if x>100:
        print("Actually, it's a really big number")
else:
    print("small number")
```
* Elif:
```
x = 7
if x > 100:
    print("really big")
elif x > 25:
    print("big")
else:
    print("small")
```

### Loops
* `type(range(10))`
```
# from 0 up to but not including 10
list(range(10))
```
```
# from 5 up to but not including 20
list(range(5,20))
```
```
# from 100 up to but not including 2000 in steps of 200
list(range(100,2000,200))
```
```
for i in range(10):
    print(i)
```
* Modulo (%) operator, returns the remainder of the division
```
print(3%2)
print(20%2)
```
```
print(30%5)
print(24%5)
```
```
for i in range(1,11):
    if i % 2 == 0:
        print(i,"is an even number")     
    else:
        print(i, "is an odd number")
```
* Iterate over a list:
```
students = ["Yaling","Sophia","Alex","Erin","Ellen","Isabelle","Ethan"]
for student in students: 
    drill = student + " is learning about code blocks."
    print(drill)
    print("---")
```
```
students = ["Yaling","Sophia","Alex","Erin","Ellen","Isabelle","Ethan"]
for student in students:
    drill = student + " is learning about code blocks."
    if len(student) % 2 == 0:
        drill = drill + " Their name has an even number of letters."
    else:
        drill = drill + " Their name has an odd number of letters."
    print(drill)
    print("---")
print("And that's it!")
```
* While loop will continue executing until a given condition is met
```
from random import sample
# 3 draws from the collection 0,...,9
print(sample(range(10),3))
# 2 draws from our list of students
print(sample(students,2))
```
```
# 1 randomly selected student name
student = sample(students,1)
print(student)
# 1 randomly selected student name, but a string
print(student[0])
```
* coin flip example: `sample(["H","T"],1)[0]`
```
flip = sample(["H","T"],1)[0]
print(flip)
count = 1

while flip == "T":
    flip = sample(["H","T"],1)[0]
    print(flip)
    count = count + 1
    
print("--->", count, "flip(s)")
```

## Functions
* Basically a block of code that we want to use repeatedly
* *Indentation*
* Basic function:
```
def addtwo(x):
    "This function adds two to a number."
    return(x+2)

addtwo(3)
```
* `help(addtwo)`
```
y = addtwo(5)
y*10+3
```
* Use the `.format()` and `{0}{1}` to format
```
ef judgey(name,ID):
    
    "This function evaluates your twitter ID"

    if ID < 20000:
        return("Wow {0}, you are an early adopter!".format(name))
    elif ID < 20000000:
        return("OK {0}, you are sorta hip".format(name))
    else:
        return("Meh {0}.".format(name))
```
```
greeting = "Hello"
mood = "!"
"{0} class{1}".format(greeting,mood)
```
* Assign a default value in a function:
```
def judgey(name,ID,greeting="Hey"):
    
    "This function evaluates your twitter ID"

    if ID < 20000:
        return("{0} {1}, you are an early adopter!".format(greeting,name))
    elif ID < 20000000:
        return("{0} {1}, you are sorta hip".format(greeting,name))
    else:
        return("{0} {1}.".format(greeting,name))
```
* A chat bot function
```
def stately():
    
    name = ""
    # a friendly welcome
    print("Hello. What is your name?")
    
    name = input("> ")
    print("Hello "+name+". How are you today?")
 
    mood = input("> ")
    print("Glad to hear you are "+mood+".") 
    
    print("Goodbye "+name+".")
```

### Handling errors
* `try` `catch` statements

## Objects
* Objects have properties and methods (functions)
* They belong to a class, this is how you define them, by creating the class and describing the class' methods and properties
```
class Car:
    def __init__(self, make, color, year):
        self.make = make
        self.color = color
        self.year = year

car1 = Car("Mazda", "black", 2008)
print(car1.make)
print(car1.year)
```
```
class Car:
    def __init__(self, make, color, year, milage):
        self.make = make
        self.color = color
        self.year = year
        self.milage = milage
    def updateMilage(milage):
        self.milage = milage
        print("The ", self.color, self.make, "milage has now been updated to", self.milage)
car1 = Car("Mazda", "black", 2008, 1000)
car1.updateMilage(2000)
```

## Exercise 5 - Tip calculator
Create a tip calculator

## Notes to self
* Install [Git for Windows](https://gitforwindows.org/)