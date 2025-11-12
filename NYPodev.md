

### Orijinal Animal interface


```
interface Animal {
    void sound();
}

// Orijinal Dog sınıfı
public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Hav hav!");
    }
    
    public void koruma() {
        System.out.println("Köpek koruyucudur");
    }
}

// Cat sınıfı
public class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Miyav!");
    }
    
    public void nankor() {
        System.out.println("Kedi nankördür");
    }
}
```
### SORU 1 CEVAP: HATALAR VE ÇÖZÜMLER

#### HATALAR:
1. print(a.koruma) - HATA: Animal interface'inde koruma() metodu yok
2. print(a.nankor) - HATA: Animal interface'inde nankor() metodu yok
3. Sadece sound() metodu çağrılabilir çünkü Animal referansı kullanılıyor

#### POLİMORFİZM FARKI: 
- Referans tipi (Animal) hangi metodlara erişileceğini belirler
- Nesne tipi (Dog/Cat) hangi metodun çalışacağını belirler
- Bu polimorfizmin temelidir!

### SORU 2: Polimorfizm Amacı ve Faydaları

#### POLİMORFİZM AMAÇLARI:
1. Esneklik: Aynı kodu farklı tiplerle kullanabilme
2. Genişletilebilirlik: Yeni tipler eklerken mevcut kodu değiştirmeden
3. Bakım Kolaylığı: Tek bir yerde değişiklik tüm alt sınıflara yansır
4. Soyutlama: Detayları gizleyip genel davranışlara odaklanma

#### FAYDALARI:
- Kod tekrarını azaltır
- Bakımı kolaylaştırır
- Yeni özellikler eklemeyi basitleştirir
- Loose coupling (gevşek bağlantı) sağlar
- Open/Closed Principle: Genişletmeye açık, değişikliğe kapalı

>Gerekli mi? Evet, modern yazılım geliştirmenin temel taşıdır.

### SORU 3: Çalışma Zamanı vs Derleme Zamanı

#### DERLEME ZAMANI (Compile Time):
- Kodun Java derleyicisi tarafından kontrol edildiği an
- Tip kontrolü yapılır
- Sözdizimi (syntax) hataları bulunur
- Referans tipine göre metod erişimi kontrol edilir

#### ÇALIŞMA ZAMANI (Runtime):
- Programın çalıştığı an
- Gerçek nesne tipine göre metod çalıştırılır
- Method overriding burada devreye girer

### SORU 4: Upcast ve Downcast

#### UPCAST (Yukarı Dönüşüm):
- Alt sınıftan üst sınıfa/interface'e dönüşüm
- Otomatik ve güvenlidir
- Polimorfizmin temelidir

#### DOWNCAST (Aşağı Dönüşüm):
- Üst sınıftan/interface'den alt sınıfa dönüşüm
- Manuel yapılır ve risklidir
- instanceof ile kontrol edilmelidir

### SORU 5: Static Metodlar ve Polimorfizm

#### CEVAP: HAYIR, static metodlar polimorfizm kullanamaz!

#### NEDEN?
- Static metodlar sınıfa aittir, nesneye değil
- Derleme zamanında referans tipine göre belirlenir
- Override edilemez, sadece gizlenirler (hiding)
- Runtime polimorfizmi yoktur






