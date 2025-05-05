# Refleksi

Nama: Muhammad Zaid Ats Tsabit <br>
NPM: 2306224410 <br>
Kelas: Advprog-B
<hr>

1. What is amqp? <br>
AMQP (Advanced Message Queuing Protocol) merupakan protokol komunikasi terbuka yang digunakan untuk message-oriented middleware. AMQP ini memungkinkan aplikasi saling bertukar pesan melalui message broker seperti RabbitMQ secara baik, asynchronous, dan terstruktur. Selain itu, protokol ini mendukung fitur seperti message queue, routing, delivery guarantee, dan security.

2. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?

- `guest` (pertama): **username** yang digunakan untuk login ke broker (contohnya RabbitMQ).
- `guest` (kedua): **password** yang digunakan bersama username untuk autentikasi.
- `localhost`: alamat server, contohnya tempat RabbitMQ dijalankan. Namun, dalam hal ini, lokal.
- `5672`: adalah **port default** dari protokol AMQP (digunakan oleh Broker untuk menerima koneksi AMQP).

## Simulation slow subscriber
![slow](/image/slow.jpeg)
Disini saya sudah menambahkan delay pada main Publisher sehingga message yang dikirimkan tidak sekaligus, melainkan satu persatu dijeda oleh delay. Lalu, saya menjalankan cargo run pada publisher sebanyak 3 kali, terlihat pada Queued messages cukup tinggi disebabkan pesan yang menumpuk saat menjalankan cargo run 3 kali sekaligus. Pada modul terlihat Queued messagesnya mencapai 20, hal ini kemungkinan menjalankan cargo run secara sekaligus sebanyak 4 kali sehingga messages yang menumpuknya sebanyak 20 message, 1 kali run ada 5 message.

## Running at least three subscribers
![threesubs](/image/threesubscriber.jpeg)
Pada test ini, saya mencoba untuk menjalankan tiga subscriber secara bersamaan, dengan cara menjalankan perintah cargo run pada publisher sebanyak 4 kali. Setiap kali publisher dijalankan, publisher mengirimkan 5 event message ke RabbitMQ, yang totalnya menghasilkan 20 message yang dikirim ke broker.

Namun, yang menarik dari percobaan ini adalah tidak terjadi message queue yang terlihat pada RabbitMQ. Ini berarti bahwa setiap message yang dikirim oleh publisher langsung diterima dan diproses oleh ketiga subscriber tersebut tanpa ada backlog atau antrian message yang tertinggal di broker. Hal ini menunjukkan bahwa RabbitMQ berhasil menyalurkan message secara efisien ke ketiga subscriber yang aktif, memungkinkan mereka untuk memproses message secara real-time.