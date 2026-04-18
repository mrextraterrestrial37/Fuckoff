# war gaME

import time

print("hello and welcome to country conquerer sim ")

name=input(" what is the name you wished called as comander? ")

pro=input("would you like to be called Sir Ma'am or Commander ")
print("ok commander ",name, " you are basically are going to do is build either quarries , farms , houses or attack and each will help you cature the surrounding countries (chad , cameroon, and benin) and when you have done that you will win (the beta version) ")

land=1000
pop=0
mats=0
buildings=0
food=0

beninPOP=25
beninLND=100
beninDSC=0

cameroonPOP=50
cameroonLND=500
cameroonDSC=0

chadPOP=100
chadLND=1000
chadDSC=0

while True:
    
    action=input(" what would you like to do? build a quarry ,a house , attack?  ")
    
    if action == "a quarry" and land>= 0 and pop>=0:
        
        mats+=5
        land-=10
        buildings+=1
        print("you have",mats,"materials",land,"land left ",pop,"residents",buildings,"buildings ")
    
    elif action=="a quarry" and land<=0 and pop>=0:
        
        print(  pro,"we will have to attack now")
    
    elif action =="a quarry" and land<=0 and pop<=0:
        print(pro,"you should build houses to attack and claim land")
    
    elif mats>=1 and action =="a house":
      
        mats-=2
        pop+=4
        land-=5
        buildings+=1
        print("you have ",mats," materials",land,"land left ",pop," residents",buildings,"buildings")
        
    elif mats<=1 and action == "a house":
        print(" Sorry",pro," but you don't have enough materials for that yet try and build some quarries")
        
    elif mats<=1and action=="a farm":
        
        print(pro,"you havent got enough materials for that try building quarries")
    
    while mats>=1 and action == "a farm":
        
        food+=1
        print("you have",food,"food")
        
        time.sleep(0.0000000000000000000000000000000000000000000000000000001)
        
                        
        if food >=50:
            
            break   
    
    if pop >=20 and action=="attack":
        
        attkCountry=input("Ok sir where do you want to attack benin,cameroon,or chad?  ")
        
        if attkCountry=="benin" and beninPOP <= pop and beninDSC>=0 :
        
            print(" you won the war and took benins land good job ",pro)
        land+=beninLND
        pop-=25
        
        print("you have",mats,"materials",land,"land left",pop,"residents ",buildings," buildings")
        
        if attkCountry=="benin" and beninPOP>= pop and beninDSC>=0:
            pop=pop/2
            print(pro,"we need back up our entire army just tanked a hit by",attkCountry,"lets re group back home ")
    
        if attkCountry=="benin"and beninPOP<=pop and beninDSC>=0:
            
            print(pro,"this is our land what are you doing?")
        
        
        if attkCountry=="cameroon" and cameroonPOP<=pop and cameroonDSC>=0:
                
            pop-=50
            land+=cameroonLND
            print("congratulations",pro,"we've just taken over cameroon")
            print("you have",mats," materials",land,"land left",pop,"residents",buildings,"buildings ")
        
        if attkCountry=="cameroon" and cameroonPOP>=pop and cameroonDSC>=0:
            pop=pop/2
            print(pro,"we need back up our entire army just tanked a hit by ",attkCountry,"lets re-group back home ")
            
        if attkCountry=="cameroon" and cameroonPOP<=pop and cameroonDSC>=0:
            
            print(pro,"this is our land what are you doing?")
        
        if attkCountry=="chad" and chadPOP<=pop and chadDSC>=0:
            
            pop-100
            land+=chadLND
            print(pro,"we have just  taken over chad congratulations")
            
        if attkCountry=="chad"and chadPOP>=pop and chadDSC>=0:
            
            pop=pop/2
            print(pro," we need back up our army just tanked a hit by",attkCountry,"lets re-group back home")
            
    elif pop <=20 and action=="attack":
        print(pro,"we must build up our army before we attack ")