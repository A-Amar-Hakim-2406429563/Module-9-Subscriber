## a. What is amqp?
AMQP itu adalah singkatan dari Advanced Message Queuing Protocol.

Itu adalah protokol komunikasi yg dipakai utk mengirim dan menerima pesan lewat message broker, seperti RabbitMQ. Jadi, amqp dipakai supaya aplikasi publisher dan subscriber bisa saling bertukar pesan secara terstruktur dan asynchronous.

## b. What does it mean? `guest:guest@localhost:5672`, what is the first guest, and what is the second guest, and what is localhost:5672 is for?
Bagian itu adalah connection string utk menghubungkan aplikasi ke RabbitMQ.

Artinya:
- guest yg pertama = username
- guest yg kedua = password
- localhost = alamat server RabbitMQ yg dijalankan di komputer lokal
- 5672 = port default AMQP yg dipakai RabbitMQ

Jadi format lengkapnya dipakai utk login ke RabbitMQ lokal dengan username guest dan password guest lewat port 5672.

# Simulation slow subscriber
![alt text](slow_subscriber.png)
## c. Why is the total queue number like that?
Karena angka total queue itu ngikutin kondisi RabbitMQ yg lagi jalan pas itu. Jadi kalau queue atau message yg masih antri banyak, angkanya bakal naik. Kalau subscriber jalan terus dan message langsung diproses, totalnya bisa kecil atau bahkan 0.

Di laptopku, angkanya beda sama contoh di modul karena aku jalanin ulang service nya sendiri dan queue/message yg tersisa juga beda. Jadi intinya memang normal kalau hasilnya gak persis sama, yg penting RabbitMQ nya konek dan message bisa masuk lalu diproses.