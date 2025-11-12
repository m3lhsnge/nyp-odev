
```
interface Animal {
    void sound();
}

// Orijinal Dog sınıfı
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Hav hav!");
    }
    
    public void koruma() {
        System.out.println("Köpek koruyucudur");
    }
}

// Orijinal Cat sınıfı
class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Miyav!");
    }
    
    public void nankor() {
        System.out.println("Kedi nankördür");
    }
}```java
