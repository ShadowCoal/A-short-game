# A-short-game
//just a short game like back in the olden days where the play inputs words into the keyboard and gets an output
//#include <iostream>
//#include <fstream>
//#include <string>
//using namespace std;

void whereToGo (int& answer);
void showWeapon (string hero, int&weapon);
void updateWeapon (int weapon, int& attack, int& mpInt, int& hit);
void showArmor(string hero, int& armor);
void updateArmor (int armor, int& defence);
void status (string hero, int level, int coutnter, int mv, int jm, int hp, int damageHp, int mp, int usedMp, int attack, int defence, int mpInt, int spd, int hit, int res, int exp, int next);
void getAtctionNumber (int& answer);
int main()
{
    string hero;
    int weapon = 0;
    int armor = 0;
    int answer = 0;
    int level = 1;
    int counter = 2;
    int mv = 6;
    int jm = 20;
    int hp = 17;
    int damageHp = 17;
    int mp = 7;
    int usedMp = 7;
    int attack = 11;
    int defence = 8;
    int mpInt = 9;
    int spd = 10;
    int hit = 11;
    int res = 8;
    int exp = 0;
    int next = 15;
    int eHP = 15;
    int eDefence = 10;
    int eAttack = 11;
    int block = 0;

    cout << "Enter hero's name: ";
    cin >> hero;

    whereToGo (answer);

    while (answer <5)
    {
        if (answer == 1)
        {
            if (weapon == 0)
            {
                showWeapon (hero, weapon);
                updateWeapon (weapon, attack, mpInt, hit);
            }
            else
                cout << hero << " cannot get another weapon" << endl;
        }
        else if (answer == 2)
        {
            if (armor == 0)
            {
                showArmor(hero, armor);
                updateArmor(armor, defence);
                cout << hero << " exit armor shop" << endl;
                cout << endl;
            }
            else
                cout << hero << " cannot get another armor" << endl;
        }
        else if (answer == 3)
        {
            cout << "Nobody is home... you head back" << endl;
        }
        else
        {
            status(hero, level, counter, mv, jm, hp, damageHp, mp, usedMp, attack, defence, mpInt, spd, hit, res, exp, next);
        }
        whereToGo (answer);
    }
    answer = 0;
    cout << hero << " enter the forest" << endl;
    cout << hero << " encounter level 1 wild wolf it has 15/15 hp" << endl;

        getAtctionNumber (answer);
        if (answer == 1)
        {
            cout << hero << " attack wild wolf. it deals " << attack - eDefence << "damage" << endl;
            eHP = eHP - (attack - eDefence);
            block = 0;
        }
        else
        {
            cout << hero << " block upcoming attack" << endl;
            block = 5;
        }

    while (eHP > 0)
    {
        if (defence > 11)
            cout << "Wild wolf attacks but no damage is dealt" << endl;
        else if (block > 2)
            cout << "Wild wolf attacks but misses" << endl;
        else
        {
            cout << "Wild Wolf attacks it deals " << eAttack - defence << "damage" << endl;
            damageHp = damageHp - (eAttack - defence);
        }

        if (damageHp > 0)
        {
             getAtctionNumber (answer);
            if (answer == 1)
            {
                cout << hero << " attack wild wolf. it deals " << attack - eDefence << "damage" << endl;
                eHP = eHP - (attack - eDefence);
                block = 0;
            }
            else
            {
                cout << hero << " block upcoming attack" << endl;
                block = 5;
            }}
        else
        {
            cout << hero << " retreat and find a healer" << endl;
            damageHp = hp;
            usedMp = mp;
            cout << hero << " return to the forest" << endl;
            answer = 0;
            cout << hero << " enter the forest" << endl;
            cout << hero << " encounter level 1 wild wolf it has 15/15 hp" << endl;
            eHP = 15;

            getAtctionNumber (answer);
            if (answer == 1)
            {
                cout << hero << " attack wild wolf. it deals " << attack - eDefence << "damage" << endl;
                eHP = eHP - (attack - eDefence);
                block = 0;
            }
            else
            {
                cout << hero << " block upcoming attack" << endl;
                block = 5;
            }
        }
    }
    cout << "Wild wolf runs off. gain 15 exp" << endl;
    cout << "Level up!" << endl;
    exp = 15;
    next = 20;
    hp +=2;
    damageHp = hp;
    mp +=1;
    usedMp = mp;
    attack += 1;
    defence +=1;
    mpInt +=1;
    spd +=1;
    hit+= 1;
    res +=1;
    status;
    status (hero,level,counter,mv,jm,hp,damageHp,mp, usedMp,attack,defence,mpInt,spd,hit,res,exp,next);
    answer = 0;
    cout <<hero << " continue into the forest" << endl;
    cout << endl;
    cout << "You find a box" << endl;
    cout << "Does " << hero << "1- open the box or 2- ignore the box";
    cin >> answer;

    if (answer == 1)
    {
        cout << hero << " finds a potion" << endl;
        cout << "potion heals " << hp - damageHp << " points. " << hero << " continue into the forest." << endl;
        damageHp = hp;
    }
    else
        cout << hero << " ignores the box, and continues into the forest" << endl;

    eHP = 20;
    eAttack = 15;
    eDefence =16;
    cout << hero << " encounters a bear." << endl;
    getAtctionNumber (answer);
        if (answer == 1)
        {
            cout << hero << " attack bear. it deals " << attack - eDefence << "damage" << endl;
            eHP = eHP - (attack - eDefence);
            block = 0;
        }
        else
        {
            cout << hero << " block upcoming attack" << endl;
            block = 5;
        }

    while (eHP > 0)
    {
        if (defence > 11)
            cout << "bear attacks but no damage is dealt" << endl;
        else if (block > 2)
            cout << "bear attacks but misses" << endl;
        else
        {
            cout << "bear attacks it deals " << eAttack - defence << "damage" << endl;
            damageHp = damageHp - (eAttack - defence);
        }

        if (damageHp > 0)
        {
             getAtctionNumber (answer);
            if (answer == 1)
            {
                cout << hero << " attack bear. it deals " << attack - eDefence << "damage" << endl;
                eHP = eHP - (attack - eDefence);
                block = 0;
            }
            else
            {
                cout << hero << " block upcoming attack" << endl;
                block = 5;
            }}
        else
        {
            cout << hero << " retreat and find a healer" << endl;
            damageHp = hp;
            usedMp = mp;
            cout << hero << " return to the forest" << endl;
            answer = 0;
            cout << hero << " enter the forest" << endl;
            cout << hero << " encounter bear it has 20/20 hp" << endl;
            eHP = 20;

            getAtctionNumber (answer);
            if (answer == 1)
            {
                cout << hero << " attack wild wolf. it deals " << attack - eDefence << "damage" << endl;
                eHP = eHP - (attack - eDefence);
                block = 0;
            }
            else
            {
                cout << hero << " block upcoming attack" << endl;
                block = 5;
            }
        }
    }
    cout << "Bear runs off. Gain 25 exp" << endl;
    cout << "Level up!" << endl;
    exp = 15;
    next = 20;
    hp +=2;
    damageHp = hp;
    mp +=1;
    usedMp = mp;
    attack += 1;
    defence +=1;
    mpInt +=1;
    spd +=1;
    hit+= 1;
    res +=1;
    status;
    status (hero,level,counter,mv,jm,hp,damageHp,mp, usedMp,attack,defence,mpInt,spd,hit,res,exp,next);
    cout << endl;
    cout << hero << " continues into the forest" << endl;
    cout << hero << " finds lost item and returns to town..." << endl;
    cout << endl;
    cout << "The End?" << endl;
    return 0;
}
void whereToGo (int& answer)
{
    cout << endl;
    cout << "to enter weapon shop, press 1" << endl;
    cout << "to enter armor shop, press 2" << endl;
    cout << "to enter item shop, press 3" << endl;
    cout << "to display current status, press 4" << endl;
    cout << "to enter the forest,press 5" << endl;
    cout << "enter number: ";
    cin >> answer;
    cout << endl;
}

void showWeapon (string hero, int& weapon)
{
    cout << hero << " enter a weapon shop" << endl;
    cout << "enter 1 to get knuckles: +11 attack, +6 hit" << endl;
    cout << "enter 2 to get sword: +13 attack" << endl;
    cout << "enter 3 to get lance: +9 attack" << endl;
    cout << "enter 4 to get bow: +8 attack" << endl;
    cout << "enter 5 to get gun: +6 hit" << endl;
    cout << "enter 6 to get ax: +18 attack, -3 hit" << endl;
    cout << "enter 7 to get staff: +8 int" << endl;
    cout << "enter any other number to exit" << endl;
    cout << "________________________________"<< endl;
    cout << "Select weapon: ";
    cin >> weapon;
    cout << endl;

}

void updateWeapon (int weapon, int& attack, int& mpInt, int& hit)
{
   if (weapon == 1)
        {
            cout << "attack increase by 11 and hit increase by 6" << endl;
            attack += 11;
            hit += 6;
            cout << "Attack is now: " << attack << " and hit is now: " << hit << endl;
        }
        else if (weapon == 2)
        {
            cout << "attack increased by 13" << endl;
            attack += 13;
            cout << "Attack is now: " << attack << endl;
        }
        else if (weapon == 3)
        {
            cout << "attack increased by 9" << endl;
            attack += 9;
            cout << "Attack is now: " << attack << endl;
        }
        else if (weapon == 4)
        {
            cout << "attack increased by 8" << endl;
            attack += 8;
            cout << "Attack is now: " << attack << endl;
        }
        else if (weapon == 5)
        {
            cout << "hit increased by 6" << endl;
            hit += 6;
            cout << "Hit is now: " << hit << endl;
        }
        else if (weapon == 6)
        {
            cout << "attack increase by 18 but hit decrease by 3" << endl;
            attack += 18;
            hit -= 3;
            cout << "Attack is now: " << attack << " hit is now: " << hit << endl;
        }
        else if (weapon == 7)
        {
            cout << "int increased by 8" << endl;
            mpInt += 8;
            cout << "Int is now: " << mpInt << endl;;
        }
        else
            cout << "got nothing" << endl;
        cout << "Exit weapon shop" << endl;
        cout << endl;
}
void showArmor(string hero, int& armor)
{
    cout <<hero << " enter an armor shop" << endl;
    cout << "enter 1 to get cheep armor: defense + 10" << endl;
    cout << "enter any other number to exit" << endl;
    cout << "________________________________"<< endl;

    cout << "select armor: ";
    cin >> armor;
    cout << endl;
}
void updateArmor (int armor, int& defense)
{
    if (armor == 1)
    {
        cout << "defense increase by 10";
        defense += 10;
        cout << "defense is now: " << defense << endl;
    }
}
void status(string hero, int level, int coutnter, int mv, int jm, int hp, int damageHp, int mp, int usedMp, int attack, int defence, int mpInt, int spd, int hit, int res, int exp, int next)
{
    cout << "Hero's name: " << hero << endl;
    cout << "level " << level << endl;
    cout << "coutnter " << coutnter << endl;
    cout << "Move " << mv << " Jump " << jm << endl;
    cout << "Hp---" << damageHp << "/" << hp << endl;
    cout << "Mp---" << usedMp << "/" << mp << endl;
    cout << "Attack: " << attack << " defence: " << defence << endl;
    cout << "int: " << mpInt << " speed: " << spd << endl;
    cout << "hit: " << hit << "res: " << res << endl;
    cout << "EXP: " << exp << " Next: " << next << endl;
}
void getAtctionNumber (int& answer)
{
    cout << "do you : 1- attack or 2- defend: " << endl;
    cin >> answer;
}

