# strukturdata-Q1-intancahyanti-KlsA
# Jawaban Struktur Data (Array & Linked List)


## 1. Karakteristik Memori dan Akses Data
Operasi akses elemen pada **Array** dapat dilakukan dalam waktu konstan **O(1)** karena array disimpan pada **memori yang bersifat kontinu (contiguous memory allocation)**. Setiap elemen memiliki ukuran yang tetap, sehingga alamat elemen ke-i dapat dihitung secara langsung menggunakan rumus:
> alamat(i) = alamat_awal + (i × ukuran_elemen)
Hal ini memungkinkan **random access**, yaitu akses langsung ke elemen tanpa perlu melakukan penelusuran.
Sebaliknya, pada **Singly Linked List**, elemen disimpan di **memori non-kontinu (tersebar)**. Setiap node hanya memiliki pointer ke node berikutnya, sehingga untuk mengakses elemen ke-i harus dilakukan traversal mulai dari head hingga posisi yang dituju.
Akibatnya, kompleksitas waktu akses adalah:
> O(n)
karena bersifat **sequential access**.

## 2. Analisis Efisiensi Operasi Insert dan Delete
**Linked List lebih unggul dibanding Array** dalam operasi penyisipan (insertion) dan penghapusan (deletion) pada kondisi tertentu, yaitu ketika operasi sering dilakukan di awal atau di tengah struktur data.
### Perbandingan:
**Array:**
- Insert/Delete di tengah atau awal memerlukan pergeseran elemen (shifting)
- Kompleksitas waktu: **O(n)**
**Linked List:**
- Setelah node posisi ditemukan, hanya perlu perubahan pointer
- Kompleksitas:
  - Insert: O(1)
  - Delete: O(1)
Namun perlu dicatat bahwa pencarian posisi tetap membutuhkan waktu **O(n)**.
### Kesimpulan:
Linked List lebih efisien ketika:
- Data bersifat dinamis
- Sering terjadi insert/delete
- Tidak membutuhkan akses indeks langsung
---

## 3. Konsep Doubly Linked List
**Doubly Linked List** adalah struktur data yang setiap node-nya terdiri dari tiga bagian:
- data
- pointer ke node berikutnya (next)
- pointer ke node sebelumnya (prev)
Representasi:
### Dampak keberadaan pointer tambahan:
#### 1. Penggunaan Memori
- Lebih besar dibanding Singly Linked List
- Karena setiap node menyimpan satu pointer tambahan (prev)
#### 2. Fleksibilitas
- Mendukung **traversal dua arah (bidirectional traversal)**
- Mempermudah operasi delete karena node sebelumnya dapat diakses langsung
### Kesimpulan:
Doubly Linked List memberikan fleksibilitas lebih tinggi dengan biaya tambahan memori.
---


## 4. Mekanisme Circular Linked List
**Circular Linked List** adalah variasi linked list di mana node terakhir tidak menunjuk ke NULL, melainkan kembali ke node pertama (head), sehingga membentuk struktur melingkar.
### Perbedaan dengan Linked List biasa:
- Linked List biasa: node terakhir → NULL
- Circular Linked List: node terakhir → head
### Karakteristik:
- Tidak memiliki node akhir (NULL)
- Dapat di-traversal secara siklik
- Harus memiliki kondisi berhenti untuk menghindari infinite loop
### Contoh Use Case:
**Round Robin CPU Scheduling**
Alasan:
- Setiap proses mendapatkan giliran eksekusi secara bergantian
- Setelah proses terakhir, kembali ke proses pertama
- Cocok untuk sistem yang bersifat berulang (cyclic process)
---

## 5. Array Dinamis (Python List)
Python `list` diimplementasikan sebagai **dynamic array** yang memiliki kapasitas internal (allocated capacity) lebih besar dari jumlah elemen saat ini.
### Mekanisme saat append:
#### Kondisi 1: Kapasitas masih cukup
- Elemen langsung ditambahkan
- Kompleksitas: **O(1)**
#### Kondisi 2: Kapasitas penuh
1. Dialokasikan array baru dengan ukuran lebih besar (growth factor)
2. Semua elemen lama disalin ke array baru
3. Array lama dihapus (garbage collected)
4. Elemen baru ditambahkan
---
### Kesimpulan:
Strategi dynamic resizing digunakan agar operasi append tetap efisien secara rata-rata meskipun sesekali terjadi reallocation yang mahal.
