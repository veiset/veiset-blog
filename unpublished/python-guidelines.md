verdier = [5,3,99,10]
for verdi in verdier:
    print(verdi)

liste = [5,3,99,10]
for i in range(len(liste)):
    print(liste[i])


# Hva som skal kommenteres, hvordan.
def metode(argument):
    ''' Metode something something argument something '''

def metode(argument):
    '''
    En lengre kommentar, som trenger flere linjer
    med tekst. Forklar litt om hva som helst. Gjør
    følgende ting. Og returnerer denne verdien.
    '''

def circleAreal(r):
    print(3.1415*r**2)

def circleAreal(r):
    pi = 3.1415
    print(pi*r**2)


if condition == True:
if condition:

if condition != True:
if not condition:


if value > second_value and value != third_value and second_value > third_value:
    print("Something here!")
    ...

if (value > second_value and
    value != third_value and
    second_value > third_value):
    print("Something here!")
    ...



#Clarity is key. Større kode-eksempel
if person == "student" and person == "awesome":
    if age > 70:
        print("Something")


def isStudent(person): return (person == "student")
def isAwesome(person): return (person == "awesome")
def isOld(age): return (age>70)

if isStudent(person) and isAwesome(student):
    if isOld(age):
        print("Something")
...
if isStudent(person): print("Welcome")


# Parentheses are not always needed:
if ((a>5) and (b>10)):
    print("hello")

if a>5 and b>10:
    print("hello")


