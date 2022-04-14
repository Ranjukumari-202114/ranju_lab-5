# ranju_lab-5

#include <iostream>
using namespace std;

class Account
{
    private:
    int bal = 0;
    
    public:
    
    Account(int a)
    {
        bal = a;
    }
    int depositeMoney(int add_amount)                                    //function to deposite money
    {
        bal= bal+add_amount;
        return bal;
    }
    int withdrawMoney(int withdraw_money)                                //function to withdraw money
    {
        if(bal>=withdraw_money)
        {
            bal = bal-withdraw_money;
            return 1;
        }
        else
        {
            cout<<"ALERT! Insufficient balance."<<endl;
            return -1;
        }
    }
    int interest(int rate,int time)                             //calculate interest
    {
        bal = (bal*rate*time/100)+bal;
        return bal;
    }
    void display()                                              //display function to show value
    {
        cout<<"The current balance in your account:"<<bal;
    }
      
};

int main()
{
    Account A1= Account(10000);
    A1.depositeMoney(50000);
    int status = A1.withdrawMoney(20000);
    if(status==1)
    {
        A1.interest(5,2);
        A1.display();
    }
    
    return 0;
}
