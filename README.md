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