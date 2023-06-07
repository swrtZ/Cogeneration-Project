#include <iostream> 


using namespace std;


double* t_hesapla_elektrik(double guc) {

	double t1, t2, t3;

	t1 = guc / ((1 * 330) + (0.8 * 150) + (0.25 * 240));
	t2 = t1 * 0.8;
	t3 = t1 * 0.25;
	double* t = new double[3];
	t[0] = t1;
	t[1] = t2;
	t[2] = t3;

	return t;
}
double* t_hesapla_dogalgaz(double dogalgazTuketim, double dogazgazIsil) {
	double t1, t2, t3;
	t1 = dogalgazTuketim * dogazgazIsil * (4.19 / 3600)/1000;
	t2 = t1 * 0.8;
	t3 = t1 * 0.25;
	double* ti = new double[3];
	ti[0] = t1;
	ti[1] = t2;
	ti[2] = t3;
	return ti;
}


double co_hesapla(double coGen[3]) {
	double coGenElektrik;
	double ct1 = coGen[0];
	double ct2 = coGen[1];
	double ct3 = coGen[2];
	coGenElektrik = (ct1 * 320) + (ct2 * 140) + (ct3 * 230);
	return coGenElektrik;
}
void yazdir(double array[3]) {
	for (int i = 0; i < 12; i++) {


	}
}

int main() {
	int x; 
	cout << "Yapmak istediginiz islemi yazin." << endl; 
	cout << "1-Isletme icin girilmis degerleri gormek" << endl;
	cout << "2-Degerleri bastan girmek " << endl; 
	cin >> x;  
	double aylik_kwh[12] = { 21524.860,20232.640,26310.760,20938.400 ,18393.740 , 24821.060 , 16750.460, 22748.260,21664.460,19799.320,14276.680,16551.020 };
	double aylik_dogalGaz[12] = { 6821,7226,6458,5600,4800, 4800,4800,4800,4800,5200,5800,5978 };
	// Girdi - Bagimsiz Degiskenler
	double Enerji_Kapasitesi = 80; // kW
	double Termal_Enerji_Kapasitesi = 72; // kW
	double Isi_sarfiyati = 228; // kcal/kWh
	double Yakit_Tuketimi = 172; // kW
	double Dogalgaz_isil_degeri = 8250; // kcal/m^3 
	double Dogalgaz_fiyati = 13; // TL/m^3 
	double Bakim_birim_maliyeti = 92.82; // TL/cal.saati
	double Calisilan_saat = 180; // saat/ay 
	double Elektrik_fiyat = 3.7; // TL/kWh 
	////////////////////////	
	
	if (x == 1) {
	}
	else if (x==2) {
		Enerji_Kapasitesi = 0 ; // kW
		Termal_Enerji_Kapasitesi = 0 ; // kW
		Isi_sarfiyati = 0; // kcal/kWh
		Yakit_Tuketimi = 0; // kW
		Dogalgaz_isil_degeri = 0 ; // kcal/m^3 
		Dogalgaz_fiyati = 0 ; // TL/m^3 
		Bakim_birim_maliyeti = 0 ; // TL/cal.saati
		Calisilan_saat = 0 ; // saat/ay 
		Elektrik_fiyat = 0 ;

		cout << "Elektrik Kapasitesi (kW) = "; 
		cin >> Enerji_Kapasitesi; 
		cout << endl; 
		cout << "Termal Enerji Kapasitesi (kW) = "; 
		cin >> Termal_Enerji_Kapasitesi; 
		cout << endl; 
		cout << "Isi Sarfiyati (kcal/kWh) = ";
		cin >> Isi_sarfiyati;
		cout << endl; 
		cout << "Yakit tuketimi (kW) = ";
		cin >>Yakit_Tuketimi;
		cout << endl;
		cout << "Calisilan Saat Sayisi (saat/ay) = ";
		cin >>Calisilan_saat ;
		cout << endl;
		cout << "Dogalgaz Fiyati (TL/m3) = "; 
		cin >> Dogalgaz_fiyati; 
		cout << endl; 
		cout << "Elektrik Fiyati (TL/kWh) = "; 
		cin >> Elektrik_fiyat; 
		cout << endl; 
		cout << "Dogalgaz Isil Degeri (kcal/m3) = "; 
		cin >> Dogalgaz_isil_degeri; 
		cout << endl; 
		cout << "Bakim Birim Fiyati (TL/cal.saati) = "; 
		cin >> Bakim_birim_maliyeti; 
		cout << endl; 
	}
	else {
		cout << "Yanlis deger girdiniz ! " << endl; 
	}
	double Uretilicek_Maks_Elektrik = (Enerji_Kapasitesi * 320) + (Enerji_Kapasitesi * 140) + (Enerji_Kapasitesi * 230);
	double toplam_t[3] = { 0,0,0 }; // t[0] = t1 , t[1] =t2 , t[2] = t3 	
	double Elektrik_maliyet;
	double Dogalgaz_maliyet;
	double coGenUretimE[3];
	double coGenUretimD[3];
	for (int k = 0; k < 12; k++) { // AY DONGUSU

		double* ptrk = t_hesapla_elektrik(aylik_kwh[k]);
		double* ptrd = t_hesapla_dogalgaz(aylik_dogalGaz[k], Dogalgaz_isil_degeri);
		cout << endl << k + 1 << ". Ayin degerleri: " << endl;

		cout << endl;

		Elektrik_maliyet = aylik_kwh[k] * Elektrik_fiyat;
		Dogalgaz_maliyet = aylik_dogalGaz[k] * Dogalgaz_fiyati;

		cout << "Elektrik Ihtiyaci (kWh/ay) = " << aylik_kwh[k] << endl;
		cout << "Dogalgaz Tuketimi (m3/ay) = " << aylik_dogalGaz[k] << endl << endl;

		cout << "Elektrik Maliyeti (TL/ay) = " << Elektrik_maliyet << endl;
		cout << "Dogalgaz Maliyeti (TL/ay) = " << Dogalgaz_maliyet << endl;
		cout << "Toplam Enerji Maliyeti (TL/ay) = " << Elektrik_maliyet + Dogalgaz_maliyet << endl;

		cout << endl;

		for (int i = 0; i < 3; i++) { // HER AY İÇİN T ELEKTRİK HESAPLAMA DÖNGÜSÜ 



			cout << "T" << i + 1 << " Saatlerinde Ortalama Cekilen Guc (kW) = " << ptrk[i] << endl;
			coGenUretimE[i] = ptrk[i];
			if (coGenUretimE[i] > Enerji_Kapasitesi) {
				coGenUretimE[i] = Enerji_Kapasitesi;
			}
			else {
				coGenUretimE[i] = coGenUretimE[i] - 2.5;
			}

			toplam_t[i] = toplam_t[i] + ptrk[i];

		}
		cout << endl;
		for (int i = 0; i < 3; i++) { // CO-GEN YAZDIRMA DONGUSU

			cout << "T" << i + 1 << " Saatlerinde Co-Gen'den alinabilecek Maks Guc (kW)= " << coGenUretimE[i] << endl;

		}
		cout << endl;
		for (int i = 0; i < 3; i++) { // HER AY İÇİN T ISITMA IHTIYACI HESAPLAMA DÖNGÜSÜ 



			cout << "T" << i + 1 << " Saatlerinde Ortalama Isitma Ihtiyaci (Kw) = " << ptrd[i] << endl;
			coGenUretimD[i] = ptrd[i];
			if (Termal_Enerji_Kapasitesi * (coGenUretimE[i] / Enerji_Kapasitesi) > ptrd[i]) {
				coGenUretimD[i] = ptrd[i];
			}
			else {
				coGenUretimD[i] = Termal_Enerji_Kapasitesi * (coGenUretimE[i] / Enerji_Kapasitesi);
			}



		}
		cout << endl;
		for (int i = 0; i < 3; i++) { // CO-GEN YAZDIRMA DONGUSU

			cout << "T" << i + 1 << " Saatlerinde Co-Gen'den Alinabilecek Max. Isitma Gucu (kW) = " << coGenUretimD[i] << endl;

		}

		double Isitma_enerjisi_ihtiyaci = (ptrd[0] * 330) + (ptrd[1] * 150) + (ptrd[2] * 240) * 860 / Dogalgaz_isil_degeri / 0.9 ;
		double coGen_Uretecegi_Elektrik = co_hesapla(coGenUretimE);
		double Uretilen_Termal_Enerji = ((Termal_Enerji_Kapasitesi * 320) + (Termal_Enerji_Kapasitesi * 140) + (Termal_Enerji_Kapasitesi * 230)) * (coGen_Uretecegi_Elektrik / Uretilicek_Maks_Elektrik);
		double coGen_Tuketim_Maliyeti = ((Yakit_Tuketimi * 860 / Dogalgaz_isil_degeri) * 320 * Elektrik_fiyat * (coGen_Uretecegi_Elektrik / Uretilicek_Maks_Elektrik)) + (Yakit_Tuketimi * 860 / Dogalgaz_isil_degeri) * 140 * Elektrik_fiyat * (coGen_Uretecegi_Elektrik / Uretilicek_Maks_Elektrik) + (Yakit_Tuketimi * 860 /Dogalgaz_isil_degeri) * 230 * Elektrik_fiyat * (coGen_Uretecegi_Elektrik / Uretilicek_Maks_Elektrik);
		double Tedas_alinan_miktar = aylik_kwh[k] - coGen_Uretecegi_Elektrik;
		double Tedas_maliyet = Tedas_alinan_miktar * Elektrik_fiyat;
		double Ek_DG_maliyet = (((Isitma_enerjisi_ihtiyaci-Uretilen_Termal_Enerji)*860/Dogalgaz_isil_degeri)/0.9)*Dogalgaz_fiyati;
		double Elde_edilecek_DG_tasarrufu; // kwh/ ay 
		if (Uretilen_Termal_Enerji > Isitma_enerjisi_ihtiyaci) {
			Elde_edilecek_DG_tasarrufu = Isitma_enerjisi_ihtiyaci;
		}
		else {
			Elde_edilecek_DG_tasarrufu = Uretilen_Termal_Enerji;
		}
		cout << endl << "Isitma Enerjisi Ihtiyaci (kWh/ay) = " << Isitma_enerjisi_ihtiyaci << endl;

		cout << endl << "Co-Gen Unitesinin Uretecegi Elektrik (kWh/ay) = " << coGen_Uretecegi_Elektrik << endl;
		cout << "Uretilebilecek Max. Elektrik Miktari (kWh/ay) = " << Uretilicek_Maks_Elektrik << endl;
		cout << "Uretilebilen Termal Enerji Miktari (kWh/ay) = " << Uretilen_Termal_Enerji << endl;
		cout << "Isitma Ile Elde Edilecek Dogalgaz Tasarrufu (kWh/ay) = " << Elde_edilecek_DG_tasarrufu << endl;
		cout << "Isitma Ile Elde Edilecek Dogalgaz Tasarrufu (TL/ay) = " << Uretilen_Termal_Enerji * Dogalgaz_fiyati * 1000 / Dogalgaz_isil_degeri << endl;

		cout << endl << "Co-Gen Kapasite Kullanim Orani (%) = " << (coGen_Uretecegi_Elektrik / Uretilicek_Maks_Elektrik) * 100 << endl;
		cout << "Elektrik Ihtiyaci Karsilama Yuzdesi (%) = " << (coGen_Uretecegi_Elektrik / aylik_kwh[k]) * 100 << endl;
		cout << "Isitma Ihtiyaci Karsilama Yuzdesi (%) = " << (Elde_edilecek_DG_tasarrufu / Isitma_enerjisi_ihtiyaci) * 100 << endl;
		cout << "Uretilen Isinin Degerlendirilme Orani (%) = " << (Uretilen_Termal_Enerji / Elde_edilecek_DG_tasarrufu) * 100 << endl;
		cout << "Kumulatif Verim (%) = " <<((Uretilen_Termal_Enerji/(Uretilen_Termal_Enerji*Termal_Enerji_Kapasitesi)+Enerji_Kapasitesi)/Yakit_Tuketimi)*100 << endl;
		cout << "TEDAS'tan Alinan Elektrik Miktari (kWh/ay) = " << Tedas_alinan_miktar << endl;

		cout << endl << "Co-Gen Unitesi Tuketim Maliyeti (TL/ay) = " << coGen_Tuketim_Maliyeti << endl;
		cout << "TEDAS Elektrik Maliyeti (TL/ay) = " << Tedas_maliyet << endl;
		cout << "Ek Dogalgaz Maliyeti (TL/ay) = " << Ek_DG_maliyet << endl;
		cout << "Toplam Enerji Maliyeti (TL/ay) = " << coGen_Tuketim_Maliyeti + Tedas_maliyet + Ek_DG_maliyet << endl;

		cout << endl << "TOPLAM BRUT TASARRUF (TL/AY) = " << (Elektrik_maliyet + Dogalgaz_maliyet) - (coGen_Tuketim_Maliyeti + Tedas_maliyet + Ek_DG_maliyet) << endl;
		cout << endl << "1.ve 2. UNITE CALISMA SAATI = " << Calisilan_saat << endl;
		cout << "3.ve 4. UNITE CALISMA SAATI = " << Calisilan_saat << endl;
		cout << endl << "YILLAR = " << k << endl;
		cout << "AMORTISMAN (EUR) = " << "NULL" << endl;
		cout << endl << "BAKIM GIDERLERI = " << Bakim_birim_maliyeti*Calisilan_saat*2<< endl;
		cout << "YAGLAMA MALIYETI =  " << 12350 << endl;
		cout << "TOPLAM ISLETME GIDERI = " << Bakim_birim_maliyeti * Calisilan_saat * 2 + 12350 << endl;
		cout << "TOPLAM NET TASARRUF = " << (Elektrik_maliyet + Dogalgaz_maliyet) - (coGen_Tuketim_Maliyeti + Tedas_maliyet + Ek_DG_maliyet) - Bakim_birim_maliyeti * Calisilan_saat * 2 + 12350 << endl;
		cout << endl << "********************************************************************************************" << endl;

		delete[] ptrk;
		delete[] ptrd;
	}
	// YIL SONU 



	double toplam_guc = 0;
	for (int i = 0; i < 3; i++) {

		toplam_guc = toplam_t[i] + toplam_guc;

	}

	

	return 0;
}
