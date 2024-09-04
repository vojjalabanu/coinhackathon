#include<bits/stdc++.h>
using namespace std;

//declarations
vector<map<string,string>>v1(26);
vector<map<string,vector<string>>>v2(26);
string profileId,profileName,location,contact,gender,occupation,postsCount;
map<string,int>followersCount,followingCount;
map<string,map<string,string>>mp;
map<string,vector<string>>ml;

//Printing the details of a profile
void printDetails(map<string,map<string,string>>&mp,map<string,vector<string>>&ml){
    cout<<"Enter profileName: ";
    string profileName;std::cin>>profileName;
    for(pair<string,string>p:mp[profileName]){
        std::cout<<p.first<<": "<<p.second<<"\n";
    }
    cout<<"FriendsList: \n";

    for(int i=0;i<ml[profileName].size();i++){
        cout<<ml[profileName][i]<<" ";
    }
}

//Takes input os two friend names and make second as friend of first
//increment following count of friend2,increment followers count of friend1
void makeFriends(map<string,vector<string>>&ml,map<string,int>&followersCount,map<string,int>&followingCount){
    string friend1,friend2;
    cout<<"Enter friend1: ";std::cin>>friend1;
    cout<<"Enter friend2: ";std::cin>>friend2;
    ml[friend1].push_back(friend2);
    followersCount[friend1]++;
    followingCount[friend2]++;
}

//Display either followers or following count depending on the input a or b
void followCount(map<string,int>&followersCount,map<string,int>&followingCount){
    string profileName;
    cout<<"Enter profileName: ";std::cin>>profileName;
    cout<<"Enter a or b: ";
    char ch;std::cin>>ch;
    if(ch=='a'){
        cout<<followersCount[profileName]<<"\n";
    }
    else{
        cout<<followingCount[profileName]<<"\n";
    }
}

//Diplaying the mutual friends of two friends
void displayMutuals(map<string,vector<string>>&ml){
    string friend1,friend2;
    cout<<"Enter friend1: ";std::cin>>friend1;
    cout<<"Enter friend2: ";std::cin>>friend2;
    for(int i=0;i<ml[friend1].size();i++){
        for(int j=0;j<ml[friend2].size();j++){
            if(ml[friend1][i]==ml[friend2][j])
            cout<<ml[friend1][i]<<" ";
        }
    }
}

//Suggest friends based on friend's friends
void suggestFriends(map<string,vector<string>>&ml){
    string profileName;
    cout<<"Enter profileName: ";std::cin>>profileName;
    cout<<"Suggested Friends: \n";
    for(int i=0;i<ml[profileName].size();i++){
        for(int j=0;j<ml[ml[profileName][i]].size();j++){
            cout<<ml[ml[profileName][i]][j];
        }
    }
}

//Diplaying the profile with highest followerslist
void mostPopular(map<string,int>&followersCount){
    string profileName="";
    int c=0;
    for(auto it:followersCount){
        if(c<it.second){
            c=it.second;
            profileName=it.first;
        }
    }
    cout<<profileName<<"\n";
}

//Displaying the profile with top in following
void topinFollowing(map<string,int>&followingCount){
    string profileName="";
    int c=0;
    for(auto it:followingCount){
        if(c<it.second){
            c=it.second;
            profileName=it.first;
        }
    }
    cout<<profileName<<"\n";
}

//Make friends until user requires
void Make(){
    while(true){
        cout<<"1:Make friends 2:Don't make\nEnter your choice: ";
        int ch;std::cin>>ch;
        if(ch==2)break;
        else{
            makeFriends(ml,followersCount,followingCount);
        }
    }
}

//creating accounts for 26 profile names
void createAccount(int i){
        string profileId,profileName,location,contact,gender,occupation,postsCount;
        std::cout<<"Enter profileId: ";
        std::cin>>profileId;
        v1[i]["profileId"]=profileId;
        std::cout<<"Enter profileName: ";
        std::cin>>profileName;
        v1[i]["profileName"]=profileName;
        std::cout<<"Enter location: ";
        std::cin>>location;
        v1[i]["location"]=location;
        std::cout<<"Enter contact: ";
        std::cin>>contact;
        v1[i]["contact"]=contact;
        std::cout<<"Enter gender: ";
        std::cin>>gender;
        v1[i]["gender"]=gender;
        std::cout<<"Enter occupation: ";
        std::cin>>occupation;
        v1[i]["occupation"]=occupation;
        std::cout<<"Enter postsCount: ";
        std::cin>>postsCount;
        v1[i]["postsCount"]=postsCount;
        mp[profileName]["profileId"]=profileId;
        mp[profileName]["profileName"]=profileName;
        mp[profileName]["location"]=location;
        mp[profileName]["contact"]=contact;
        mp[profileName]["gender"]=gender;
        mp[profileName]["occupation"]=occupation;
        mp[profileName]["postsCount"]=postsCount;
}

//Display the number of posts of a user
void displayposts(map<string,map<string,string>>&mp){
    string profilename;std::cin>>profilename;
    cout<<mp[profilename]["postsCount"];
}

int main(){

    //asking user to take choice and display the required
    bool flag=true;
    while(flag)
    {
        int ch;
        cout<<"Enter choice: ";
        std::cin>>ch;
        switch(ch){
            case 1:for(int i=0;i<5;i++){
                        createAccount(i);
                    }
                    break;
            case 2:printDetails(mp,ml);break;
            case 3:Make();break;
            case 4:followCount(followersCount,followingCount);break;
            case 5:displayMutuals(ml);break;
            case 6:suggestFriends(ml);break;
            case 7:mostPopular(followersCount);break;
            case 8:displayposts(mp);break;
            case 9:topinFollowing(followingCount);break;
            case 10:cout<<"App Closed\nThank You";flag=false;break;
            default:cout<<"enter correct choice ";break;

            
        }
    }
}
