

>*ÖDEV : Polimorfizm – inrterface ve class yapısında irdelenmesi*
*NOT: 05.11.2025 tarihli dersimizde yazdığımız kodu bilgisayarlarınızda yazınız.*
*Animal -> interface*
*Sound() ;*
*Dog -> sınıf implements Animal*
*Koruma(){ print(“Köpek koruyucudur”};*
*Cat -> sınıf implements Animal*
*Nankor(){print(“Kedi nankördür”)}*
*Main ()*
*List<Animal> oluşturun.*
*Animal dog=new Dog() şeklinde Animal referansıyla Dog sınıfından nesne*
*üretin.*
*Animal cat=new Cat() şeklinde Animal referansıyla Cat sınıfından nesne*
*üretin.*
*makeItSound(Animal a) {*
*print(a.sound) // ne yazar?*
*print(a.Koruma) // ne yazar?*
*print(a.Nankor) // ne yazar?*
*}*
*Soru 1.) Yukarıda yazdığımzı kod çalışır mı nerelerde hata verir irdeleyin. Sınıfta fark*
*etmediğiniz bir şey var mı bu ödevle fark ettiniz mi? Size katkısı ne oldu yazınız.*
*Hataları madde madde yazın ve çözüm şekilleri neler açıklayın. Tüm çözüm*
*şekillerini yazmanızı bekliyorum. Çalışır aynı sonucu veren kodların hepsini*
*bekliyorum.*
*Soru 2.)Polimorfizm amacaı ve faydaları nelerdir. Sizce gerekli mi?*
*Soru 3.) Çalışma zamanı ve derleme zamanı nedir? Bu örnekte uygulayarak anlatın*
*Soru 4.) upcast ve downcast nedir? Bu örnekte uygulayarak anlatın.*
*Soru 5.) static metodların polimorfizm kullanımı mümkün mü? Mümkünse veya*
*değilse kodla açıklayarak yazın.*
S*Soru 6.) Koleksiyonlar / veri yapılaro üzerinde polimorfizm nasıl kullanılır. Kullanılır mı*
**? Gerekli mi ? kodlarla açıklayın.*
*Soru 7.) İnstanceof kullanımını switch case ile de sağlayabilir miyiz ? bunu irdeleyin*
*Bu sorulara hazırlanan cevap kodlar yukarıdaki örneği çözen kodlar olacak.*
*Bu örneği geliştirebilirsiniz. Kapsülleme, miras alma yöntemlerini uygulayabilirsiniz.*
*Fonksiyon ve parametreler ekler geliştirirseniz size faydalı olacaktır. Kodu farklı farklı*
*yazmaya çalışın.*


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






