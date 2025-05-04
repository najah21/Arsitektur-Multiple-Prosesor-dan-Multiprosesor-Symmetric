# Arsitektur-Multiple-Prosesor-dan-Multiprosesor-Symmetric

![Multiple Prosesor dan Multiprosesor Symmetric drawio (1)](https://github.com/user-attachments/assets/c30175fe-00bf-45af-bc9c-bc1c217e10b8)

### **1. Architecture Multiprocessor**
Pada sisi kiri gambar, arsitektur *Multiprocessor* digambarkan sebagai sistem dengan beberapa prosesor yang memiliki hierarki memori antara **L1 Cache**, **L2 Cache**, dan memori utama. Proses komunikasi antar prosesor dikelola menggunakan **System Bus/Interconnect** yang menghubungkan prosesor dengan memori utama.

#### **Karakteristik Utama**:
1. **L1 Cache dan L2 Cache**:
   - Setiap CPU memiliki **L1 Cache** (cache tingkat pertama) untuk akses cepat ke data yang sering digunakan.
   - **L2 Cache** berfungsi sebagai cache tingkat kedua yang mungkin berbagi data antara beberapa prosesor.

2. **System Controller**:
   - Bertindak sebagai pengatur komunikasi antara memori utama, I/O, dan prosesor.

3. **Independensi Prosesor**:
   - Setiap prosesor bekerja secara relatif independen dengan memori lokal (*local cache*), namun komunikasi tetap dikoordinasikan melalui **System Bus**.

#### **Kelebihan**:
- Skalabilitas yang baik untuk sistem terdistribusi.
- Cocok untuk aplikasi yang membutuhkan pemrosesan paralel.

---

### **2. Architecture Multiprocessor Symmetric (SMP)**
Pada sisi kanan gambar, arsitektur SMP ditunjukkan sebagai sistem dengan **System Bus** sebagai penghubung langsung antara semua prosesor dan memori utama. Dalam sistem ini, semua prosesor memiliki akses simetris terhadap memori bersama.

#### **Karakteristik Utama**:
1. **System Bus**:
   - Semua prosesor terhubung langsung ke memori dan perangkat I/O melalui **System Bus**, sehingga memungkinkan komunikasi yang cepat dan efisien.

2. **Cache Bersama**:
   - Data dari memori utama dapat di-*cache* untuk mempercepat akses oleh masing-masing prosesor.

3. **I/O Controller**:
   - Mengatur komunikasi antara perangkat input/output dengan prosesor.

4. **Akses Simetris**:
   - Semua prosesor memiliki akses yang sama terhadap memori utama dan perangkat I/O, sehingga tidak ada hierarki di antara prosesor.

#### **Kelebihan**:
- Kinerja tinggi untuk aplikasi yang membutuhkan sinkronisasi data (*shared memory*).
- Komunikasi antar prosesor lebih cepat dibandingkan dengan arsitektur *Multiprocessor* biasa.

---

### **Perbandingan Gambar Multiprocessor dan SMP**
| **Aspek**                   | **Multiprocessor**                     | **Multiprocessor Symmetric (SMP)**          |
|------------------------------|-----------------------------------------|---------------------------------------------|
| **Akses Memori**             | Menggunakan hierarki cache (L1, L2).   | Semua prosesor memiliki akses langsung ke memori utama. |
| **Komunikasi Antar Prosesor**| Melalui **System Controller**.         | Langsung melalui **System Bus**.            |
| **Hierarki Prosesor**        | Bisa ada hierarki (*master-slave*).    | Tidak ada hierarki, semua prosesor setara.  |
| **Efisiensi Komunikasi**     | Relatif lebih lambat.                  | Lebih cepat karena menggunakan memori bersama. |

---
