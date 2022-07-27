/*This program simulates the login system of applications. It registers new users, and if the user 
is already registered it looks for their username and password in files.
Created by: Hiva Hakimzadeh
Date: 07/26/2022
*/
#include <iostream>
#include <string>
#include <fstream>
#include<cstdlib>
using namespace std;

//asks if the user is a member or not function 
bool menu()
{
    char choice='\0';
    bool create;
    cout<<"Please press a if you already have an account and b if you need to register: ";
    cin>>choice;
    switch (choice)
    {
        case 'a':
           create= true;//already have an accout so the user should be a member
           break;
        case 'b':
            create=false;
            break;
        default:
            cout<<"choice was invalid";
    }
    return create;
}
//reads the file and checks if the user has already registered by looking for matching username and 
//password
bool check(string name, string pass)
{
        string us1,pas1;
        bool checked=false;
        //ifstream read("c:\\"+ name+".txt");
        fstream myFile;
        myFile.open(name+".txt",ios::in);
        getline(myFile, us1);
        getline(myFile, pas1);
        if(us1==name && pas1==pass)
        {
          checked =true;
        }
        return checked;
}
main()
{
    string name,passcode, username1,passcode1;
    bool ismember= menu();
    //if the user is not a member then register the user
    if(ismember==false)
    {
        
        cout<<"Enter your username: "; cin>>name;
        cout<<"Enter your password: "; cin>>passcode;
        
        //store the login info of the new member into a file by creating a new file for new members
        ofstream file;
        file.open(name+".txt",ios::out);//write data
        file<< name << endl <<passcode;
        file.close();
        main(); //calls the main function again to prompt the choices for the member to sign in.
    }
    else if(ismember==true)
    {
        cout<<"Enter a username: ";
        cin>>name;
        cout<<"Enter a password: ";
        cin>>passcode;
        //if the user enters the correct username and password, then they are logged into the system.
        bool isloggedIn=check(name, passcode); 
        if(!(isloggedIn))
        {
            cout<<"could not find the username entered";
            system("pause");
        }
        else if(isloggedIn)
        {
            cout<<"you are logged in.";
            system("pause");
            return 1;
        }   
    }
}
