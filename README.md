# Flappy Bird - C# Windows Forms Oyunu

Bu proje, klasik Flappy Bird oyununun C# Windows Forms kullanılarak geliştirilmiş tam özellikli bir sürümüdür. Orijinal deneyimi korurken ek özellikler ve Türkçe dil desteği sunar.

## İçindekiler
- [Özellikler](#özellikler)
- [Teknolojiler](#teknolojiler)
- [Kurulum](#kurulum)
- [Oynanış](#oynanış)
- [Proje Yapısı](#proje-yapısı)
- [Geliştirme Süreci](#geliştirme-süreci)
- [Teknik Detaylar](#teknik-detaylar)
- [Katkıda Bulunma](#katkıda-bulunma)
- [Proje İstatistikleri](#proje-İstatistikleri)
- [Lisans](#lisans)

## Özellikler

### Oyun Mekaniği
- Fizik tabanlı hareket: gerçekçi yerçekimi ve zıplama
- Yumuşak ve duyarlı kontroller
- Dinamik oluşturulan çoklu boru sistemi (3 çift)
- Artan zorluk: skor yükseldikçe hız artışı
- Çarpışma efektleri: görsel ve işitsel geri bildirim

### Görsel Özellikler
- Kuş kanat çırpma animasyonu
- Çarpışma sonrası titreme ve renk değişimi
- Temiz ve anlaşılır kullanıcı arayüzü (UI)
- Tam Türkçe oyun metinleri

### Teknik Özellikler
- Sabit pencere boyutu (yeniden boyutlandırma korumalı)
- 20ms timer ile akıcı oyun döngüsü
- Dinamik nesne yönetimi (bellek verimliliği)
- Hata korumalı ses sistemi

## Teknolojiler

### Ana Framework
- **.NET Framework 4.7.2**: Ana geli�tirme framework'�
- **Windows Forms**: GUI framework'�
- **C# 7.3**: Programlama dili

### Kullan�lan S�n�flar ve Bile�enler
```csharp
// Ana S�n�flar
- Form (Ana oyun penceresi)
- PictureBox (Ku� ve boru g�rselleri)
- Timer (Oyun d�ng�s� ve animasyonlar)
- Label (Skor ve talimatlar)

// Koleksiyonlar
- List<PictureBox> (Dinamik boru y�netimi)
- Rectangle (�arp��ma kontrol�)

// Grafik ve Medya
- System.Drawing (G�rsel i�lemler)
- System.Media.SystemSounds (Ses efektleri)
- Resources (Oyun varl�klar�)
```

### Oyun D�ng�s� Bile�enleri
- **gameTimer**: Ana oyun d�ng�s� (20ms interval)
- **Flying_timer1**: Ku� animasyonu (200ms interval)
- **KeyDown Events**: Keyboard input handling
- **Mouse Click Events**: Mouse input handling

## ?? Kurulum

### Gereksinimler
- Windows 10/11
- .NET Framework 4.7.2 veya �zeri
- Visual Studio 2019/2022 (geli�tirme i�in)

### Kurulum Ad�mlar�
1. **Projeyi �ndirin**
   ```bash
   git clone [repository-url]
   cd FlappyBird
   ```

2. **Visual Studio'da A��n**
   - `FlappyBird.sln` dosyas�n� �ift t�klay�n
   - Veya Visual Studio > File > Open > Project/Solution

3. **Build ve �al��t�r�n**
   - `Ctrl + F5` ile derleyin ve �al��t�r�n
   - Veya Build > Build Solution > Debug > Start Without Debugging

## ?? Oynan��

### Kontroller
| Tu�/Aksiyon | Fonksiyon |
|-------------|-----------|
| **SPACE** | Ku�u z�plat�r / Oyunu yeniden ba�lat�r |
| **Mouse Click** | Ku�u z�plat�r / Oyunu yeniden ba�lat�r |

### Oyun Kurallar�
1. **Ama�**: Ku�u borular�n aras�ndan ge�irerek en y�ksek skoru elde edin
2. **Hareket**: Ku� s�rekli d��er, SPACE ile yukar� z�plar
3. **Engeller**: �st ve alt borulara �arpmay�n
4. **S�n�rlar**: Ekran�n �st ve alt s�n�rlar�na �arpmay�n
5. **Skor**: Her boru �iftini ge�ti�inizde +1 puan
6. **Zorluk**: Her 15 puanda oyun h�z� artar

### Oyun Mekani�i Detaylar�
- **Ba�lang�� Gravity**: 4 (yumu�ak d����)
- **Maksimum Gravity**: 10
- **Z�plama Kuvveti**: -10 (yukar� do�ru)
- **Boru H�z�**: 4'ten 7'ye kadar artar
- **Boru Aral���**: 220 pixel (ge�ilebilir)
- **�arp��ma Efekti**: 0.6 saniye titreme ve renk de�i�imi

## ?? Proje Yap�s�

```
FlappyBird/
??? ?? Form1.cs                 # Ana oyun logic'i
??? ?? Form1.Designer.cs        # UI tasar�m kodu
??? ?? Form1.resx              # Form kaynaklar�
??? ?? Program.cs               # Uygulama giri� noktas�
??? ?? Properties/
?   ??? ?? AssemblyInfo.cs      # Assembly bilgileri
?   ??? ?? Resources.Designer.cs # Kaynak dosyas� y�netimi
?   ??? ?? Resources.resx       # Kaynak tan�mlar�
?   ??? ?? Settings.Designer.cs # Uygulama ayarlar�
??? ?? Resources/               # Oyun varl�klar�
?   ??? ??? Flappy_Bird_1.png    # Ku� sprite 1
?   ??? ??? Flappy_Bird_2.png    # Ku� sprite 2
?   ??? ??? PipeHead.png         # Boru ba��
?   ??? ??? PipeBody.png         # Boru g�vdesi
??? ?? README.md               # Bu dosya
```

## ?? Geli�tirme S�reci

### Faz 1: Temel Oyun Mekani�i
- [x] Ku� hareketi ve gravity sistemi
- [x] Temel z�plama mekani�i
- [x] Ku� animasyonu (kanat ��rpma)

### Faz 2: Boru Sistemi
- [x] Dinamik boru olu�turma
- [x] Boru hareketi ve yeniden konumland�rma
- [x] �arp��ma kontrol�

### Faz 3: Oyun Mekani�i
- [x] Skor sistemi
- [x] Game over logic'i
- [x] Yeniden ba�latma

### Faz 4: �yile�tirmeler
- [x] T�rk�e dil deste�i
- [x] Oynan�� kolayla�t�rmalar�
- [x] �oklu boru sistemi
- [x] Sabit pencere boyutu

### Faz 5: G�rsel Efektler
- [x] �arp��ma efektleri
- [x] Ses efektleri
- [x] Titreme animasyonu
- [x] Renk de�i�imi efektleri

## ?? Teknik Detaylar

### Ana S�n�flar ve Fonksiyonlar

#### Form1.cs - Ana Oyun S�n�f�
```csharp
public partial class Form1 : Form
{
    // Temel oyun de�i�kenleri
    int pipeSpeed = 4;           // Boru hareket h�z�
    int gravity = 6;             // Gravity kuvveti
    int score = 0;               // Oyuncu skoru
    bool gameOver = false;       // Oyun durumu
    List<PictureBox> pipes;      // Dinamik boru listesi
    
    // �arp��ma efekti de�i�kenleri
    bool crashEffect = false;     // Efekt durumu
    int crashEffectTimer = 0;     // Efekt zamanlay�c�s�
}
```

#### Kritik Fonksiyonlar
- **`setupPipes()`**: Dinamik boru sistemini ba�lat�r
- **`resetGame()`**: Oyunu s�f�rlar ve yeniden ba�lat�r
- **`jump()`**: Ku�un z�plama mekani�i
- **`gameTimer_Tick()`**: Ana oyun d�ng�s� (60 FPS)
- **`startCrashEffect()`**: �arp��ma efektini ba�lat�r
- **`finalizeGameOver()`**: Oyun biti�ini tamamlar

### Algoritma Detaylar�

#### �arp��ma Kontrol�
```csharp
Rectangle birdRect = new Rectangle(
    FlappyBirdpictureBox1.Left + 5, 
    FlappyBirdpictureBox1.Top + 5, 
    FlappyBirdpictureBox1.Width - 10, 
    FlappyBirdpictureBox1.Height - 10
);
```
- 10 pixel tolerans ile daha adil �arp��ma
- Rectangle intersection kullan�m�

#### Boru Pozisyonlama
```csharp
int minHeight = 180; // Minimum ge�i� y�ksekli�i
int maxHeight = 350; // Maksimum ge�i� y�ksekli�i
int pipeHeight = rand.Next(minHeight, maxHeight);
```
- Garantili ge�ilebilir aral�klar
- 220 pixel ge�i� bo�lu�u

### Performance Optimizasyonlar�
- **Timer Intervals**: 20ms ana d�ng�, 200ms animasyon
- **Memory Management**: Dinamik liste kullan�m�
- **Efficient Collision**: Rectangle intersection
- **Resource Management**: Shared PictureBox kullan�m�

## ?? Kullan�lan Varl�klar

### G�rsel Varl�klar
- **Flappy_Bird_1.png**: Ku� sprite (kanat yukar�)
- **Flappy_Bird_2.png**: Ku� sprite (kanat a�a��)
- **PipeHead.png**: Boru ba�� (�st ve alt i�in)
- **PipeBody.png**: Boru g�vdesi (kullan�ma haz�r)

### Ses Efektleri
- **System.Media.SystemSounds.Hand**: �arp��ma sesi
- Platform native ses kullan�m�

### Renkler ve Tema
- **Arka Plan**: Sky Blue (`RGB(153, 217, 234)`)
- **Zemin**: Saddle Brown
- **UI Text**: Beyaz ve Sar�
- **�arp��ma Efekti**: K�rm�z� yan�p s�nme

## ?? Gelecek Geli�tirmeler

### Planlanan �zellikler
- [ ] High Score kaydetme sistemi
- [ ] Farkl� ku� karakterleri
- [ ] Ek ses efektleri ve m�zik
- [ ] Power-up'lar ve bonuslar
- [ ] Farkl� zorluk seviyeleri
- [ ] Achievement sistemi

### Teknik �yile�tirmeler
- [ ] Settings dosyas� ile �zelle�tirme
- [ ] Database entegrasyonu
- [ ] Network leaderboard
- [ ] Better graphics ve animasyonlar

## ?? Katk�da Bulunma

### Geli�tirme Ortam� Kurulumu
1. Visual Studio 2019+ y�kleyin
2. .NET Framework 4.7.2 SDK's�n� kurun
3. Projeyi clone edin
4. Dependencies'leri restore edin

### Katk� Y�nergeleri
1. Fork edin
2. Feature branch olu�turun (`git checkout -b feature/AmazingFeature`)
3. De�i�ikliklerinizi commit edin (`git commit -m 'Add some AmazingFeature'`)
4. Branch'e push edin (`git push origin feature/AmazingFeature`)
5. Pull Request olu�turun

## ?? Proje �statistikleri

- **Toplam Kod Sat�r�**: ~400 sat�r C#
- **S�n�f Say�s�**: 1 ana s�n�f (Form1)
- **Method Say�s�**: 12 ana method
- **Varl�k Say�s�**: 4 g�rsel varl�k
- **Geli�tirme S�resi**: ~8 iterasyon
- **Platform**: Windows (.NET Framework)

## ?? Lisans

Bu proje e�itim ama�l� geli�tirilmi�tir. Ticari olmayan kullan�m i�in serbesttir.

## ????? Geli�tirici Notlar�

### ��renilen Konular
- Windows Forms ile oyun geli�tirme
- Timer tabanl� game loop
- Collision detection algoritmalar�
- Resource management
- Event-driven programming
- UI/UX design prensipleri

### Kar��la��lan Zorluklar ve ��z�mler
1. **�arp��ma Tolerans�**: Hitbox k���ltme ile ��z�ld�
2. **Boru Spawn Logic**: Min/Max s�n�rlar ile kontrol edildi
3. **Performance**: Timer interval optimizasyonu
4. **�arp��ma Efektleri**: State management ile y�netildi

---

?? **�yi Oyunlar!** ??

*Bu oyun, klasik Flappy Bird deneyimini modern C# teknolojileri ile yeniden yaratma amac�yla geli�tirilmi�tir.*