# main module

import french_translator
import menu

def main():
    menu.display_menu()
    print()
    selection=input('Please enter your choice[number only]:')

    
    while selection.isdigit()==False or int(selection)>2:
        print('Invalid data,please reread the instruction')
        selection=input('Please enter your choice again[number only]:')

    if int(selection)==1:
        
        print('These are the words and phrases you can translate in French')
        print()
        phrase=['','1.Good moring','2.Goodbye',
                '3.Thankyou','4.Girl','5.Boy','6.Please',
                '7.Good evening','8.Good night','9.Excuse me','10.You’re welcome']
        for i in range(0,len(phrase)):
            print(phrase[i])
        print()
        

        number=input('Select your choice[number only]:')
        while number.isdigit()==False or int(number)>10: 
            print('Invalid data,please reread the instruction')
            number=input('Please enter your choice again[number only]:')
        if number.isdigit()==True:
            print(phrase[int(number)])
            print('The phrase after translate is:',french_translator.translate(number))


            flag=input('Do you wish to continue?[y-continue/press any key to exit]:')
            if flag.lower()=='y':
                main()
            else:
                print('You have exit the program')
                
    else:
        print('You have successfully exit the program')
    
    
main() 



# first module
def display_menu():
    print('This program is a simple language translator')
    print()
    print('\t Menu')
    print('1. Translate English to France')
    print('2. Exit the program')

# second module
def translate(number):

    word={'1':'Bonjour','2':'Au revoir','3':'Merci','4':'Fille','5':'Garçon',
          '6':'S’il vous plaît','7':'Bonsoir','8':'Bonne Nuit',
          '9':'Excusez-moi','10':'Je vous en prie'}
    a=word[number]
    return a

    


