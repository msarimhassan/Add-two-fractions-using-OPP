# Add-two-fractions-using-OPP
#include<iostream>
#include<cstdlib>
#include<ctime>
using namespace std;

class fraction
{
	public:
	int numenator;
	int denominator;
	public:
	fraction()
	{
	numenator=0;
	denominator=0;
	}
	
	fraction(int n, int d)
	{
		numenator=n;
		denominator=d;
	}
	setnumenator(int n)
	{
		numenator=n;
		
	}
	setdenominator(int d)
	{
		denominator=d;
	}
	int getnumenator()
	{
		return numenator;
		}	
		int getdenominator()
		{
			return denominator;
		}
		show()
		{
			cout<<this->numenator<<" / "<<this->denominator;
		}
};
class mathproblem
{
	public:
		fraction obj1;
		fraction obj2;
		fraction obj3;
	    fraction obj4;
		int numinator,deno;
	//	srand(time(0));
	int indicator;

	setproblem()
	{
	srand (time(0));
	
	obj1.setnumenator(rand()%10+1);
	obj1.setdenominator(rand()%10+1);
	
	obj2.setnumenator(rand()%10+1);
	obj2.setdenominator(rand()%10+1);

   }
	
	displayproblem()
	{
			srand (time(0));
		indicator=rand()%4+1;
	if (indicator==1)
	{
	
		obj1.show();
		cout<<" "<<"X"<<" ";
		obj2.show();
		cout<<endl;
	
		obj3.setnumenator(obj1.getnumenator()*obj2.getnumenator());
		obj3.setdenominator(obj1.getdenominator()*obj2.getdenominator());
	}
	else if(indicator==2)
	{
		obj1.show();
		cout<<" "<<"/"<<" ";
		obj2.show();
		cout<<endl;
		obj3.setnumenator (obj1.getnumenator()*obj2.getdenominator());
		obj3.setdenominator(obj1.denominator*obj2.getnumenator());
	}
	else if(indicator==3)
	{
		obj1.show();
		cout<<" "<<"+"<<" ";
		obj2.show();
		cout<<endl;
		obj3.setnumenator (obj1.getnumenator()*obj2.getdenominator() + obj1.getdenominator()*obj2.getnumenator());
		obj3.setdenominator(obj1.getdenominator()*obj2.getnumenator());
		
	}
	else if(indicator==4)
	{
 	obj1.show();
		cout<<" "<<"-"<<" ";
		obj2.show();
		cout<<endl;
		obj3.setnumenator( obj1.getnumenator()*obj2.getdenominator() - obj1.getdenominator()*obj2.getnumenator());
		obj3.setdenominator( obj1.getdenominator()*obj2.getnumenator());
	}
}
    askuserforanswer()
    {
     cout<<"ENTER YOUR ANSWER"<<endl;
     cin>>numinator;
     obj4.setnumenator(numinator);
     cin>>deno;
     obj4.setnumenator(deno);
    }
    bool isanswer()
    {
	
      if (obj3.getnumenator()==numinator && obj3.getdenominator()==deno )
     	{
     		return true;
		}
		else
		{
			cout<<"WRONG ANSWER"<<endl;
			return false;
		}
	}
	 
};
int main()
{
	mathproblem obj1;
	obj1.setproblem();
	obj1.displayproblem();
	obj1.askuserforanswer();
	bool found=obj1.isanswer();
	if( found==true)
	{
		cout<<"CORRECT ANSWER";
	}

		
	

	
}

