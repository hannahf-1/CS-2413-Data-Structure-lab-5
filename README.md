# C-Lab-5
finds the capital gain and loss 

#include <iostream>
#include <queue> 
using namespace std;

//print the queue 
void showq(queue<int> q)
{
    queue<int> queue0= q;
    while(!queue0.empty())
    {
        cout << '\t' << queue0.front();
        queue0.pop();
    }
    cout << '\n';
}

//driver code 
int main()
{
    //intializing variables and queues
    int amountShares, costShare, shareSold, costSold, ans; 
    queue<int> shareQueue;
    queue<int> costQueue;
   
   //asking for input and storing them 
    for (int i =1; i <= 3; i++)
    {
        cout << endl << "How many shares were brought on day " << i << "? ";
        cin >> amountShares;
        cout << "How much did each share cost? ";
        cin >> costShare;
        shareQueue.push(amountShares);
        costQueue.push(costShare);
    }
    
    //what was sold 
    cout << "\n\nHow many shares were sold? ";
    cin >> shareSold; 
    cout << "How much were they sold for? ";
    cin >> costSold;
    
    //calucating the captial gain 
    int x= shareQueue.front();
    shareQueue.pop();
    int y= costQueue.front();
    costQueue.pop();
    
    ans= x*10 + y*6 + costSold*(-6);
    
    
    
    //printing the output 
    cout << "\n\aThe capital gain is:: $" << ans;
    
    
}
