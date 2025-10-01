# Flappy Bird - C# Windows Forms Oyunu

Bu proje, klasik Flappy Bird oyununun C# Windows Forms kullanılarak geliştirilmiş tam özellikli bir sürümüdür. Orijinal deneyimi korurken ek özellikler ve Türkçe dil desteğiyle geliştirilmiştir.

## 🎮 Oyun Özellikleri
- Dinamik boru sistemi (sürekli yenilenir)
- Gravity ve zıplama mekaniği
- Skor sistemi
- Çarpışma kontrolü
- Game over ekranı
- Yeniden başlatma
- Zorluk seviyesi (hız artışı)
- Çarpışma efektleri (titreme, renk değişimi)
- Ses efektleri
- Türkçe dil desteği

## 🛠️ Kullanılan Teknolojiler
- C#
- Windows Forms
- .NET Framework
- GDI+ (Graphics)

## 📸 Ekran Görüntüleri
- Ana Oyun Ekranı  
- Oyun Bitti Ekranı  
- Yeniden Başlatma  

*(Ekran görüntüleri `Resources/` klasörüne eklenebilir.)*

## 🕹️ Nasıl Oynanır?
- SPACE tuşuna basarak kuşu zıplatın
- Borulara ve yere çarpmadan ilerleyin
- Geçilen her boru çifti için +1 puan alın
- En yüksek skorunuzu kırmaya çalışın!

## 🔄 Oyun Döngüsü ve Bileşenleri
- **Timer**: Her 20ms'de bir `gameTimer_Tick` çalışır  
- **Kuş**: Gravity ile sürekli düşer, zıplama ile yükselir  
- **Boru**: Soldan sağa kayar, ekran dışına çıkınca yeniden konumlandırılır  
- **Skor**: Boru geçişleri ile artar  
- **Çarpışma**: Kuşun borular veya sınırlar ile kesişimi kontrol edilir  
- **Game Over**: Çarpışma sonrası oyun durur, efektler tetiklenir  
- **Restart**: SPACE tuşu ile oyun yeniden başlatılır  

## Oyun Kuralları
1. **Amaç**: Kuşu boruların arasından geçirerek en yüksek skoru elde edin  
2. **Hareket**: Kuş sürekli düşer, SPACE ile yukarı zıplar  
3. **Engeller**: Üst ve alt borulara çarpmayın  
4. **Sınırlar**: Ekranın üst ve alt sınırlarına çarpmayın  
5. **Skor**: Her boru çiftini geçtiğinizde +1 puan  
6. **Zorluk**: Her 15 puanda oyun hızı artar  

## Oyun Mekaniği Detayları
- **Başlangıç Gravity**: 4 (yumuşak düşüş)  
- **Maksimum Gravity**: 10  
- **Zıplama Kuvveti**: -10 (yukarı doğru)  
- **Boru Hızı**: 4'ten 7'ye kadar artar  
- **Boru Aralığı**: 220 pixel  
- **Çarpışma Efekti**: 0.6 saniye titreme ve renk değişimi  

## 📂 Proje Yapısı
```
FlappyBird/
├── Form1.cs                 # Ana oyun mantığı
├── Form1.Designer.cs        # UI tasarım kodu
├── Form1.resx               # Form kaynakları
├── Program.cs               # Uygulama giriş noktası
├── Properties/
│   ├── AssemblyInfo.cs
│   ├── Resources.Designer.cs
│   ├── Resources.resx
│   ├── Settings.Designer.cs
├── Resources/               # Oyun varlıkları
│   ├── Flappy_Bird_1.png
│   ├── Flappy_Bird_2.png
│   ├── PipeHead.png
│   ├── PipeBody.png
└── README.md
```

## 🚀 Geliştirme Süreci
### Faz 1: Temel Oyun Mekaniği
- [x] Kuş hareketi ve gravity sistemi  
- [x] Temel zıplama mekaniği  
- [x] Kuş animasyonu (kanat çırpma)  

### Faz 2: Boru Sistemi
- [x] Dinamik boru oluşturma  
- [x] Boru hareketi ve yeniden konumlandırma  
- [x] Çarpışma kontrolü  

### Faz 3: Oyun Mekaniği
- [x] Skor sistemi  
- [x] Game over mantığı  
- [x] Yeniden başlatma  

### Faz 4: İyileştirmeler
- [x] Türkçe dil desteği  
- [x] Oynanış kolaylaştırmaları  
- [x] Çoklu boru sistemi  
- [x] Sabit pencere boyutu  

### Faz 5: Görsel Efektler
- [x] Çarpışma efektleri  
- [x] Ses efektleri  
- [x] Titreme animasyonu  
- [x] Renk değişimi efektleri  

## ⚙️ Teknik Detaylar
### Ana Sınıflar ve Fonksiyonlar
#### Form1.cs - Ana Oyun Sınıfı
```csharp
public partial class Form1 : Form
{
    int pipeSpeed = 4;           // Boru hareket hızı
    int gravity = 6;             // Gravity kuvveti
    int score = 0;               // Oyuncu skoru
    bool gameOver = false;       // Oyun durumu
    List<PictureBox> pipes;      // Dinamik boru listesi
    
    // Çarpışma efekti değişkenleri
    bool crashEffect = false;    
    int crashEffectTimer = 0;    
}
```

#### Kritik Fonksiyonlar
- **`setupPipes()`**: Dinamik boru sistemini başlatır  
- **`resetGame()`**: Oyunu sıfırlar ve yeniden başlatır  
- **`jump()`**: Kuşun zıplama mekaniği  
- **`gameTimer_Tick()`**: Ana oyun döngüsü  
- **`startCrashEffect()`**: Çarpışma efektini başlatır  
- **`finalizeGameOver()`**: Oyun bitişini tamamlar  

### Çarpışma Kontrolü
```csharp
Rectangle birdRect = new Rectangle(
    FlappyBirdpictureBox1.Left + 5, 
    FlappyBirdpictureBox1.Top + 5, 
    FlappyBirdpictureBox1.Width - 10, 
    FlappyBirdpictureBox1.Height - 10
);
```
- 10 pixel tolerans ile daha adil çarpışma  
- Rectangle intersection kullanımı  

### Boru Pozisyonlama
```csharp
int minHeight = 180; 
int maxHeight = 350; 
int pipeHeight = rand.Next(minHeight, maxHeight);
```

## 🎨 Katkıda Bulunanlar
- **Sen** – Geliştirici  
- Topluluk önerileriyle büyüyebilir  

## 📜 Lisans
Bu proje MIT lisansı altında sunulmaktadır.
