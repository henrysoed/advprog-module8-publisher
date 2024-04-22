# Understanding publisher and message broker
a. How many data your publisher program will send to the message broker in onerun?

Program publisher akan mengirimkan 5 data ke broker pesan dalam satu kali program publisher dijalankan. Setiap pesan akan berisi informasi tentang pembuatan pengguna (`UserCreatedEventMessage`), termasuk ID pengguna (`user_id`) dan nama pengguna(`user_name`). Berikut adalah detail pesan yang akan dikirimkan:

1. User ID: "1", Nama Pengguna: "2206827762-Amir"
2. User ID: "2", Nama Pengguna: "2206827762-Budi"
3. User ID: "3", Nama Pengguna: "2206827762-Cica"
4. User ID: "4", Nama Pengguna: "2206827762-Dira"
5. User ID: "5", Nama Pengguna: "2206827762-Emir"

b. The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?

Makna dari amqp://guest:guest@localhost:5672 dalam program publisher yang sama dengan dalam program subscriber dalam arsitektur AMQP adalah bahwa keduanya telah dikonfigurasi untuk terhubung ke broker pesan AMQP yang identik, yaitu RabbitMQ, yang di-hosting di mesin lokal. Publisher bertanggung jawab mengirim pesan ke queue di RabbitMQ, sementara subscriber akan menyiapkan listener untuk menerima atau mengambil pesan dari queue tersebut.

Hal ini menunjukkan bahwa keduanya berinteraksi melalui RabbitMQ sebagai titik koordinasi pusat, di mana publisher mengirim pesan dan subscriber menunggu serta memproses pesan yang diterima. Karena itu, penting bagi keduanya untuk terhubung ke broker yang sama agar komunikasi ini dapat berjalan dengan efektif.

Lampiran Running RabbitMQ
![alt text](images/image1.png)


Screen show consoles after running publisher multiple times
![alt text](images/image.png)