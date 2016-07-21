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
}
void bubblep(int *tab, int ile){
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
	for (int i=0; i<ile; i++){
		tab[i]=rand()%10000;
		tab2[i]=tab[i];
		tab3[i]=tab[i];
	}
	start=clock();
	bubblepp(tab,ile);
	stop=clock();
	czas=(double)(stop-start)/CLOCKS_PER_SEC;
	cout<<"Najszybsza metoda: "<<czas<<endl;
	start=clock();
	bubble(tab2,ile);
	stop=clock();
	czas=(double)(stop-start)/CLOCKS_PER_SEC;
	cout<<"Zwykla metoda: "<<czas<<endl;
	start=clock();
	bubblep(tab3,ile);
	stop=clock();
	czas=(double)(stop-start)/CLOCKS_PER_SEC;
	cout<<"Metoda srednia: "<<czas<<endl;
	return 0;
}
