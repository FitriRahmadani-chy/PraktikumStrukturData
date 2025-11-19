IMPLEMENTASI STACK DAN QUEUE DI PYTHON

STACK

Program berikut mendemonstrasikan cara kerja stack (tumpukan) menggunakan list di Python. Struktur data stack mengikuti prinsip LIFO (Last In, First Out) elemen terakhir yang ditambahkan akan menjadi elemen pertama yang diambil.

KODE PROGRAM MENGGUNAKAN STACK:

# Stack and stack operation
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)

# Pop
element = stack.pop()
print("Pop: ", element)

# Peek 
topElement = stack[-1]
print("Peek: ", topElement)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)

# Size
print("Size :", len(stack))
PENJELASANNYA:

Membuat Stack Pertama, kita buat sebuah list kosong yang akan bertindak sebagai stack:
stack = []
Menambah Data (Push) Elemen dimasukkan ke stack menggunakan metode append():
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)
Setelah bagian ini, kondisi stack tampak seperti berikut:

Stack:  ['A', 'B', 'C']
Menghapus Elemen (Pop) Untuk mengeluarkan elemen paling atas dari stack:
element = stack.pop()
print("Pop: ", element)
Hasilnya adalah:

Pop:  C
Elemen 'C' keluar terlebih dahulu karena dia yang terakhir masuk.

Melihat Elemen Teratas (Peek) Untuk mengetahui elemen paling atas tanpa menghapusnya:
topElement = stack[-1]
print("Peek: ", topElement)
Output:

Peek:  B
Mengecek Apakah Stack Kosong Cek apakah masih ada elemen dalam stack:
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)
Output:

isEmpty:  False
Ini menunjukkan bahwa stack tidak kosong.

Menghitung Banyaknya Elemen Gunakan len() untuk mengetahui jumlah elemen yang tersisa:
print("Size :", len(stack))
Output:

Size : 2
HASIL EKSEKUSINYA:

Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size : 2
KESIMPULAN: Struktur data stack dapat dengan mudah dibuat di Python menggunakan list. Stack bekerja dengan prinsip LIFO (Last In, First Out), di mana elemen yang terakhir ditambahkan akan menjadi yang pertama keluar. Operasi utama dalam stack antara lain:

Push dengan append() untuk menambah elemen.
Pop dengan pop() untuk menghapus elemen paling atas.
Peek dengan stack[-1] untuk melihat elemen teratas tanpa mengeluarkannya.
Mengecek apakah stack kosong melalui not bool(stack).
Menghitung jumlah elemen menggunakan len(stack).
Struktur ini berguna dalam banyak skenario, seperti sistem undo/redo, navigasi halaman web, dan manajemen memori saat pemanggilan fungsi.

QUEUE
Program ini menjelaskan cara membuat dan mengoperasikan queue (antrian) di Python menggunakan list. Queue adalah struktur data dengan prinsip FIFO (First In, First Out) artinya elemen yang pertama masuk akan diproses lebih dulu.

KODE PROGRAM MENGGUNAKAN QUEUE:

#Creating queue and Queue Operations

queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
PENJELASAN:

Membuat Queue Program memulai dengan membuat sebuah antrian kosong menggunakan list:
queue = []
Menambah Elemen (Enqueue) Kita tambahkan elemen ke bagian belakang antrian menggunakan append():
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)
Setelah bagian ini, antrian berisi:

Queue:  ['A', 'B', 'C']
Menghapus Elemen Pertama (Dequeue) Untuk mengeluarkan elemen terdepan, kita gunakan pop(0):
element = queue.pop(0)
print("Dequeue: ", element)
Output:

Dequeue:  A
Elemen 'A' keluar karena dia yang pertama masuk.

Melihat Elemen Terdepan (Peek) Untuk melihat elemen yang ada di depan antrian tanpa menghapusnya:
frontElement = queue[0]
print("Peek: ", frontElement)
Output:

Peek:  B
Mengecek Apakah Queue Kosong Untuk mengetahui apakah antrian masih ada isi:
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)
Output:

isEmpty:  False
Menghitung Jumlah Data Gunakan len(queue) untuk mengetahui berapa banyak elemen yang masih ada di antrian:
print("Size: ", len(queue))
Output:

Size:  2
HASIL EKSEKUSINYA:

Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
KESIMPULAN:

Program ini menunjukkan bahwa struktur data queue di Python bisa dibuat dengan memanfaatkan list. Queue bekerja berdasarkan prinsip FIFO (First In, First Out), yaitu data yang pertama masuk akan diproses terlebih dahulu.

Operasi penting yang ditunjukkan antara lain:

append() untuk menambahkan elemen ke dalam antrian (enqueue),
pop(0) untuk menghapus elemen paling depan (dequeue),
queue[0] untuk melihat elemen terdepan tanpa menghapusnya (peek),
not bool(queue) untuk mengecek apakah antrian kosong,
dan len(queue) untuk menghitung jumlah elemen yang masih ada.
Struktur ini sangat berguna untuk model antrian seperti antrean pelanggan, manajemen job di sistem, atau skenario yang memerlukan pemrosesan berurutan.
