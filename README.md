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