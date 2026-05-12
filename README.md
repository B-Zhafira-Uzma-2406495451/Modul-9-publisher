# REFLEKSI MODUL 9
## How much data your publisher program will send to the message broker in one run?
program publisher akan mengirimkan total 5 event atau pesan ke message broker dalam satu kali eksekusi cargo run. Pesan
-pesan tersebut merepresentasikan pembuatan pengguna (User Created Event) dengan ID yang berbeda-beda, yaitu dari
user_id: "1" hingga user_id: "5".

## The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Penggunaan URL yang sama pada kedua program berarti publisher dan subscriber terhubung ke instance server RabbitMQ atau
message broker yang sama. Dalam sistem Event-Driven Architecture, URL ini berfungsi sebagai alamat perantara karena
keduanya terhubung ke alamat dan port yang sama yaitu localhost:5672. Publisher dapat mengirimkan pesan ke queue
tertentu dan subscriber dapat mendengarkan serta memproses pesan dari antrean tersebut pada broker yang sama.

## Monitoring Chart
![Monitoring chart based on publisher](image1.png)
Foto di atas menunjukkan dashboard dari RabbitMQ ketika kita login dengan user guest untuk modul tutorial ini

## Running Cargo on Both Publisher and Subscriber
![cargo run on subscriber](image2.png)
Foto di atas menunjukkan terminal subscriber yang berhasil menangkap kelima pesan yang dikirim oleh publisher.
Sesuai instruksi pada modul, teks pada output telah diubah menjadi "In Uzma's Computer [129500004y]" sebagai identitas
pengenal. Setiap kali pesan sampai di antrean "user_created", subscriber yang sedang dalam kondisi listening akan
langsung mengambil dan menampilkan isi pesan tersebut di konsol.

![cargo run on publisher](image3.png)
Foto di atas menunjukkan terminal publisher setelah menjalankan perintah cargo run. Saat dijalankan, program publisher
secara otomatis membuat dan mengirimkan 5 buah event (UserCreatedEventMessage) ke message broker RabbitMQ.  Setiap pesan
berisi data berupa user_id (1 sampai 5) dan user_name yang menyertakan identitas NPM. Publisher hanya bertugas
mengirimkan data ke antrean (queue) tanpa perlu tahu kapan atau siapa yang akan memprosesnya.