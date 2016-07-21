#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

void bubblepp(int *tab,int ile){
	int bufor,x=0;
	bool zamiana=true;
	while(zamiana==true){
		zamiana=false;
		for (int j=ile-1; j>x; j--){
			if (tab[j]<tab[j-1]){
				zamiana=true;
				bufor=tab[j];
				tab[j]=tab[j-1];
				tab[j-1]=bufor;
			}
		}
		x++;
	}
	cout<<"DONEO"<<endl;
}
void bubble(int *tab, int ile){
	int bufor;
	for (int i=1; i<ile; i++){
		for (int j=ile-1; j>0; j--){
			if (tab[j]<tab[j-1]){
				bufor=tab[j];
				tab[j]=tab[j-1];
				tab[j-1]=bufor;
				}
		}
	}
	cout<<"DONE"<<endl;
}
void bubblep(int *tab, int ile){
	cout<<"HIER"<<endl;
	int bufor;
	bool nadal=true;
	while (nadal==true){
		nadal=false;
		for (int i=ile-1; i>0; i--){
			if (tab[i]<tab[i-1]){
				nadal=true;
				bufor=tab[i];
				tab[i]=tab[i-1];
				tab[i-1]=bufor;
			}
		}
	}
	cout<<"DONENO"<<endl;
}
int main() {
	clock_t start, stop;
	double czas;
	int ile;
	cout<<"Ile liczb w tablicy?"<<endl;
	cin>>ile;
	int *tab=new int [ile];
	int *tab2=new int [ile];
	int *tab3=new int [ile];
	cout<<"PRZED SORTOWANIEM"<<endl;
	for (int i=0; i<ile; i++){
		tab[i]=rand()%10000;
		tab2[i]=tab[i];
		tab3[i]=tab[i];
	}
	cout<<"PO SORTOWANIU"<<endl;
	bubblepp(tab,ile);
	bubble(tab2,ile);
	bubblep(tab3,ile);
	for (int i=0; i<ile; i++){
		cout<<tab[i]<<endl;
		cout<<tab2[i]<<endl;
		cout<<tab3[i]<<endl;
	}
	return 0;
}
