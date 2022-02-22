
# Python - Mengecek Stok Barang

## Menghitung Jumlah Produk Per Merek
 - 
 - A
 
#### Perintah untuk Menghitung Jumlah Produk Per Merek

```http
import pandas as pd
from pandas import ExcelFile

# lokasi file 
file = "E:\smartphone.xls"
# baca data excel pada sheet "Sheet1"
dataSheet1 = pd.read_excel(file, sheet_name="Sheet1")

# inisialisasi awal
sumXiaomi = 0
sumSamsung = 0
sumOppo = 0
sumRealme = 0
sumVivo = 0
sumHuawei = 0
#gabolehhh ada data kosong atau NaN/Null pada kolom/field yg ada di excel/file !!!!!!!!!!!!!!!!!!!
#baca data hanya pada kolom nama produk
for data in dataSheet1["nama produk"]:
    if data[:6] == "Xiaomi": #membaca 6 digit digit ke 1-6
        sumXiaomi += 1 #counter bertambah
    if data[:4] == "Oppo": #membaca 4 digit digit ke 1-4
        sumOppo += 1 #counter bertambah
    if data[:6] == "Realme": #membaca 6 digit digit ke 1-6
        sumRealme += 1 #counter bertambah
    if data[:4] == "Vivo": #membaca 4 digit digit ke 1-4
        sumVivo += 1 #counter bertambah
    if data[:6] == "Huawei": #membaca 6 digit digit ke 1-6
        sumHuawei += 1 #counter bertambah
    elif data[:7] == "Samsung": #membaca 7 digit ke 1-7
        sumSamsung += 1 #counter bertambah
# # untuk tampilan output
print("Jumlah produk Xiaomi  :", sumXiaomi)
print("Jumlah produk Oppo    :", sumOppo)
print("Jumlah produk Realme  :", sumRealme)
print("Jumlah produk Vivo    :", sumVivo)
print("Jumlah produk Huawei  :", sumHuawei)
print("Jumlah produk Samsung :", sumSamsung)
```
![kasus 1](https://user-images.githubusercontent.com/86678205/155153537-b91fdfcf-591e-4a1a-9a48-672d9274a330.PNG)

## Mencari Jumlah Produk Per Merek Per Kategori
 - t

#### Perintah untuk Mencari Jumlah Produk Per Merek Per Kategori (Tampilan Seluruh Merek)

```http
import pandas as pd
from pandas import ExcelFile

# lokasi file
file = "e:\smartphone.xls"
# baca data excel pada sheet "Sheet1"
dataSheet1 = pd.read_excel(file, sheet_name="Sheet1")

# list seluruh Kategori
listKategori = ["Mi", "PO", "Re", "Galaxy-", "GalaxyZ", "Ren", "Fin", "A54", "A74", "Y", "X", "V", "Nova", "Mate", "C2", "8-", "GT"]
# inisialisasi awal per produk
sumXiaomi = {}
sumSamsung = {}
sumOppo = {}
sumVivo = {}
sumHuawei = {}
sumRealme = {}
for kat in listKategori:
    sumXiaomi[kat] = 0
    sumSamsung[kat] = 0
    sumOppo[kat] = 0
    sumVivo[kat] = 0
    sumHuawei[kat] = 0
    sumRealme[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[7:9] #membaca mulai digit 7 sampai digit 9
    if data[:6] == "Xiaomi": #membaca 6 digit, digit ke 1-6
        sumXiaomi[kat] += 1 #counter bertambah
    kat = data[8:15] #membaca mulai digit 8 sampai digit 15
    if data[:7] == "Samsung": #membaca 7 digit, digit ke 1-7
        sumSamsung[kat] += 1 #counter bertambah
    kat = data[5:8] #membaca mulai digit 5 sampai digit 8
    if data[:4] == "Oppo": #membaca 4 digit, digit ke 1-4 
        sumOppo[kat] += 1 #counter bertambah
    kat = data[5:6] #membaca mulai digit 5 sampai digit 6
    if data[:4] == "Vivo": #membaca 4 digit, digit ke 1-4 
        sumVivo[kat] += 1 #counter bertambah
    kat = data[7:11] #membaca mulai digit 7 sampai digit 11
    if data[:6] == "Huawei": #membaca 6 digit, digit ke 1-6
        sumHuawei[kat] += 1 #counter bertambah
    kat = data[7:9] #membaca mulai digit 7 sampai digit 9
    if data[:6] == "Realme": #membaca 6 digit, digit ke 1-6
        sumRealme[kat] += 1 #counter bertambah

# untuk tampilan output
print("Kategori/Series".ljust(30), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------")
print("Xiaomi".ljust(30), end="")
for kat in listKategori:
    print(str(sumXiaomi[kat]).rjust(10), end="")

print()
print("Samsung".ljust(30), end="")
for kat in listKategori:
    print(str(sumSamsung[kat]).rjust(10), end="")
    
print()
print("Oppo".ljust(30), end="")
for kat in listKategori:
    print(str(sumOppo[kat]).rjust(10), end="")
    
print()
print("Vivo".ljust(30), end="")
for kat in listKategori:
    print(str(sumVivo[kat]).rjust(10), end="")
    
print()
print("Huawei".ljust(30), end="")
for kat in listKategori:
    print(str(sumHuawei[kat]).rjust(10), end="")
    
print()
print("Realme".ljust(30), end="")
for kat in listKategori:
    print(str(sumRealme[kat]).rjust(10), end="")
```
![1](https://user-images.githubusercontent.com/86678205/155153665-acd8cb7a-4779-44f0-9b62-8fd7cd1c4c2d.PNG)
##
![2](https://user-images.githubusercontent.com/86678205/155153738-a3d831c6-0e89-4f19-bdc2-c692a886527b.PNG)

#### Perintah untuk Mencari Jumlah Produk Per Merek Per Kategori (Tampilan Per Merek)

```http
import pandas as pd
from pandas import ExcelFile

# lokasi file
file = "e:\smartphone.xls"
# baca data excel pada sheet "Sheet1"
dataSheet1 = pd.read_excel(file, sheet_name="Sheet1")

# list seluruh Kategori
listKategori = ["Galaxy-", "GalaxyZ"]
# inisialisasi awal per produk
sumSamsung = {}
for kat in listKategori:
    sumSamsung[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[8:15] #membaca mulai digit 8 sampai digit 15
    if data[:7] == "Samsung": #membaca 7 digit, digit ke 1-7
        sumSamsung[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(Galaxy|GalaxyZ)".ljust(35), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("------------------------------------------------------------")
print("Samsung".ljust(35), end="")
for kat in listKategori:
    print(str(sumSamsung[kat]).rjust(8), end="")

# list seluruh Kategori
listKategori = ["Mi", "PO", "Re"]
# inisialisasi awal per produk
sumXiaomi = {}
for kat in listKategori:
    sumXiaomi[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[7:9] #membaca mulai digit 7 sampai digit 9
    if data[:6] == "Xiaomi": #membaca 6 digit, digit ke 1-6
        sumXiaomi[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(Mi|POCO|Redmi)".ljust(40), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("-----------------------------------------------------------------------")
print("Xiaomi".ljust(40), end="")
for kat in listKategori:
    print(str(sumXiaomi[kat]).rjust(10), end="")

# list seluruh Kategori
listKategori = ["Ren", "Fin", "A54", "A74"]
# inisialisasi awal per produk
sumOppo = {}
for kat in listKategori:
    sumOppo[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[5:8] #membaca mulai digit 5 sampai digit 8
    if data[:4] == "Oppo": #membaca 4 digit, digit ke 1-4
        sumOppo[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(Reno|Find|A54|A74)".ljust(40), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("----------------------------------------------------------------------------------")
print("Oppo".ljust(40), end="")
for kat in listKategori:
    print(str(sumOppo[kat]).rjust(10), end="")

# list seluruh Kategori
listKategori = ["Y", "X", "V"]
# inisialisasi awal per produk
sumVivo = {}
for kat in listKategori:
    sumVivo[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[5:6] #membaca mulai digit 5 sampai digit 6
    if data[:4] == "Vivo": #membaca 4 digit, digit ke 1-4
        sumVivo[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(Y Series|X Series|V Series)".ljust(45), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("----------------------------------------------------------------------------------")
print("Vivo".ljust(45), end="")
for kat in listKategori:
    print(str(sumVivo[kat]).rjust(10), end="")

# list seluruh Kategori
listKategori = ["Nova", "Mate"]
# inisialisasi awal per produk
sumHuawei = {}
for kat in listKategori:
    sumHuawei[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[7:11] #membaca mulai digit 7 sampai digit 11
    if data[:6] == "Huawei": #membaca 6 digit, digit ke 1-6
        sumHuawei[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(Nova|Mate)".ljust(40), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("----------------------------------------------------------------------------------")
print("Huawei".ljust(40), end="")
for kat in listKategori:
    print(str(sumHuawei[kat]).rjust(10), end="")

# list seluruh Kategori
listKategori = ["C2", "8-", "GT"]
# inisialisasi awal per produk
sumRealme = {}
for kat in listKategori:
    sumRealme[kat] = 0

# pencacahan data kategori per produk 
for data in dataSheet1["nama produk"]:
    # ambil kategori dari data kolom nama_produk
    kat = data[7:9] #membaca mulai digit 7 sampai digit 9
    if data[:6] == "Realme": #membaca 6 digit, digit ke 1-6
        sumRealme[kat] += 1
        
# untuk tampilan output
print("Kategori/Series(C|8|GT)".ljust(40), end="")

for kat in listKategori:
    print(kat.rjust(10), end="")
print()
print("----------------------------------------------------------------------------------")
print("Realme".ljust(40), end="")
for kat in listKategori:
    print(str(sumRealme[kat]).rjust(10), end="")
```
![5](https://user-images.githubusercontent.com/86678205/155154071-28ca9113-287b-4e68-bbe0-78f20dc2cfb7.PNG)
##
![6](https://user-images.githubusercontent.com/86678205/155154118-877f2e40-2878-4d9f-8470-8305a83d44ea.PNG)
##
![7](https://user-images.githubusercontent.com/86678205/155154155-97d39964-8c6a-4107-8ba3-e40a6419f2e7.PNG)
##
![8](https://user-images.githubusercontent.com/86678205/155154192-c62f3e73-4022-4bde-9d42-b01f7cd199e9.PNG)
##
![9](https://user-images.githubusercontent.com/86678205/155154221-c5370a3c-93c5-4524-92f7-62669a976d19.PNG)
##
![10](https://user-images.githubusercontent.com/86678205/155154250-1b39a6f5-6a71-4467-be28-ac72643b81c6.PNG)

## Mencari Seluruh Kategori Apa Saja yang Ada
 - D
 - K
 - A

 #### Perintah untuk Mencari Seluruh Kategori Apa Saja yang Ada (tampilan mendatar)

```http
import pandas as pd
data = pd.read_csv("E:\dataset\smartphone.csv", ";")

sumKategori = {}
for x in data["kategori"]:
    if x in sumKategori.keys():
        sumKategori[x] += 1
    else:
        sumKategori[x] = 1

print(sumKategori)

```
![1](https://user-images.githubusercontent.com/86678205/155154293-a9661273-5444-49e6-8de2-910dd4f9dc4c.PNG)

#### Perintah untuk Mencari Seluruh Kategori Apa Saja yang Ada (tampilan kebawah)

```http
import pandas as pd
data = pd.read_csv("E:\dataset\smartphone.csv", ";")

sumKategori = {}
for x in data["kategori"]:
    if x in sumKategori.keys():
        sumKategori[x] += 1
    else:
        sumKategori[x] = 1

sumKategori
```
![2](https://user-images.githubusercontent.com/86678205/155154334-f39113d5-5359-4a28-a87c-c564b2af7712.PNG)

#### Perintah untuk menampilkan 5 data pertama hasil sorting (besar ke kecil)

```http
from operator import itemgetter

# men-sorting data kategori/series produk
# berdasarkan value/nilai secara descending (besar ke kecil)
sorting_data = sorted(sumKategori.items(), key=itemgetter(1), reverse=True)

# menampilkan 5 data pertama hasil sorting
for i in range(5):
    print(sorting_data[i])
```
![3](https://user-images.githubusercontent.com/86678205/155154360-92de9b3d-c5fd-43bd-b11c-cdd60c7027c4.PNG)
