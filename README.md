C-Card-Game
===========
//
//  main.cpp
//  Chapter 4 c++
//
//  Created by zhangshiyu on 11/11/14.
//  Copyright (c) 2014 ZSY. All rights reserved.


#include <iostream>
using namespace std;
const int clubs=0;
const int diamonds=1;
const int hearts=2;
const int spades=3;
const int jack=11;
const int queen=12;
const int king=13;
const int ace=14;


struct card
{
    int number;
    int suit;
};


int main(int argc, const char * argv[]) {
    card temp,chosen,prize;   //define cards
    int position;
    
    card card1={7,clubs};   //initialize card1
    cout<<"Card 1 is the 7 of clubs\n";
    
    card card2={jack,hearts};
    cout<<"Card 2 is the jack of hearts\n";
    
    card card3={ace,spades};
    cout<<"Card 3 is the spades of ace\n";
    
    prize=card3;     //copy this card, to remember it
    
    cout<<"I'm swapping card 1 and card 3\n";
    temp=card3;card3=card1;card1=temp;
    
    cout<<"I'm swapping card 2 and card 3\n";
    temp=card3;card3=card2;card2=temp;
    
    cout<<"I'm swapping card 1 and card 2\n";
    temp=card2;card2=card1;card1=temp;
    
    cout<<"Now,where(1,2, or3) is the ace of spades?";
    cin>>position;
    
    switch (position) {
        case 1:chosen=card1;
            break;
        case 2:chosen=card2;
            break;
        case 3:chosen=card3;
            break;
            
        
    }
    
    
    if(chosen.number==prize.number&&chosen.suit==prize.suit)
        cout<<"That's right!You win!\n";
    else
        cout<<"Sorry.You lose.\n";
    return 0;
}
