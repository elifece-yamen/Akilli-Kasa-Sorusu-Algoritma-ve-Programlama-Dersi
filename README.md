#include <stdio.h>
#include <stdlib.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main(int argc, char *argv[]) {
	
	// 1. Tutar ve Ödenen Parayı 'float' olarak tanımlıyoruz
	float urunTutari, odenenPara;
	float paraUstuTL;
	int kalanKurus;
	int toplamKupurSayisi = 0;
	int adet;
	
	// Ödemenin yeterli olup olmadığını kontrol eden mantıksal değişken (1 veya 0)
	int odemeYeterli = (odenenPara >= urunTutari);	
	
	//Kullanıcıdan girdileri alma
	printf("Urun tutarini giriniz (TL): ");
	scanf("%f", &urunTutari);
	
	printf("Odenen parayi giriniz (TL): ");
	scanf("%f", &odenenPara);
	
	//Para üstünü TL olarak hesaplama
	paraUstuTL = odenenPara - urunTutari;
	
	//KURAL 3: Doğru Yuvarlama Yöntemi (+0.5 ekleyerek int'e dönüştürme)
	//Bu yöntem hassasiyet kaybı nedeniyle 1.299999 olan değeri 130 kuruşa tam yuvarlar.
	kalanKurus = (int)(paraUstuTL * 100 + 0.5);
	
	//KURAL 1 & KURAL 2: Küpür Hesabı (Büyükten küçüğe bölme ve mod alma)
	
	//200 TL = 20000 Kuruş
	adet = kalanKurus / 20000;
	kalanKurus = kalanKurus % 20000;
	toplamKupurSayisi += adet;
	printf("200 TL : %d adet\n", adet);
	
	// 100 TL = 10000 Kuruş
	adet = kalanKurus / 10000;
	kalanKurus = kalanKurus % 10000;
	toplamKupurSayisi += adet;
	printf("100 TL : %d adet\n", adet);
	
	// 50 TL = 50000 Kuruş
	adet = kalanKurus / 5000;
	kalanKurus = kalanKurus % 5000;
	toplamKupurSayisi += adet;
	printf("50 TL : %d adet\n", adet);
	
	// 20 TL = 2000 Kuruş
	adet = kalanKurus / 2000;
	kalanKurus = kalanKurus % 2000;
	toplamKupurSayisi += adet;
	printf("20 TL : %d adet\n", adet);
	
	// 10 TL = 1000 Kuruş
	adet = kalanKurus / 1000;
	kalanKurus = kalanKurus % 1000;
	toplamKupurSayisi += adet;
	printf("10 TL : %d adet\n", adet);
	
	// 5 TL = 500 Kuruş
	adet = kalanKurus / 500;
	kalanKurus = kalanKurus % 500;
	toplamKupurSayisi += adet;
	printf("5 TL : %d adet\n", adet);
	
	// 1 TL = 100 Kuruş
	adet = kalanKurus / 100;
	kalanKurus = kalanKurus % 100;
	toplamKupurSayisi += adet;
	printf("1 TL : %d adet\n", adet);

	// 50 Kuruş
	adet = kalanKurus / 50;
	kalanKurus = kalanKurus / 50;
	toplamKupurSayisi += adet;
	printf("50 Kr : %d adet\n", adet);
	
	// 25 Kuruş
	adet = kalanKurus / 25;
	kalanKurus = kalanKurus / 25;
	toplamKupurSayisi += adet;
	printf("25 Kr : %d adet\n", adet);
	
	// 10 Kuruş
	adet = kalanKurus / 10;
	kalanKurus = kalanKurus / 10;
	toplamKupurSayisi += adet;
	printf("10 Kr : %d adet\n", adet);
	
	// 5 Kuruş
	adet = kalanKurus / 5;
	kalanKurus = kalanKurus / 5;
	toplamKupurSayisi += adet;
	printf("5 Kr : %d adet\n", adet);
	
	// 1 Kuruş
	adet = kalanKurus / 1;
	kalanKurus = kalanKurus / 1;
	toplamKupurSayisi += adet;
	printf("1 Kr : %d adet\n", adet);
	
	// KURAL 2: Toplam verilen küpür sayısını yazdırıyoruz
	printf("---------------\n");
	printf("Toplam Kupur Sayisi: %d\n", toplamKupurSayisi);
	
	
		return 0;
}
	
	return 0;
}
