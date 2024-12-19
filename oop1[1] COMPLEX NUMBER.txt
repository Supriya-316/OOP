#include<iostream>
using namespace std;
class complex {
	int x,y;
	public:
		complex() {
			x=0;
			y=0;
		}
        friend void operator >>	(complex &u,complex &v) {
        	cout<<"enter the first real no.:"<<endl;
        	cin>>u.x;
        	cout<<"enter first imaginary no.:"<<endl;
        	cin>>u.y;
        	cout<<"enter the second real no.:"<<endl;
        	cin>>v.x;
        	cout<<"enter second imaginary no.:"<<endl;
        	cin>>v.y;
        	
		}
		friend void operator <<(complex &u,complex &v) {
			cout<<"the first complex number is:"<<u.x<<"+"<<u.y<<"i"<<endl;
			cout<<"the second complex number is:"<<v.x<<"+"<<v.y<<"i"<<endl;
		}
		friend void operator + (complex &u,complex &v) {
			complex add;
			add.x=u.x+v.x;
			add.y=u.y+v.y;
			if(add.y>0) {
				cout<<"the addition of complex no. is :"<<add.x<<"+"<<add.y<<"i"<<endl;
			}
			else {
				cout<<"the addition of complex no. is :"<<add.x<<(-1)*add.y<<"-i"<<endl;
			}
		}
		friend void operator * (complex &u,complex &v) {
			complex mul;
			mul.x=(u.x*v.x)-(u.y*v.y);
			mul.y=(u.x*v.y)+(u.y*v.x);
			if(mul.y>0) {
				cout<<"the multiplication of complex no. is :"<<mul.x<<"+"<<mul.y<<"i"<<endl;
			}
			else {
				cout<<"the addition of complex no. is :"<<mul.x<<(1)*mul.y<<"-i"<<endl;
			}
			
		}
};
int main () {
	char ch;
	char ch1 = 'y';
	complex s1,s2;
	operator >>(s1,s2);
	operator <<(s1,s2);
	do {
		cout<<"select upon choices:"<<endl;
		cout<<"(+)Addition"<<endl;
		cout<<"(*)Multiplication"<<endl;
		cin>>ch;
		switch(ch) {
			case '+' :
				s1+s2;
				break;
			case'*' :
				s1*s2;
				break;
			default :
				cout<<"INVALID OPERATION"<<endl;
		}
		cout<<"DO you want to continue?(Y or N):"<<endl;
		cin>>ch1;
	}while( ch1== 'Y' || ch1 == 'y');
}