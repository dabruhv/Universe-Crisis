#include <iostream>
#include <ctime>
using namespace std;
//Jesse Madrigal, Fall 2020, Universe Crisis
int skull(int slip);//the odds youll fall off the stairs
int chidori();//the function for the lightning stone needed for the sectret ending
int pray(int phealth);//a function that will heal the player, but it has the chance to kill the player
int ie();//enemies
int rng;
string name = "inventory";
string inventory[7];
int main() {
  string n1;//players name
  bool curse=true;//player needs to make false for normal ending
  bool power=false;//player needs true for secret ending
  bool win = false;//good ending
  int room = 1;
  int health = 100;
  string input;
  srand(time(NULL));
  for (int i = 0;i<7;i++)
      inventory[i]=" ";   
  
  cout << "enter name"<<endl;
  cin>>n1;
  cout<<"you are cursed "<<n1<<endl;
  cout<<"you must repent your sins and go on a quest "<<n1<<endl;
  cout<<"Bring me the relic to free yourself of this curse"<<endl;
  cout<<"If you fail the quest you will be trapped in a corrupt form of your world"<<endl;
  cout<<"However if you can find these items "<<n1<<" you will be granted power and riches beyond imagination"<<endl;
  getchar();
  while(health > 0 && input != "quit" && win == false){ //game loop
    cout<<"you have "<<health<<" health"<<endl;
    cout<<"press 'i' for inventory, press 'f' to pick up items, type 'quit' to quit"<<endl;
    switch(room){
      case 1: //start
       
       inventory[0]="courage";//does nothing but makes it feel more optimistic
        cout<<"you're in the cafeteria that is surprisingly empty with only a few tables. you can go east , west, or north"<<endl;
        getline(cin,input);
        if (input.compare("east")==0)
          room = 3;
        else if(input.compare("west")==0)
          room = 2;
        else if(input.compare("north")==0)
          room = 6;
        else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
       
        break;
      case 2: //weapons
         health -= ie();
          //lament charm needed to stay alive in room 7
        cout<<"you're in the weapons room, the room feels strange, like the room wants to tell you something thats close by but yet so far away. you can go east or south"<<endl;
        getline(cin,input);
        if (input.compare("east")==0)
          room = 1;
        else if(input.compare("south")==0)
          room = 4;
        else if(input.compare("f")==0){
          inventory[1]="lamentCharm";
          cout<<"you found a lament charm"<<endl;
        }
        else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 3: //teleporter B
        health -= ie();
        cout<<"you're in teleporter room B this is where science experiments were performed to allow teleportation to go public and something about this room feels like it has a surge of electricity. you can go west or south"<<endl;
        getline(cin,input);
        if (input.compare("south")==0)
          room = 5;
        else if(input.compare("west")==0)
          room = 1;
        else if(input.compare("use")==0){
          if(inventory[2]=="ElectricalCord"){
            power = true;
            cout<<"The power is on!"<<endl;
            inventory[2]="  ";
          }
          else if(inventory[2]=="  "){
            cout<<"you already turned on the power"<<endl;}
        }
        else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 4: //teleporter A
         
        //inventory[2]="electrical cord";needed for secret ending
        cout<<"you're in teleporter room A it seems like this teleporter is broken and on these ships only two teleporters are allowed so I dont think the creator wants us to teleport in this game. you can go north"<<endl;
        getline(cin,input);
        if(input.compare("north")==0)
          room = 2;
        else if(input.compare("f")==0){
          inventory[2]="ElectricalCord";
          cout<<"you found an electrical cord"<<endl;}
        else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 5: //staff
       
       //inventory[3]="key";unlocks room 7
        cout<<"you're in a room with a staff that seems very important, I dont think its meant to be used against monsters but there seems to be a slot that looks like something is meant to go in there. you can go north or you can pray"<<endl;
        getline(cin,input);
        if (input.compare("north")==0)
          room = 3;
        else if(input.compare("f")==0){
          inventory[3]="key";
          cout<<"you found a key"<<endl;}
        else if(input.compare("pray")==0)
          health=pray(health);
        else if (input.compare("use")==0){
          cout<<"you walk toward the staff and see an engraving that says you need one of two stones, one that has been lost in the darkness, while the other is worshipped."<<endl;
          cout<<"use gem?(yes/no)"<<endl;
          getline(cin,input);
          if (input.compare("yes")==0){
            cout<<"which gem will you use?"<<endl;
            getline(cin,input);
            if (input.compare("vermillion")==0){
              if(inventory[5]!="VermillionGem"){
                cout<<"don't be lazy or you'll never be ballin'"<<endl;}
              else if(inventory[5]=="VermillionGem"){
              cout<<"Your services to the over lords is much appreciated "<<n1<<" its a shame it must end this way, but I have buisness to attend to and souls to consume and sadly my first victim is you!"<<endl;
              room = 11;
              }
            }
            if(input.compare("lightning")==0){
              if(inventory[6]!="lightningStone"){
                cout<<"I have no idea what you're talking about"<<endl;}
              else if(inventory[6]=="lightningStone" &&   power == true){
                cout<<"you've done it! you successfully killed the shadowman. His cycle of destroying your world has finally been brought to an end. You crash land in a zoo, but thankfully no animals and no people are hurt and you are taken to safety"<<endl;
                win = true;
                
              
              }
              else if(power == false)
                health = 0;
            }
          }
          else if (input.compare("no")==0)
            room=5;
        }
        else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
       case 6: //ominous room
       //inventory[4]="vermillion eye";//removes curse mark if sacrificed in room 8
       cout<<"you're in a room with two doors, the right has a rock looking drawing on it and the left door has a drawing of the curse mark thats identical to mine. you can go south,east, west, or if you'd like, you can read the sign"<<endl;
       getline(cin,input);
      if (input.compare("south")==0)
         room = 1;
      else if (input.compare("east")==0)
        room = 9;
      else if (input.compare("west")==0){
        if (inventory[3]=="key" || inventory[3]=="  "){
          cout<<"you used the key"<<endl;
          inventory[3]="  ";
          room = 7;}
        else 
          cout<<"you need a key"<<endl;
      }
      else if(input.compare("read")==0){
        cout<<"for the door on the left you need proof of your pain, for the door on the right those who bear the mark shall be slain"<<endl;
      }
      else if(input.compare("f")==0){
        inventory[4]="VermillionEye";
        cout<<"you found the vermillion eye"<<endl;
      }
      else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
     
      case 7: //evil room
       
       
       health -= ie();
       cout<<"you're in a room that is dark but you can sense the dangers within that room. you can go east or west"<<endl;
       if (inventory[1]!="lamentCharm"){
          cout<<"jk lol you were consumed by evil"<<endl;
          health = 0;}
       getline(cin,input);
      if (input.compare("west")==0)
         room = 8;
      else if(input.compare("east")==0)
          room = 6;
      else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 8: //cursemark room
       chidori();
       cout<<"you're in a room thats dark and has nothing but a glowing curse mark that feels as if it were talking to you. you can go east or read sign"<<endl;
       getline(cin,input);
      if (input.compare("east")==0)
         room = 7;
      else if (input.compare("read")==0)
      cout<<"in order to purify yourself you must sacrifice the visual prowess of someone who can only see the world drenched in blood"<<endl;
      else if(input.compare("use")==0){
        if (inventory[4]=="VermillionEye"){
          curse = false;
          inventory[4]="  ";
          cout<<"you have been purified"<<endl;}
        else 
          cout<<"you have nothing to sacrifice"<<endl;
      }
      else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 9: //stair room
       if(curse == true)
          health = 0;
       cout<<"you're in a room with nothing but stairs but be careful going up...you might fall. you can go west or east"<<endl;
       getline(cin,input);
      if (input.compare("west")==0)
         room = 6;
      else if(input.compare("east")==0)
          room = 10;
      else if(input.compare("i"))
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 10: //holy room
       //inventory[5]="vermillion gem";//triggers normal ending
       cout<<"you're in a room with the feeling of great power that shadow man must have been talking about. you can go west"<<endl;
       health=skull(health);
       getline(cin,input);
      if (input.compare("west")==0)
         room = 9;
      else if (input.compare("f")==0){
        inventory[5]="VermillionGem";
        cout<<"you found the Vermillion Gem"<<endl;
      }
      else if(input.compare("i")==0)
          for(int i = 0;i<8; i++)
            cout<<inventory[i]<<endl;
          cout<<endl<<endl;
        break;
      case 11: //purgatory
      cout<<"you're in a room with nothing but a window to the world you called home being destroyed. All you can hear is the suffering of the people you thought you would save. Maybe its better this way. If everyone has suffered that means that means nobody will bear the curse of hatred, right?"<<endl;
      getline(cin,input);
      if(input.compare("quit")==0)
        cout<<"better luck next time,"<<n1<<endl;
      else {
        cout<<"all good things must come to an end..."<<endl;}//sort of like when you're at the gate of hell in cave adventure, but i think in cave adventure there was probably a way out
      break;
     default:
      cout<<"bruh"<<endl;
    }
  } //end game loop

  if(win == true){
    cout<<"YOU WON!"<<endl;
  
  }
  else if (health<0)
    cout<<"GAME OVER"<<endl;

  cout<<"Thanks for playing!"<<endl;
}//end main


int ie(){//generates random monster that will take away a set amount of health
 int rng = rand() % 100 + 1;
    if(rng < 51){
        cout<<"a fly spawned"<<endl;
        cout<<"you lost 1 health"<<endl;
         return 1;
    }
   else if(rng >= 51 && rng < 71){
     cout<<"a knife shot out"<<endl;
      cout<<"you lost 15 health"<<endl;
        return 15;}
   else if (rng >=71 && rng <95 ){
       cout<<"a zombie spawned"<<endl;
       cout<<"you lost 10 health"<<endl;
       return 10;
       }

    else if (rng >= 95 && rng <= 100){
      cout<<"you have a fire gem shard"<<endl;
      cout<<"you lost 50 health"<<endl;
      return 50; 
      }
      
    else 
      cout<<"you shoudn't see this message";//for debugging
    return 0;
}
int pray(int phealth){
  int approval;
  approval = rand() % 100 + 1;
  if (approval <= 99){
    cout<<"you have pleased the gods"<<endl;
    phealth = 100;
  }
  else if(approval == 100){
    cout<<"you're a disappointment to the gods and shall be punished"<<endl;
    phealth = 0;
  }
  return phealth;

}
int chidori(){//will randomly give lightning stone
  int luck;
  luck = rand() % 1000 + 1;
  if(luck <= 999){
   
    cout<<endl<<endl;}
  else if(luck == 1000){
    inventory[6]="lightningStone";//item needed for secret ending
    cout<<"you got a lightning stone!"<<endl;}
 return luck;
}
int skull(int slip){//will randomly slip off the stairs
  int breakage;
  breakage=rand()% 1000 + 1;
  if (breakage <= 995){
    cout<<"great job you didn't die"<<endl;}
  else if(breakage>=996){
    cout<<"thats what I would have said if you listened to me and were more careful"<<endl;
    slip = 0;
  }
  return slip;

}
