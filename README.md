A repository to save my all tasks(code in C++) for an internship in CodSoft

Task # 1--> [A number guessing game] :
#include<iostream>
#include<cstdlib>
#include<ctime>
using namespace std ;
int main(){
	srand(time(0)) ;
	int num=0, g=0 ;
	num=rand()%20+1 ;
	cout<<"Guess the number: " ;
	cin>>g ;
	while(g!=num){
		if(g>num){
			cout<<endl<<"Your guess is higher than actual number"<<endl<<"GUESS AGAIN: " ;
			cin>>g ;
		}
		else if(g<num){
			cout<<endl<<"Your guess is lesser than actual number"<<endl<<"GUESS AGAIN: " ;
			cin>>g ;
		}
	}
	cout<<endl<<g<<" is the right guess !!" ;
}


TASK # 02--> [Simple Calculator] :
#include<iostream>
#include<cstdlib>
using namespace std ;
int main() {
	int n1=0, n2=0 ;
	char sym ;
	cout<<"Enter first number: " ;
	cin>>n1 ;
	cout<<"Enter second number: " ;
	cin>>n2 ;
	cout<<"Enter sign: " ;
	cin>>sym ;
	if(sym=='+'){
		cout<<endl<<(n1)+(n2) ;
	}
	if(sym=='-'){
		cout<<endl<<abs((n1)-(n2)) ;
	}
	if(sym=='*'){
		cout<<endl<<n1*n2 ;
	}
	if(sym=='/'){
		cout<<endl<<n1/n2 ;
	}
}


TASK # 03--> [A To-Do Application]:
#include<iostream>
#include<vector>
using namespace std ;
struct TASK {
	string data ;
	string sts ;
};
int main() {
	vector<TASK> tasks ;
	vector<TASK> :: iterator pt ;
    TASK p, q ;
    string d ;
	int x=0, f=0 ;
	while(f==0){
		cout<<endl<<"Press 1 to add new task\nPress 2 to display previous tasks\nPress 3 to delete any task\nPress 4 to mark the status of task\nPress 0 to exit an application: " ;
		cin>>x ;
		if(x==0){
			break ;
		}
		else{
			if(x==1){
				cout<<endl<<"Enter the task: " ;
				cin.ignore() ;
				getline(cin,d) ;
				p.data=d ;
				p.sts="Pending" ;
				tasks.push_back(p) ;
			}
			if(x==2){
				for(int a=0 ; a<tasks.size() ; a++){
					q = tasks[a] ;
					cout<<endl<<q.data<<" "<<"["<<q.sts<<"]" ;
				}
				cout<<endl ;
			}
			if(x==3){
				int g=0 ;
				for(int a=0 ; a<tasks.size() ; a++){
					q = tasks[a] ;
					cout<<endl<<q.data<<" "<<"["<<q.sts<<"]" ;
				}
				cout<<endl<<"Enter index number of a task to delete it: " ;
				cin>>g ;
				pt = tasks.begin() + (g-1) ;
				tasks.erase(pt) ;
				for(int a=0 ; a<tasks.size() ; a++){
					q = tasks[a] ;
					cout<<endl<<q.data<<" "<<"["<<q.sts<<"]" ;
				}
				cout<<endl ;
			}
			if(x==4){
				int l=0 ;
				for(int a=0 ; a<tasks.size() ; a++){
					q = tasks[a] ;
					cout<<endl<<q.data<<" "<<"["<<q.sts<<"]" ;
				}
				cout<<endl<<"Now enter index number of a task to change the status of: " ;
				cin>>l ;
				q=tasks[l-1] ;
				if( q.sts=="Pending" ){
					q.sts="Finished" ;
				}
				else{
					q.sts="Pending" ;
				}
				tasks[l-1]=q ;
				for(int a=0 ; a<tasks.size() ; a++){
					q = tasks[a] ;
					cout<<endl<<q.data<<" "<<"["<<q.sts<<"]" ;
				}
				cout<<endl ;
			}
		}
	}
}
