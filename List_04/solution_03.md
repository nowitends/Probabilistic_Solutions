# Task 3 — Binom Dağılımı: Bin(n, p)

---

## 1. Deneyin Modellenmesi: n Bernoulli Denemesi

### Deney Tanımı

**Örnek Deney:** Adil bir bozuk para 10 kez atılıyor. Her atışta "yazı" gelmesi başarı sayılıyor.

Daha genel olarak: Aynı koşullar altında **n kez** tekrarlanan, her seferinde yalnızca iki olası sonucu olan (başarı / başarısızlık) bir deney.

**Bernoulli Koşulları:**
- Her deneme bağımsızdır.
- Her denemede başarı olasılığı **p** sabittir (0 < p < 1).
- n denemelerin sayısı önceden belirlenmiştir.

---

### Örnek Uzay Ω

n = 3 için örnek uzay:

```
Ω = { (B,B,B), (B,B,Y), (B,Y,B), (B,Y,Y),
       (Y,B,B), (Y,B,Y), (Y,Y,B), (Y,Y,Y) }
```

Genel olarak: |Ω| = 2ⁿ

---

### Temel Sonuç ω

Bir temel sonuç, n denemeden oluşan bir sıralı listedir:

```
ω = (ω₁, ω₂, ..., ωₙ)   burada ωᵢ ∈ {B (başarı), Y (başarısızlık)}
```

**Örnek:** ω = (B, Y, B, B, Y) → 5 denemede 3 başarı

---

### Rastgele Değişken X(ω)

```
X(ω) = ω içindeki toplam başarı sayısı
```

**Örnek:** X( (B, Y, B, B, Y) ) = 3

---

## 2. PMF (Olasılık Kütle Fonksiyonu)

### Formül

Eğer X ~ Bin(n, p) ise:

```
P(X = k) = C(n, k) · p^k · (1-p)^(n-k)
```

Burada:
- **C(n, k) = n! / (k! · (n-k)!)** → k başarı için kombinasyon sayısı
- **p^k** → k başarının olasılığı
- **(1-p)^(n-k)** → (n-k) başarısızlığın olasılığı
- **q = 1 - p** kolaylık için kullanılır

### Neden bu formül?

Herhangi bir ω için, k tane "B" ve (n-k) tane "Y" içeriyorsa:
```
P(ω) = p^k · (1-p)^(n-k)
```
Böyle ω sayısı C(n,k) kadardır. Bu tüm olasılıkların toplamı:
```
Σ P(X = k) = Σ C(n,k)·p^k·(1-p)^(n-k) = (p + (1-p))^n = 1^n = 1  ✓
```

---

## 3. Destek (Support)

```
Destek = { 0, 1, 2, ..., n }
```

X en az 0, en fazla n başarı alabilir.

---

## 4. PMF Grafikleri

### 4a. Sabit n = 20, farklı p değerleri

```
p = 0.2           p = 0.5           p = 0.8
 ▲                  ▲                  ▲
0.20|  ■           0.20|     ■        0.20|           ■
0.18|  ■ ■         0.18|    ■ ■       0.18|         ■ ■
0.16|  ■ ■ ■       0.16|   ■   ■      0.16|       ■   ■
0.12| ■  ■  ■      0.12|  ■     ■     0.12|      ■     ■
0.08| ■       ■    0.08| ■       ■    0.08|    ■         ■
0.04|■           ■ 0.04|■         ■   0.04| ■              ■
    +----------→      +----------→       +----------→
    0    5   10 20    0    5   10  20     0    10  15  20

    Tepe: k ≈ 4        Tepe: k = 10       Tepe: k ≈ 16
    (sola çarpık)      (simetrik)         (sağa çarpık)
```

**Gözlem:** p arttıkça dağılım sağa kayar.

---

### 4b. Sabit p = 0.4, farklı n değerleri

```
n = 5              n = 15             n = 30
 ▲                  ▲                  ▲
0.35|   ■          0.20|      ■       0.14|         ■
0.30|  ■ ■         0.18|     ■ ■      0.12|        ■ ■
0.25| ■   ■        0.16|    ■   ■     0.10|       ■   ■
0.15| ■     ■      0.10|   ■     ■    0.08|      ■     ■
0.05|■         ■   0.04|  ■       ■   0.04|     ■       ■
    +------→           +-----------→       +---------------→
    0  2  4  5         0  4   6   15       0   8  12      30

    Tepe: k = 2         Tepe: k = 6        Tepe: k = 12
```

**Gözlem:** n arttıkça dağılım yayılır ve normale benzemeye başlar.

---

## 5. CDF (Kümülatif Dağılım Fonksiyonu) Grafikleri

### CDF Formülü

```
F(k) = P(X ≤ k) = Σᵢ₌₀ᵏ C(n, i) · p^i · (1-p)^(n-i)
```

### 5a. Sabit n = 20, farklı p değerleri

```
F(k)
1.0 |                           ───────  p=0.8
    |                     ────          
    |               ────                
0.5 |─────                       p=0.5
    |     ─────                  p=0.2
    |          ─────
0.0 +─────────────────────────→
    0   4   8  10  14  16  20
```

- **p = 0.2:** Eğri erken (küçük k'larda) 1'e yaklaşır → çoğu başarı sol tarafta
- **p = 0.5:** Simetrik S-eğrisi, k=10'da F(k)≈0.5
- **p = 0.8:** Eğri geç (büyük k'larda) 1'e ulaşır → başarılar sağda yoğunlaşır

### 5b. Sabit p = 0.4, farklı n değerleri

```
F(k)
1.0 |           ─────────────── n=5
    |      ────────────────────────  n=15
    |   ──────────────────────────────── n=30
0.5 |
    |
0.0 +───────────────────────────────→
    0   5   10   15   20   25   30
```

- n büyüdükçe CDF daha yavaş yükselir (değerler daha geniş aralığa yayılır)
- S-eğrisi daha uzadıkça kademeli bir geçiş görülür

---

## 6. Şeklin Nasıl Değiştiği

### p Arttığında (sabit n)

| p değeri    | Tepe noktası (mod) | Şekil            |
|-------------|---------------------|------------------|
| p küçük     | Sol tarafta (küçük k) | Sağa çarpık (positive skew) |
| p = 0.5     | Ortada: k = n/2   | Simetrik         |
| p büyük     | Sağ tarafta (büyük k) | Sola çarpık (negative skew) |

**Kural:** Mod ≈ ⌊(n+1)p⌋ veya (np) civarında

**Kıyıcıllık (çarpıklık):**
```
Skewness = (1 - 2p) / √(np(1-p))
```
- p < 0.5 → pozitif çarpıklık (sağa eğimli)
- p = 0.5 → sıfır çarpıklık (simetrik)
- p > 0.5 → negatif çarpıklık (sola eğimli)

---

### n Arttığında (sabit p)

| n değeri    | Dağılımın görünümü                |
|-------------|----------------------------------|
| n küçük     | Ayrık, az sayıda çubuk, asimetrik olabilir |
| n orta      | Belirgin tepe, az çarpıklık       |
| n büyük     | Normal dağılıma benziyor (Merkezi Limit Teoremi) |

**Merkezi Limit Teoremi (CLT):** n → ∞ iken:
```
X ~ Bin(n,p)  →  yaklaşık  N(np, np(1-p))
```

**Ortalama ve Varyans:**
```
E[X] = np
Var(X) = np(1-p)
Std(X) = √(np(1-p))
```

n arttıkça standart sapma (spread) da artsa bile **göreli** yayılım (katsayı) azalır:
```
CV = Std(X)/E[X] = √((1-p)/(np)) → 0
```

---

## 7. Olasılık Hesapları

### Parametreler: X ~ Bin(10, 0.3)

Ortalama: E[X] = 10 × 0.3 = 3  
Varyans: Var(X) = 10 × 0.3 × 0.7 = 2.1

---

### 7a. P(X = k) — Nokta Olasılığı (PMF'den doğrudan)

**P(X = 4) = ?**

```
P(X = 4) = C(10, 4) · (0.3)⁴ · (0.7)⁶

C(10,4) = 10! / (4! · 6!) = 210

P(X = 4) = 210 · 0.0081 · 0.117649
         = 210 · 0.000952...
         ≈ 0.2001
```

---

### 7b. P(X ≤ k) — CDF Kullanımı

**P(X ≤ 3) = ?**

```
P(X ≤ 3) = P(X=0) + P(X=1) + P(X=2) + P(X=3)

P(X=0) = C(10,0)·(0.3)⁰·(0.7)¹⁰ = 1 · 1 · 0.028248 = 0.0282
P(X=1) = C(10,1)·(0.3)¹·(0.7)⁹  = 10 · 0.3 · 0.040354 = 0.1211
P(X=2) = C(10,2)·(0.3)²·(0.7)⁸  = 45 · 0.09 · 0.057648 = 0.2335
P(X=3) = C(10,3)·(0.3)³·(0.7)⁷  = 120 · 0.027 · 0.082354 = 0.2668

P(X ≤ 3) = 0.0282 + 0.1211 + 0.2335 + 0.2668 = 0.6496
```

---

### 7c. P(X ≥ k) — Tümleyenden CDF

**P(X ≥ 5) = ?**

```
P(X ≥ 5) = 1 - P(X ≤ 4)

P(X=4) ≈ 0.2001   (yukarıda hesaplandı)

P(X ≤ 4) = P(X ≤ 3) + P(X = 4)
           = 0.6496 + 0.2001
           = 0.8497

P(X ≥ 5) = 1 - 0.8497 = 0.1503
```

---

### 7d. P(a ≤ X ≤ b) — Aralık Olasılığı

**P(2 ≤ X ≤ 5) = ?**

```
P(2 ≤ X ≤ 5) = P(X ≤ 5) - P(X ≤ 1)

P(X=5) = C(10,5)·(0.3)⁵·(0.7)⁵ = 252 · 0.00243 · 0.16807 ≈ 0.1029

P(X ≤ 5) = P(X ≤ 4) + P(X=5)
           = 0.8497 + 0.1029
           = 0.9526

P(X ≤ 1) = P(X=0) + P(X=1)
           = 0.0282 + 0.1211
           = 0.1493

P(2 ≤ X ≤ 5) = 0.9526 - 0.1493 = 0.8033
```

---

### Özet Tablo: X ~ Bin(10, 0.3)

| Sorgu               | Formül                    | Sonuç   |
|---------------------|---------------------------|---------|
| P(X = 4)            | PMF direkt                | 0.2001  |
| P(X ≤ 3)            | F(3)                      | 0.6496  |
| P(X ≥ 5)            | 1 - F(4)                  | 0.1503  |
| P(2 ≤ X ≤ 5)        | F(5) - F(1)               | 0.8033  |

---

## 8. Pratik Uygulamalar

### 8a. Kalite Kontrol / Üretim

**Senaryo:** Bir fabrika, %5 hatalı ürün üretiyor. 100 ürün seçilirse, kaç tanesinin hatalı olma olasılığı araştırılıyor.

```
X ~ Bin(100, 0.05)
E[X] = 5,  Var(X) = 4.75

P(X ≤ 3) = ?   → "çok az hata" olasılığı
P(X ≥ 10) = ?  → "çok fazla hata" olasılığı (alarm eşiği)
```

---

### 8b. Tıp / Klinik Denemeler

**Senaryo:** Bir ilaç %70 etkinlikte. 20 hasta tedavi ediliyor.

```
X ~ Bin(20, 0.70)
E[X] = 14 hasta iyileşir

P(X ≥ 16) = ?   → beklenenden çok iyileşme
P(X ≤ 10) = ?   → tedavinin başarısız sayılma olasılığı
```

---

### 8c. Seçim Anketi / Anket Analizi

**Senaryo:** Seçmenin %45'i A partisini destekliyor. 200 kişilik anket.

```
X ~ Bin(200, 0.45)
E[X] = 90

P(X ≥ 100) ≈ ?   → rastgele örneklemde çoğunluk A'yı destekler mi?
```

---

### 8d. Finans / Risk Yönetimi

**Senaryo:** Her ay %15 ihtimalle kötü piyasa gününde kayıp olur. 12 aylık periyot.

```
X ~ Bin(12, 0.15)
P(X ≥ 3) = ?   → 3 veya daha fazla kayıp ayı olasılığı
```

---

### 8e. Spor / Turnuva İstatistikleri

**Senaryo:** Bir basketbolcu serbest atışlarda %80 isabetli. 10 atış yapıyor.

```
X ~ Bin(10, 0.80)
P(X = 10) = (0.8)¹⁰ ≈ 0.107   → mükemmel performans
P(X ≥ 8) = ?                    → iyi performans eşiği
```

---

## 9. Karşılaştırmalı Analiz: Aynı Grafik Üzerinde İki Seçim

### 9a. Sabit n, farklı p (n = 15)

```
k  | Bin(15,0.3)  | Bin(15,0.6)
---|-------------|-------------
0  | 0.0047      | 0.0000
1  | 0.0305      | 0.0005
2  | 0.0916      | 0.0022
3  | 0.1700      | 0.0063
4  | 0.2186      | 0.0127
5  | 0.2061      | 0.0186
6  | 0.1472      | 0.0268
7  | 0.0811      | 0.1771     ← Bin(15,0.6) tepe bölgesi
8  | 0.0348      | 0.2066
9  | 0.0116      | 0.2066
10 | 0.0030      | 0.1859
...
```

ASCII gösterimi:

```
P(X=k)
0.22 |■
0.20 |■                    ■ ■
0.18 |■ ■                ■     ■
0.16 |  ■              ■         ■
0.12 |    ■          ■             ■
0.08 |      ■      ■
0.04 |        ■ ■              ■     ■
0.00 +─────────────────────────────────→
     0  1  2  3  4  5  6  7  8  9  10  k

     ■ = Bin(15, 0.3)     (sol kümeli)
     ■ = Bin(15, 0.6)     (sağ kümeli)
```

---

### 9b. Sabit p = 0.5, farklı n

```
P(X=k) — normalleştirilmiş görünüm

n=10: tepe k=5, yayılım dar
n=30: tepe k=15, yayılım geniş ama daha basık

     Bin(10, 0.5)           Bin(30, 0.5)
0.25 |     ■              
0.20 |    ■ ■           
0.15 |   ■   ■         0.15 |         ■ ■ ■
0.10 |  ■     ■        0.10 |       ■       ■
0.05 | ■       ■       0.05 |     ■           ■
     +─────────→            +─────────────────→
     0  5  10              0   10   15   20  30
```

---

## 10. Özet ve Temel Formüller

| Kavram              | Formül / Değer                           |
|---------------------|------------------------------------------|
| PMF                 | P(X=k) = C(n,k) pᵏ (1-p)ⁿ⁻ᵏ            |
| Destek              | k ∈ {0, 1, 2, ..., n}                   |
| Beklenti (Ortalama) | E[X] = np                               |
| Varyans             | Var(X) = np(1-p)                         |
| Standart Sapma      | σ = √(np(1-p))                           |
| Çarpıklık           | (1-2p)/√(np(1-p))                        |
| Basıklık (Excess)   | (1-6p(1-p))/(np(1-p))                    |
| Mod                 | ⌊(n+1)p⌋ veya (np+p) civarında           |
| CDF                 | F(k) = Σᵢ₌₀ᵏ C(n,i)pⁱ(1-p)ⁿ⁻ⁱ           |
| Tümleyen CDF        | P(X≥k) = 1 - F(k-1)                     |
| Aralık olasılığı    | P(a≤X≤b) = F(b) - F(a-1)                |
| Bernoulli özel hal  | Bin(1, p) ≡ Bernoulli(p)                 |
| CLT yaklaşımı       | Büyük n için: X ≈ N(np, np(1-p))         |

---

## Ekler: Manuel Hesap Yardımcısı

### Kombinasyon Tablosu: C(n, k) için küçük değerler

```
n\k  0   1   2    3    4    5    6    7    8    9   10
 0 [ 1 ]
 1 [ 1   1 ]
 2 [ 1   2   1 ]
 3 [ 1   3   3   1 ]
 4 [ 1   4   6   4   1 ]
 5 [ 1   5  10  10   5   1 ]
 6 [ 1   6  15  20  15   6   1 ]
 7 [ 1   7  21  35  35  21   7   1 ]
 8 [ 1   8  28  56  70  56  28   8   1 ]
 9 [ 1   9  36  84 126 126  84  36   9   1 ]
10 [ 1  10  45 120 210 252 210 120  45  10   1 ]
```

### Güç Tablosu: pᵏ için p = 0.3

```
k=0: 1.0000
k=1: 0.3000
k=2: 0.0900
k=3: 0.0270
k=4: 0.0081
k=5: 0.0024
```

### Güç Tablosu: (1-p)^k için p = 0.3 → q = 0.7

```
k=0: 1.0000
k=1: 0.7000
k=2: 0.4900
k=3: 0.3430
k=4: 0.2401
k=5: 0.1681
k=6: 0.1176
k=7: 0.0824
k=8: 0.0576
k=9: 0.0404
k=10: 0.0282
```

---

*Kaynak: Olasılık Teorisi — Binom Dağılımı, Task 3*