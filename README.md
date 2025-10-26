# Animal-Population-Simulation
Predator-prey and reproduction simulation using Python (Zoo ecosystem model)



## 🇹🇷 🐾 Hayvan Popülasyonu Simülasyonu

Bu proje, **yırtıcı-av ilişkilerini** ve **hayvan popülasyonlarının zaman içindeki değişimini** modelleyen bir **Python simülasyonu**dur.  
Her hayvan türü (örneğin koyun, kurt, aslan, avcı) kendi hareket, üreme ve avlanma davranışlarına sahiptir.  
Simülasyon 1000 adım boyunca çalışır ve her 100 adımda mevcut popülasyon sayıları ekrana yazdırılır.

---

### 🎯 Amaç
- Doğadaki **ekolojik etkileşimleri (avlanma, üreme, yok olma)** algoritmik olarak modellemek  
- **Nesne Yönelimli Programlama (OOP)** yapısını uygulamak  
- Uzamsal (spatial) ilişkileri kullanarak yakınlık temelli karar mekanizmaları geliştirmek  

---

### ⚙️ Kullanılan Teknolojiler
- **Python 3.x**
- **NumPy** – rastgele hareket ve matematiksel işlemler  
- **SciPy (cKDTree)** – komşuluk ve mesafe hesaplamaları  
- **Random** – üreme ve cinsiyet belirleme  

---

### 🧠 Simülasyon Kuralları

#### 🔹 Alan Boyutu
500x500 birimlik kare alan içinde gerçekleşir.  

#### 🔹 Türler
- **Koyun, İnek, Tavuk, Horoz, Kurt, Aslan, Avcı**  
- Erkek (E) ve Dişi (D) cinsiyetleriyle başlatılır.  
- Avcı cinsiyetsizdir.  

#### 🔹 Avlanma Kuralları
| Yırtıcı | Avladığı Türler | Avlanma Mesafesi |
|----------|------------------|------------------|
| Kurt | Koyun, Tavuk, Horoz | 4 |
| Aslan | İnek, Koyun | 5 |
| Avcı | Koyun, İnek, Tavuk, Kurt, Horoz, Aslan | 8 |

#### 🔹 Üreme Kuralları
- Aynı türden erkek ve dişi bireyler **3 birim** mesafede buluşursa yavrular doğar.  
- Yeni bireylerin cinsiyeti rastgele belirlenir.

---

### 📈 Simülasyon Akışı
1. Hayvanlar rastgele hareket eder.  
2. Yırtıcılar yakınındaki uygun türleri avlar.  
3. Hayvanlar yakın mesafedeki karşı cinsleriyle ürer.  
4. Her 100 adımda popülasyon sayısı yazdırılır.  
5. 1000 adım sonunda tür bazlı toplam sayım yapılır.  

---

### 🖥️ Örnek Çıktı
Adım: {'koyun': 30, 'inek': 10, 'tavuk': 10, 'horoz': 10, 'kurt': 10, 'aslan': 8, 'avci': 1}

Adım: {'koyun': 41, 'inek': 11, 'tavuk': 16, 'horoz': 9, 'kurt': 10, 'aslan': 8, 'avci': 1}
...
1000 adım sonrası hayvan sayısı:
koyun: 52
inek: 9
tavuk: 21
horoz: 7
kurt: 8
aslan: 6
avci: 1
...


---

### ▶️ Çalıştırma
```bash
# Gerekli kütüphaneleri yükle
pip install numpy scipy

# Kodu çalıştır
python animal_population_simulation.py
```
---

### 💡 Geliştirme Önerileri

Zamanla popülasyon değişimini matplotlib grafikleriyle görselleştir.

Tür sayılarının çizgi grafiğini oluştur.

Simülasyonu pygame veya tkinter ile görsel arayüze dönüştür.



## 🇬🇧 🐾 Animal Population Simulation

This project is a **Python-based predator-prey simulation** that models how animal populations change over time.  
Each species (e.g., sheep, wolf, lion, hunter) has its own movement, reproduction, and hunting behavior.  
The simulation runs for 1000 steps and prints the population counts every 100 steps.

---

### 🎯 Purpose
- To model **ecological interactions** such as hunting, reproduction, and extinction algorithmically  
- To apply **Object-Oriented Programming (OOP)** principles  
- To use **spatial reasoning** for proximity-based decision making  

---

### ⚙️ Technologies Used
- **Python 3.x**
- **NumPy** – random movement and mathematical operations  
- **SciPy (cKDTree)** – proximity and distance calculations  
- **Random** – reproduction and gender assignment  

---

### 🧠 Simulation Rules

#### 🔹 Area
The simulation takes place in a 500x500 unit square environment.  

#### 🔹 Species
- **Sheep, Cow, Chicken, Rooster, Wolf, Lion, Hunter**  
- Males (M) and females (F) are initialized.  
- The hunter has no gender.  

#### 🔹 Predation Rules
| Predator | Prey | Hunting Range |
|-----------|------|----------------|
| Wolf | Sheep, Chicken, Rooster | 4 |
| Lion | Cow, Sheep | 5 |
| Hunter | Sheep, Cow, Chicken, Wolf, Rooster, Lion | 8 |

#### 🔹 Reproduction Rules
- Males and females of the same species reproduce when they meet within **3 units** of distance.  
- The offspring’s gender is assigned randomly.

---

### 📈 Simulation Flow
1. Animals move randomly.  
2. Predators hunt nearby prey.  
3. Animals reproduce based on proximity and gender.  
4. Population counts are printed every 100 steps.  
5. After 1000 steps, the final population of each species is displayed.  

---

### 🖥️ Example Output
Step: {'sheep': 30, 'cow': 10, 'chicken': 10, 'rooster': 10, 'wolf': 10, 'lion': 8, 'hunter': 1}

Step: {'sheep': 41, 'cow': 11, 'chicken': 16, 'rooster': 9, 'wolf': 10, 'lion': 8, 'hunter': 1}
...
After 1000 steps:
sheep: 52
cow: 9
chicken: 21
rooster: 7
wolf: 8
lion: 6
hunter: 1


---

### ▶️ Run Instructions
```bash
# Install required libraries
pip install numpy scipy

# Run the code
python animal_population_simulation.py
```
---

### 💡 Future Improvements

Visualize population changes over time using matplotlib.

Create line charts showing the count of each species over time.

Add an interactive GUI using pygame or tkinter for visualization.

