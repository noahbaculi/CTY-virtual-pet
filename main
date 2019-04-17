'''

Noah Baculi (noahbaculi.com) and Masayuki  Fujita (https://www.facebook.com/profile.php?id=100004246866478)
July 2014
Johns Hopkins Center for Talented Youth Program at Seattle University


The user inputs name
Pet introduces himself
Things need to be done:
Feeding
Petting
First feeding, petting, etc.

Code to access files:
*Make a new .txt file for each data type
READ FILES:
dataRead = open(pathPetDataFolder+"FILE NAME","r")
aVariableName = dataRead.read()
dataRead.close()
WRITE ON FILES:
dataWrite = open(pathPetDataFolder+"FILE NAME","w")
dataWrite.write("ANYTHING YOU WANT TO WRITE ON THE FILE")
dataWrite.close()
'''
########################################
#LOAD STUFF#############################
########################################
from __future__ import print_function
from tkinter import *
import tkinter
from time import sleep
import random
import getpass

#Font: Courier New
#Project: Virtual Pet

#Show Picture Function
def showPicture(pictureNumber):
        window.geometry("120x120")
        mainCanvas.delete("all")
        mainCanvas.create_image(60,60, image=photoVirtualPet[pictureNumber])
        mainCanvas.update()

def showBigPicture(pictureNumber):
        window.geometry("500x500")
        mainCanvas.delete("all")
        mainCanvas.create_image(250,250, image=photoAdventureBackground[pictureNumber])
        mainCanvas.update

#Get username
userName = getpass.getuser()

#Create Path
pathPetDataFolder = "/Users/nbaculi/Documents/SSHS records/2014-2015- Sophomore/CTY~The Fundamentals Of Computer Science (June-July, 2014)/(7-14-14--7-17-14)~Masayuki and Noah Final Project Virtual Pet/(7-14-14--7-17-14)~Masayuki and Noah Final Project Virtual Pet Images" 

#Create Window and Canvas
window = Tk()
mainCanvas = Canvas(window, width = 500, height = 500, bg = 'white')
mainCanvas.grid(row = 0, column = 0)

#Load pictures of the dog
#PICTURE DATA
#0:Angry 1:Upset 2:Crying 3:Eating 4:Thinking 5:Lovesick 6:Happy(normal) 7:Scared 8:Happy(Big eyes) 9:Unsure 10:Angry 11:Crying 12:Sleeping 13:Tired
photoVirtualPet = []
for i in range (0, 14):
        photoVirtualPet.append(PhotoImage(file = pathPetDataFolder + "Pictures/virtualPet" + str(i) + ".gif"))
#Adventure
photoAdventureBackground = []
for i in range (0, 6):
        photoAdventureBackground.append(PhotoImage(file = pathPetDataFolder + "Pictures/WithBackground/adventure" + str(i) + ".gif"))
#Determines if it already has a name:
newName = False
dataRead = open(pathPetDataFolder + "virtualPetName.txt","r")
if "NameInputState:Done" in dataRead.read():
        dataRead.close() 
        dataRead = open(pathPetDataFolder + "virtualPetName.txt","r")
        petNameInputArray = dataRead.read().split()
        petNameInput = petNameInputArray[0]
        dataRead.close()
else:
        dataRead.close()
        showPicture(6)
        petNameInput=raw_input("What would you like to name your pet?: ")
        dataWrite = open(pathPetDataFolder + "virtualPetName.txt","w")
        dataWrite.write(petNameInput + "\nNameInputState:Done")
        dataWrite.close()
        newName = True
#Load pointNumber
dataRead = open(pathPetDataFolder+"virtualPetPointnumber.txt","r")
pointNumber = int(dataRead.read())
dataRead.close()

#Load feedSkipCount
dataRead = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","r")
feedSkipCount = int(dataRead.read())
dataRead.close()

#Load sleepSkipCount
dataRead = open(pathPetDataFolder+"virtualPetSleepskipcount.txt","r")
sleepSkipCount = int(dataRead.read())
dataRead.close()


#variables:
twoOptionNumber1=random.randint(0,1)
twoOptionNumber2=random.randint(0,1)

########################################
#ACTUAL CODE############################
########################################
if newName:
    print(petNameInput,": Hi!")
    showPicture(6)
else:
    temporaryRandomNumber = random.randint(0,1)
    if temporaryRandomNumber == 0:
        print(petNameInput,"says: Hi!")
        showPicture(6)
    elif temporaryRandomNumber == 1:
        print("... ", end = "")
        showPicture(12)
        sleep(1)
        print("... ", end = "")
        sleep(1)
        print("...", end = "")
        print("\n",end="")
        showPicture(1)
        sleep(0.2)
        showPicture(6)
        print(petNameInput,": \"Oh, hey!\"\n")
        sleepSkipCount = 0
        dataWrite = open(pathPetDataFolder+"virtualPetSleepskipcount","w")
        dataWrite.write(str(sleepSkipCount))
        dataWrite.close()
        
sleep(1)
#HUBInitiationSequence
while True:
        feedSkipCount=feedSkipCount+1
        dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
        dataWrite.write(str(feedSkipCount))
        dataWrite.close()
        sleepSkipCount=sleepSkipCount+1
        dataWrite = open(pathPetDataFolder+"virtualPetSleepskipcount.txt","w")
        dataWrite.write(str(sleepSkipCount))
        dataWrite.close()
        if feedSkipCount>5:
            showPicture(2)
            twoOptionFeedInput2=str(raw_input(petNameInput+" is close to starving! Are you sure you don't want to feed her?(Feed or Not): "))
            while True:
                if twoOptionFeedInput2.lower()=="feed":
                        showPicture(3)
                        print(petNameInput,"is chewing.")
                        for i in range(0,5):
                                print("... ",end="")
                                sleep(.75)
                        print("...")
                        showPicture(6)
                        print(petNameInput+": Yum!\n")
                        feedSkipCount=0
                        dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
                        dataWrite.write(str(feedSkipCount))
                        dataWrite.close()
                        break
                if twoOptionFeedInput2.lower()=="not":
                        showPicture(3)
                        print(petNameInput,"stole some food! Oh well...\n")
                        feedSkipCount=0
                        dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
                        dataWrite.write(str(feedSkipCount))
                        dataWrite.close()
                        break
                else:
                    print("Input not understood. Try again.\n")
        if sleepSkipCount>5:
            showPicture(13)
            twoOptionFeedInput2=str(raw_input(petNameInput+" is too sleepy! Are you sure you don't want to let her sleep?(Sleep or Not): "))
            while True:
                if twoOptionFeedInput2.lower()=="sleep":
                    print(petNameInput,"is napping.")
                    for i in range(0,5):
                        print("... ",end="")
                        sleep(.75)
                    print("...")
                    showPicture(6)
                    print(petNameInput+": Yay! All rested!\n")
                    sleepSkipCount=0
                    dataWrite = open(pathPetDataFolder+"virtualPetSleepskipcount.txt","w")
                    dataWrite.write(str(sleepSkipCount))
                    dataWrite.close()
                    break
                if twoOptionFeedInput2.lower()=="not":
                    showPicture(12)
                    print(petNameInput,"fainted! Oh well...\n")
                    for i in range(0,10):
                        print("... ",end="")
                        sleep(.85)
                    print("\n",end="")
                    sleepSkipCount=0
                    dataWrite = open(pathPetDataFolder+"virtualPetSleepskipcount.txt","w")
                    dataWrite.write(str(sleepSkipCount))
                    dataWrite.close()
                    break
                else:
                    print("Input not understood. Try again.\n")
            
#HUB
        showPicture(6)
        userActionInput=str(raw_input("HUB: You and Amy have "+str(pointNumber)+" points. What would you like to do?(Feed, Pet, Sleep, Adventure, Stop): "))
        sleep(.5)
#feed
        if userActionInput.lower()=="feed":
            feedSkipCount=0
            dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
            dataWrite.write(str(feedSkipCount))
            dataWrite.close()
            print(petNameInput,"is chewing.")
            showPicture(3)
            for i in range(0,2):
                        print("... ",end="")
                        sleep(.75)
            print("...")
            print(petNameInput+": Yum!")
            sleep(.5)
            showPicture(6)
#pet
        if userActionInput.lower()=="pet":
            print(petNameInput,"is panting.")
            showPicture(8)
            for i in range(0,2):
                        print("... ",end="")
                        sleep(.75)
            print("...")
            print(petNameInput,"barked!")
            sleep(.5)
            showPicture(6)
#sleep
        if userActionInput.lower()=="sleep":
            sleepSkipCount=0
            print("Oh, good.",petNameInput,"is already yawning.")
            showPicture(1)
            sleep(0.2)
            showPicture(12)
            for i in range(0,2):
                        print("... ",end="")
                        sleep(.75)
            print("...")
            showPicture(1)
            sleep(0.2)
            showPicture(6)
            print(petNameInput,"is awake! Great!",petNameInput,"is well-rested now.")
            showPicture(6)
#stop
        if userActionInput.lower()=="stop":
                sleep(.5)
                break
        print("\n", end = "")
        if userActionInput.lower()=="adventure":
                userAdventureInput=str(raw_input("Do you and "+petNameInput+" want to go on adventure 1, 2, or 3?(1, 2, 3, or quit): "))
                while True:
                        if userAdventureInput.lower()=="quit":
                            print("\n",end="")
                            break
#ADVENTURE1
                        if userAdventureInput=="1":
                            sleep(1)
                            adventureLocation1=str(raw_input("\nWhere do you and "+petNameInput+" want to venture?(Mountain or Forest?): "))
                            adventureLocation1=adventureLocation1.lower()
                            print("Starting the journey to the mistic",adventureLocation1,"for adventure #1!")
                            sleep(1)
                            for i in range(12,0,-1):
                                print((i*10),"miles to go!")
                                sleep(.93)
                            sleep(.95)
                            if adventureLocation1 == "mountain":
                                    showBigPicture(0)
                            if adventureLocation1 == "forest":
                                    showBigPicture(1)
                            print("Here!")
                            print(petNameInput,"started running off into the grass! Go after her!(Press enter)",end="")
                            raw_input()
                            print("...")
                            sleep(.95)
                            print("*rustle rustle*")
                            showPicture(7)
                            sleep(.65)
                            print("Uh oh, what was that noise?")
                            sleep(.65)
                            print("*rustle rustle*")
                            print("\n",end="")
                            sleep(.85)
                            if twoOptionNumber1==0:
                                if twoOptionNumber2==0:
                                    showPicture(7)
                                    print("Oh no! It's a wild Bulbasaur!")
                                    sleep(.85)
                                    print("To defeat the Bulbasar you need to guess the number that it is thinking of in it's mind. Ready?(Press enter)",end="")
                                    raw_input()
                                    showPicture(9)
                                    print("Bulbasar: \"Try to guess my number, it is between 0 and 20\"\n")
                                    sleep(1)
                                    guessCount=0
                                    num=random.randint(1,19)
                                    while True:
                                            guess=int(raw_input("Enter yours and "+petNameInput+"'s guess: "))
                                            guessCount=guessCount+1
                                            if (num-guess)>0:
                                                    print("Bulbasar: \"My number is higher\"")
                                            if (num-guess)<0:
                                                    print("Bulbasar: \"My number is lower\"")
                                            if (num-guess)==0:
                                                    print("Congradulations! You guessed right!",num,"was indeed the Bulbasar's number.")
                                                    showPicture(6)
                                                    print("It only took you",guessCount,"number of times.")
                                                    sleep(1)
                                                    print("\n",end="")
                                                    print("The wild Bulbasar was captured.")
                                                    break
                                            print("\n",end="")
                                if twoOptionNumber2==1:
                                    print("Oh no! It's a wild liger!")
                                    showPicture(7)
                                    sleep(.85)
                                    print("To defeat the liger you need to guess the number that it is thinking of in it's mind. Ready?(Press enter)",end="")
                                    raw_input()
                                    showPicture(9)
                                    print("Liger: \"Try to guess my number, it is between 0 and 20\"\n")
                                    sleep(1)
                                    guessCount=0
                                    num=random.randint(1,19)
                                    while True:
                                            guess=int(raw_input("Enter yours and "+petNameInput+"'s guess: "))
                                            guessCount=guessCount+1
                                            if (num-guess)>0:
                                                    print("Liger: \"My number is higher\"")
                                            if (num-guess)<0:
                                                    print("Liger: \"My number is lower\"")
                                            if (num-guess)==0:
                                                    print("Congradulations! You guessed right!',num,'was indeed the Liger's number.")
                                                    print("It only took you",guessCount,"number of times.")
                                                    showPicture(6)
                                                    sleep(1)
                                                    print("\n",end="")
                                                    print("The wild liger was captured.")
                                                    break
                                            print("\n")
                            else:
                                showPicture(6)
                                print("Awe, it's okay, it's just a bunny.",petNameInput,"likes bunnies!")
                            print("\n",end="")
                            while True:
                                    twoOptionFeedInput1=str(raw_input(petNameInput+" is hungry, do you want to feed her?(Yes or No): "))
                                    if twoOptionFeedInput1.lower()=="yes":
                                            showPicture(3)
                                            print(petNameInput,"is chewing.")
                                            for i in range(0,2):
                                                    print("... ",end="")
                                                    sleep(.75)
                                            print("...")
                                            print(petNameInput+": Yum!")
                                            break
                                    elif twoOptionFeedInput1.lower()=="no":
                                            sleep(.5)
                                            showPicture(1)
                                            print("Okay, just don't push "+petNameInput+" too hard...")
                                            feedSkipCount=feedSkipCount+1
                                            dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
                                            dataWrite.write(str(feedSkipCount))
                                            dataWrite.close()    
                                            break
                                    else:
                                            print("Input not understood. Try again.")
                                            showPicture(9)
                            sleep(2)
                            print("\n",end="")
                            print("Looks like",petNameInput,"is tired, better start heading back.(Press enter)",end="")
                            showPicture(13)
                            raw_input()
                            showPicture(6)
                            for i in range(12,0,-1):
                                print((i*10),"miles to go!")
                                sleep(.9)
                            print("\n",end="")
                            print(petNameInput,"is tired, and is going to rest for the night.")
                            showPicture(1)
                            sleep(0.2)
                            showPicture(12)
                            for i in range(0,5):
                                    sleep(.95)
                                    print("... ",end="")
                            print("\n")
                            showPicture(1)
                            sleep(0.2)
                            showPicture(6)
                            print("Yay!",petNameInput,"is rested and ready for a new day!")
                            while True:
                                    twoOptionFeedInput1=str(raw_input(petNameInput+" is hungry again, should she be fed?(Yes or No): "))
                                    if twoOptionFeedInput1.lower()=="yes":
                                            showPicture(3)
                                            print(petNameInput,"is chewing.")
                                            for i in range(0,2):
                                                    print("... ",end="")
                                                    sleep(.75)
                                            print("...")
                                            print(petNameInput+": Yum!")
                                            feedSkipCount=0
                                            dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
                                            dataWrite.write(str(feedSkipCount))
                                            dataWrite.close()
                                            break
                                    if twoOptionFeedInput1.lower()=="no":
                                            showPicture(10)
                                            print("Okay, just don't push "+petNameInput+" too hard...")
                                            feedSkipCount=feedSkipCount+1
                                            dataWrite = open(pathPetDataFolder+"virtualPetFeedskipcount.txt","w")
                                            dataWrite.write(str(feedSkipCount))
                                            dataWrite.close()
                                            break
                                    else:
                                            print("Input not understood. Try again.")
                            print("")
                            sleep(1.5)
                            pointNumber=pointNumber+100
                            dataWrite = open(pathPetDataFolder+"virtualPetPointnumber.txt","w")
                            dataWrite.write(str(pointNumber))
                            dataWrite.close()
                            showPicture(6)
                            break
#ADVENTURE2
                        if userAdventureInput=="2":
                            sleep(1)
                            while True:
                                    adventureLocation2=str(raw_input("Do you and "+petNameInput+" want to travel to the vast volcano or to the beseeching beach?(Volcano or Beach): "))
                                    if adventureLocation2.lower()=="volcano":
                                            adventureLocation2=0
                                            adventureLocationName2="vast volcano"
                                            print("Ooh, the "+adventureLocationName2+", good choice.")
                                            showPicture(9)
                                            break
                                    if adventureLocation2.lower()=="beach":
                                            adventureLocation2=1
                                            adventureLocationName2="beseeching beach"
                                            print("Ooh, the "+adventureLocationName2+", good choice.")
                                            showPicture(9)
                                            break
                                    else:
                                            print("Input not understood.")
                                            showPicture(9)
                            sleep(1)
                            #showPicture(6)
                            print("Starting the journey to the "+adventureLocationName2+" for adventure #2!")
#volcano
                            if adventureLocation2==0:
                                    for i in range(14,0,-1):
                                            print((i*10),"miles to go!")
                                            sleep(.85)
                                    showBigPicture(2)
                                    print("Here!")
                                    print("You have arrived just outside the volcano.(Press enter)",end="")
                                    raw_input()
                                    print("To get the majestic gem you need to get inside the volcano!(Press enter)",end="")
                                    raw_input()
                                    showPicture(9)
                                    print(petNameInput+": \"Oh look, a bridge!\"")
                                    sleep(2)
                                    print("Walk over to the bridge!(Press enter)",end="")
                                    raw_input()
                                    for i in range(0,4):
                                        print("... ",end="")
                                        sleep(.85)
                                    print("\n",end="")
                                    showPicture(2)
                                    print(petNameInput+": \"Uh oh, the bridge has a gaurdian!\"(Press enter)",end="")
                                    raw_input()
                                    print("Gaurdian: \"You! Stop!\"(Press enter)",end="")
                                    raw_input()
                                    showPicture(7)
                                    print(petNameInput+": \"How can we pass into the volcano?\"")
                                    sleep(1.5)
                                    print("Gaurdian: \"Well then we'll have to make an exchange. What do you know about computer science?\"(Press enter)",end="")
                                    raw_input()
                                    showPicture(6)
                                    print(petNameInput+": \"We know a little bit, why?\"(Press enter)",end="")
                                    raw_input()
                                    print("Gaurdian: \"Well, I have a CS quiz coming up soon, and I need a little help.\"")
                                    showPicture(4)
                                    sleep(0.2)
                                    showPicture(6)
                                    sleep(1.5)
                                    print(petNameInput+": \"Sure! What's your question?\"(Press enter)",end="")
                                    raw_input()
                                    trivia1NumberIncorrectCount=0
                                    while True:
                                            showPicture(7)
                                            triviaInput1=str(raw_input("Gaurdian: \"What is the main component in every computer? Is it A.memory, B.CPU, C.graphics, or D.cookies?\"(A, B, C, or D): "))
                                            if triviaInput1.lower()=="a":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            showPicture(11)
                                                            home=1
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            if triviaInput1.lower()=="b":
                                                    print("Gaurdian: \"Oh yeah! That makes sense. Thank you, you may pass.")
                                                    home=0
                                                    showPicture(6)
                                                    break
                                            if triviaInput1.lower()=="c":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    sleep(1)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            home=1
                                                            showPicture(10)
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            if triviaInput1.lower()=="d":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            home=1
                                                            showPicture(10)
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            else:
                                                    print("Gaurdain: \"I don't understand, try again.\"")
                                                    showPicture(7)
                                            print("\n",end="")
                                    if home==0:
                                            print(petNameInput+": \"Yay!\"")
                                            showPicture(6)
                                            print("Go onto the bridge")
                                            for i in range(0,3):
                                                    print("... ",end="")
                                                    sleep(.5)
                                            print("\n",end="")
                                            print(petNameInput+": \"Look, the gem!\"")
                                            showPicture(6)
                                            print("Go get the gem!")
                                            print(petNameInput+": \"Got the gem!\"(Press enter)",end="")
                                            raw_input()
                                            pointNumber=pointNumber+250
                                            print("Time to go!(Press enter)",end="")
                                            raw_input()
                                            for i in range(14,0,-1):
                                                    print((i*10),"miles to go!")
                                                    sleep(.85)
                                            print(petNameInput+": \"Back home!\"")
                                            showPicture(6)
                                    if home==1:
                                            showPicture(2)
                                            for i in range(14,0,-1):
                                                    print((i*10),"miles to go!")
                                                    sleep(.85)
                                            print(petNameInput+": \"Back home!\"")
                                            showPicture(6)
#beach
                            if adventureLocation2==1:
                                    for i in range(14,0,-1):
                                            print((i*10),"miles to go!")
                                            sleep(.85)
                                    showBigPicture(3)
                                    print("Here!")
                                    print("You have arrived on the beach.(Press enter)",end="")
                                    raw_input()
                                    print("To get the majestic gem you need to get onto the pier!(Press enter)",end="")
                                    raw_input()
                                    showPicture(9)
                                    print(petNameInput+": \"Oh look, a boadwalk!\"")
                                    sleep(2)
                                    print("Walk over to the boardwalk!(Press enter)",end="")
                                    raw_input()
                                    for i in range(0,4):
                                        print("... ",end="")
                                        sleep(.85)
                                    showPicture(2)
                                    print("\n",end="")
                                    print(petNameInput+": \"Uh oh, the boardwalk has a gaurdian!\"(Press enter)",end="")
                                    raw_input()
                                    print("Gaurdian: \"You! Stop!\"(Press enter)",end="")
                                    raw_input()
                                    showPicture(7)
                                    print(petNameInput+": \"How can we pass onto the pier?\"")
                                    sleep(1.5)
                                    print("Gaurdian: \"Well then we'll have to make an exchange. What do you know about computer science?\"(Press enter)",end="")
                                    raw_input()
                                    showPicture(6)
                                    print(petNameInput+": \"We know a little bit, why?\"(Press enter)",end="")
                                    raw_input()
                                    print("Gaurdian: \"Well, I have a CS quiz coming up soon, and I need a little help.\"")
                                    showPicture(4)
                                    sleep(0.2)
                                    showPicture(6)
                                    sleep(1.5)
                                    print(petNameInput+": \"Sure! What's your question?\"(Press enter)",end="")
                                    raw_input()
                                    trivia1NumberIncorrectCount=0
                                    while True:
                                            triviaInput1=str(raw_input("Gaurdian: \"What is the main component in every computer? Is it A.memory, B.CPU, C.graphics, or D.cookies?\"(A, B, C, or D): "))
                                            showPicture(4)
                                            if triviaInput1.lower()=="a":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            home=1
                                                            showPicture(10)
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            if triviaInput1.lower()=="b":
                                                    print("Gaurdian: \"Oh yeah! That makes sense. Thank you, you may pass.")
                                                    home=0
                                                    showPicture(8)
                                                    break
                                            if triviaInput1.lower()=="c":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            home=1
                                                            showPicture(10)
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            if triviaInput1.lower()=="d":
                                                    print("Gaurdian: \"I don't think that is right,",end="")
                                                    showPicture(7)
                                                    trivia1NumberIncorrectCount=trivia1NumberIncorrectCount+1
                                                    if trivia1NumberIncorrectCount>2:
                                                            print("you are out of guesses, go away\"")
                                                            home=1
                                                            showPicture(10)
                                                            break
                                                    if trivia1NumberIncorrectCount<3:
                                                            print("you have",(3-trivia1NumberIncorrectCount),"guesses left.\"")
                                                            showPicture(6)
                                            else:
                                                    print("Gaurdain: \"I don't understand, try again.\"")
                                                    showPicture(7)
                                            print("\n",end="")
                                    if home==0:
                                            print(petNameInput+": \"Yay!\"")
                                            showPicture(6)
                                            print("Go onto the bridge")
                                            for i in range(0,3):
                                                    print("... ",end="")
                                                    sleep(.5)
                                            print("\n",end="")
                                            print(petNameInput+": \"Look, the gem!\"")
                                            showPicture(6)
                                            print("Go get the gem!")
                                            print(petNameInput+": \"Got the gem!\"(Press enter)",end="")
                                            pointNumber=pointNumber+250
                                            raw_input(end="")
                                            print("Time to go!(Press enter)",end="")
                                            raw_input()
                                            for i in range(14,0,-1):
                                                    print((i*10),"miles to go!")
                                                    sleep(.85)
                                            print(petNameInput+": \"Back home!\"")
                                            showPicture(6)
                                    if home==1:
                                            showPicture(2)
                                            for i in range(14,0,-1):
                                                    print((i*10),"miles to go!")
                                                    sleep(.85)
                                            print(petNameInput+": \"Back home!\"")
                                            showPicture(6)
                            sleep(1.5)
                            print("\n",end="")
                            break     
#ADVENTURE3
                        if userAdventureInput=="3":
                            sleep(1)
                            codeNumberAdventure3=random.randint(0,80)
                            sleep(.5)
                            while True:
                                    adventureLocation3=str(raw_input("Do you and "+petNameInput+" want to travel to the desert canyon or to the jeopardous jungle?(Canyon or Jungle) "))
                                    if adventureLocation3.lower()=="canyon":
                                            print("Ooh, the desert canyon, wow.")
                                            break
                                    if adventureLocation3.lower()=="jungle":
                                            print("Ooh, the jeopardous junlge, wow.")
                                            break
                                    else:
                                            print("Input not understood.")
                            sleep(2)
                            print("Starting the journey to "+adventureLocation3.lower()+" for adventure #3.")
                            for i in range(50,1,-1):
                                print((i*10),"miles left!")
                                sleep(.145)
                            sleep(1)
                            if adventureLocation3.lower()=="canyon":
                                print("Arrrived at the canyon!(Press enter)",end="")
                                showBigPicture(4)
                                raw_input()
                                showPicture(1)
                                print(petNameInput+": \"We have to climb down this canyon wall to get to the gem.\"(Press enter)",end="")
                                raw_input()
                                showPicture(0)
                                for i in range(0,8):
                                    print("... ",end="")
                                    sleep(.5)
                                print("\n",end="")
                                showPicture(6)
                                print("In the canyon.(Press enter)",end="")
                                raw_input()
                                print(petNameInput+": \"Look, there's a safe, I bet the gem is inside!\"")
                                sleep(2)
                                print("To into the safe, you need to guess its code.(Press enter)",end="")
                                raw_input()
                                guessCountAdventure3=0
                                showPicture(4)
                                while True:
                                            guessNumberAdventure3=int(raw_input("The dial goes from 0 to 80. Enter the guess that you and Amy want to try: "))
                                            guessCountAdventure3=guessCountAdventure3+1
                                            if (codeNumberAdventure3-guessNumberAdventure3)>0:
                                                    print("The number is higher")
                                            if (codeNumberAdventure3-guessNumberAdventure3)<0:
                                                    print("The number is lower")
                                            if (codeNumberAdventure3-guessNumberAdventure3)==0:
                                                    print("Congratulations! You guessed right!",codeNumberAdventure3,"was indeed the secret code to the safe.")
                                                    showPicture(6)
                                                    print("It only took you",guessCountAdventure3,"number of times. Lucky for you and Amy, it was fast enough.")
                                                    sleep(2)
                                                    print("\n",end="")
                                                    print("You retrieved the gem!")
                                                    showPicture(5)
                                                    break
                                            print("\n",end="")
                                            sleep(2)
                            if adventureLocation3.lower()=="jungle":
                                print("Arrrived at the jungle!(Press enter)",end="")
                                showBigPicture(5)
                                raw_input()
                                showPicture(1)
                                print(petNameInput+": \"We have to walk down this jungle path to get to the gem.\"")
                                sleep(2)
                                showPicture(0)
                                for i in range(0,8):
                                    print("... ",end="")
                                    sleep(.5)
                                print("\n",end="")
                                showPicture(6)
                                print("In the jungle.(Press enter)",end="")
                                raw_input()
                                print(petNameInput+": \"Look, there's a safe, I bet the gem is inside!\"")
                                sleep(2)
                                print("To into the safe, you need to guess its code.(Press enter)",end="")
                                raw_input()
                                guessCountAdventure3=0
                                showPicture(4)
                                while True:
                                            guessNumberAdventure3=int(raw_input("The dial goes from 0 to 80. Enter the guess that you and Amy want to try: "))
                                            guessCountAdventure3=guessCountAdventure3+1
                                            if (codeNumberAdventure3-guessNumberAdventure3)>0:
                                                    print("The number is higher")
                                            if (codeNumberAdventure3-guessNumberAdventure3)<0:
                                                    print("The number is lower")
                                            if (codeNumberAdventure3-guessNumberAdventure3)==0:
                                                    print("Congratulations! You guessed right!",codeNumberAdventure3,"was indeed the secret code to the safe.")
                                                    showPicture(6)
                                                    print("It only took you",guessCountAdventure3,"number of times. Lucky for you and Amy, it was fast enough.")
                                                    sleep(2)
                                                    print("\n",end="")
                                                    print("You retrieved the gem!")
                                                    break
                                            print("\n",end="")
                            print("Going home.")
                            print("Starting the journey to "+adventureLocation3.lower()+" for adventure #3.")
                            for i in range(50,1,-1):
                                print((i*10),"miles left!")
                                sleep(.145)
                            sleep(1.5)
                            pointNumber=pointNumber+500
                            dataWrite = open(pathPetDataFolder+"virtualPetPointnumber.txt","w")
                            dataWrite.write(str(pointNumber))
                            dataWrite.close()
                            showPicture(6)
                            print("\n",end="")
                            break
