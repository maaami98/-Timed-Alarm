#include <iostream>
	
	#include <ctime>
	
	#include <windows.h>
	using namespace std;
	int main() {
	    std::clock_t start;
	    int sure;
	
	     //süreye şu anki zamanı atadı
	
	    setlocale(LC_ALL,"Turkish");
		cout<<"Alarım Süresini Giriniz\n";
		cout<<"Dakika:";
		int dk;
		cin>>dk;
		cout<<"Saniye:";
		int sn;
		cin>>sn;
		sn=sn+(dk*60);
		start = std::clock();
		while(1){
	    sure = ( std::clock() - start ) /  CLOCKS_PER_SEC;
	    system("cls");
	    cout<<"Alarm Kuruldu.\n";
	    switch(sure%4)
	    {
	    	case 0:{cout<<"-";
				break;
			}
			case 1:{cout<<"\\";
				break;
			}
			case 2:{cout<<"|";
				break;
			}
			case 3:{cout<<"/";
				break;
			}
		}
		printf("  %d:%d",(sn-sure)/60,(sn-sure)%60);
		if(sure==sn)break;
		Sleep(1000);
		}
		PlaySound("alarm.wav",NULL, SND_FILENAME|SND_LOOP);
	  
	}
