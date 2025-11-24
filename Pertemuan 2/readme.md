
**Penjelasan Kode: Linked List Sederhana di Python**

1. Class Node

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

Penjelasan:

* Setiap elemen dalam linked list disebut node.
* Node punya 2 bagian:

 * data : nilai yang disimpan.
 * next : pointer yang menunjuk ke node berikutnya.
 * Konstruktor menerima:

  * `data`: isi node.
  * `pointer`: alamat node berikutnya.



 **2. Class LinkedList**

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

**Penjelasan:**

* Linked list punya satu pointer utama yaitu **head**, penunjuk ke node pertama.
* Awalnya list kosong → `head = None`.


 **3. METHOD INSERT**

**3.1 insert_at_first**

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

 **Penjelasan:**

* Menambahkan data di **depan list**.
* Node baru akan menunjuk ke head lama.
* Head diganti menjadi node baru.

Urutan berubah menjadi:
**baru → sebelumnya**


**3.2 insert_at_last**

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        node = Node(data)
        node_sekarang.next = node
```

**Penjelasan:**

* Jika list kosong, elemen baru jadi head.
* Jika ada isinya:

  * Traverse (telusuri) sampai **node terakhir** (yang `next = None`).
  * Tambahkan node baru di ujung list.


 **3.3 insert_at(index, data)**

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

**Penjelasan:**

* Jika index tidak valid → tampilkan pesan.
* Jika index = 0 → gunakan insert_at_first.
* Untuk index lain:

  * Cari node yang letaknya sebelum index.
  * Node baru disisipkan di antara node tersebut.


**4. METHOD REMOVE**

**4.1 remove_first**

```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```

 **Penjelasan:**

* Menghapus elemen pertama.
* Head digeser ke node berikutnya.


**4.2 remove_last**

```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head

        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next

        node_sebelumnya.next = None
```

 **Penjelasan:**

* Jika list kosong → tidak bisa hapus.
* Jika hanya 1 node → head dihapus → list jadi kosong.
* Jika banyak node:

  * Telusuri sampai node terakhir.
  * Putuskan pointer node sebelumnya.
  * Node terakhir otomatis hilang.


 **4.3 remove_at(index)**

```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index tidak valid")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1

        node_sekarang.next = node_sekarang.next.next
```

**Penjelasan:**

* Jika index salah → pesan error.
* Index = 0 → hapus node pertama.
* Untuk index lain:

  * Telusuri sampai node sebelum index.
  * Skip pointer ke node setelah node yang akan dihapus.


 **5. print()**

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ""
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + " -> "
            node_sekarang = node_sekarang.next

        print(text_print)
```

**Penjelasan:**

* Menampilkan semua data dalam bentuk:

  ```
  mangga -> anggur -> ...
  ```
* Traversal dilakukan dari head sampai node terakhir.


 **6. length()**

```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan
```

**Penjelasan:**

* Menghitung jumlah node.
* Traverse dari head → akhir list.


**7. Bagian Program Utama**

```python
LL = LinkedList()
```

Membuat objek linked list.


**7.1 INSERT yang dilakukan**

```python
LL.insert_at_first("jeruk")     # jeruk
LL.insert_at_first("mangga")    # mangga -> jeruk
LL.insert_at_first("manggis")   # manggis -> mangga -> jeruk
LL.insert_at_last("apel")       # ... -> jeruk -> apel
LL.insert_at(2, "anggur")       # manggis -> mangga -> anggur -> jeruk -> apel
```


 **7.2 REMOVE yang dilakukan**

```python
LL.remove_first()   # hapus manggis
LL.remove_last()    # hapus apel
LL.remove_at(1)     # hapus index 1 (anggur)
```

**List akhir:**

```
mangga -> jeruk
```



 **7.3 PRINT**

```
mangga -> jeruk ->
```

**7.4 LENGTH**

```
2
```



**HASIL AKHIR OUTPUT**

```
mangga -> jeruk ->
2
```



