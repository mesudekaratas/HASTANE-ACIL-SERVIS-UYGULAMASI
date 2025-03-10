# HASTANE-ACIL-SERVIS-UYGULAMASI
veri yapıları ve algoritmalar dersi ödevi 16.03.2025

#include <stdio.h>
#include <string.h>
#include <time.h>
#include <stdlib.h>

typedef struct hasta{
    char isim[150];
    int yas[3];
    char hastalik[100];
    int tc[11];
    char cinsiyet[100];
}hasta;

int main() {
   
   while(1){
       
    printf("   ----- ACİL SERVİS ----- \n");
    
    int durum;
  printf("\nHASTANIN TRİYAJA GİTTİĞİNDEN EMİN OLUNUZ.\n");
  printf("\n");
  
  printf("TRİYAJDA HANGİ ALANA YÖNLENDİRİLDİĞİNİZİ GİRİNİZ: \n(1: Yesil/Yuksek, 2: Sari/Orta, 3: Kirmizi/Dusuk): ");
  scanf("%d", &durum);
  
  if(durum==1||durum==2||durum==3){
      printf("yönlendiriliyorsunuz... \n");
  }
  else{
      printf("geçerli alanı giriniz.\n");
  }
  
    
    printf("\n");
    
    printf("HASTA KAYIT YAPTIRINIZ -> \n");
     printf("\n");
  
    hasta h;
    
    printf("   ----- HASTA KAYIT İŞLEMLERİ ----- \n");
    printf("HASTANIN ADI-SOYADI: ");
    getchar(); // ?
    fgets(h.isim, 100, stdin);
    h.isim[strcspn(h.isim,"\n")] = 0;
    
    printf("HASTANIN TC KİMLİK: ");
    scanf("%d",&h.tc);
    
    printf("HASTANIN CİNSİYETİ: ");
    scanf("%s",h.cinsiyet);
    
     printf("HASTANIN YAŞI: ");
     scanf("%d", &h.yas);
     getchar();

     printf("HASTANIN ŞİKAYETİ: ");
     fgets(h.hastalik, 100, stdin);
     h.hastalik[strcspn(h.hastalik, "\n")] = 0;
    
  
    printf("\n");
    
    printf("   -----HASTA ÖNCELİK SİRASİ -----   \n");
 
    if (durum == 1) {
        printf("YEŞİL ALAN\n");
    } else if (durum == 2) {
        printf("SARI ALAN\n");
    } else if (durum == 3) {
        printf("KIRMIZI ALAN\n");
    } else {
        printf("Gecersiz durum!\n");
        return 1; 
    }

    if (durum == 3) {
        printf("SIRA YOK, ACIL MÜDAHALE!\n");
    } else if (durum == 2) {
        srand(time(NULL)); 
        int sira = 100 + rand() % 300; 
        printf("SIRA NO: %d\n", sira);
    }
    else if (durum == 1 ) {
        srand(time(NULL)); 
        int sira = 700 + rand() % 900; 
        printf("SIRA NO: %d\n", sira);}
    
    printf("\n");
    
    printf("   ----- ACİL SERVİS ODASI NO:  -----   \n");
    
    int odano;
    
    if(durum==3){
        printf("DİREKT MUAYENE, ACİL DURUM");
    }
    else if(durum==2||durum==1){
        srand(time(NULL));
        odano= 1 + rand() % 10;
        printf("ACİL SERVİS ODA NO: %d\n",odano);
    }
     printf("\n");
    
     printf("   ----- HASTANIN VİTAL BULGULARI:  -----   \n");
     
     double vital;
     srand(time(NULL));
     vital= 36.0 + ((rand() % 41) / 10.0);
     printf("HASTANIN ATEŞİ: %.1f°C\n",vital);
     
     int sistolik = 100 + rand() % 41; 
     int diyastolik = 60 + rand() % 31;

    printf("HASTANIN TANSİYONU: %d/%d mmHg\n", sistolik, diyastolik);
    
    int nabız = 60 + rand () % 130;
    printf("HASTANIN NABIZ SAYISI: %d adım/dakika\n",nabız);
    
     printf("\n");
     
      printf("   ----- DOKTOR YÖNLENDİRMELERİ SONUCUNDA VERİLEN REÇETE NO: -----   \n");
      
      if(durum==3){
          printf("HASTA TEDAVİ GÖRÜYOR, REÇETE NO YOK\n");
      }
    else if(durum==2 || durum==1){
        srand(time(NULL));
        int receteno = 100000 + rand() % 900000;
        printf("REÇETE NO: %d\n",receteno);
    }
    else{
        printf("geçersiz durum!\n");
    }
    printf("\n");
    printf("\n");
    
    
    }
    return 0;
}
