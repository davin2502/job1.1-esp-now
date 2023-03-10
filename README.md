Davin Marselon/4.31.20.1.07/TE-3B

# Job 1.1 ESP NOW

## Alat dan Bahan
1. ESP32 > 4
2. Arduino IDE (Terinstal ESP32)
3. Library DHT dan Adafruit unified sensor
4. Breadboard
5. Kabel Jumper
6. Resistor < 220Ω
7. Sensor DHT

## Instalasi ESP32
1. Buka Arduino IDE
   - Masuk ke Preferences
   - Isikan board url dengan link : https://dl.espressif.com/dl/package_esp32_index.json dan simpan
   - Buka Tools > Board > Boards Manager
   - Cari ESP32, by Espressif. Kemudian instal
   - Pilih flash mode DIO/QIU menyesuaikan
2. Jalankan program .ino
3. Jika terdapat error saat uploading, tekan dan tahan tombol Boot pada ESP32 saat upload, hingga Connecting selesai

## Instalasi DHT & Adafruit Libraries
1. Buka Arduino IDE
2. Buka Sketch > Include Library > Library Manager
3. Cari DHT sensor library by Adafruit, kemudian instal. Atau dapat melalui link DHT Library dan upload pada libraries di direktori projek. Rename direktori menjadi DHT_sensor_library.
4. Instal juga library Adafruit unified sensor by Adafruit. Atau dapat melalui link Adafruit Sensor dan upload pada libraries di direktori projek. Rename direktori menjadi Adafruit_Unified_Sensor.

## Percobaan A. MAC Address (MacScanning)
### Rangkaian & Instalasi
1. Siapkan ESP32 dan hubungkan ke Arduino IDE
2. Download dan jalankan kode dari source code sesuai project.

### Keluaran 
Mac akan keluar di serial monitor. Pastikan baud rate sama dengan kode.

<img src="https://camo.githubusercontent.com/5729ffe8a869f3f29c3c38cd30e6a19b44007cb4f6d9c71fb1f66b45871f7f04/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313034383935303636383835353039313330312f412e5f4d61632e706e67" width=600px>

## Percobaan B. One-Way Point-to-Point Communication (Simplex Point to Point)
### Rangkaian & Instalasi
1. Siapkan 2 ESP32 yang sudah diketahui Mac Address wifinya.

<img src="https://camo.githubusercontent.com/3087a187ce5a594d4db6b35212c404f04ef685db9550509a9a7c6e0d99f32ee5/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313034383935313930323039373932303039302f422e5f53696d706c65785f5054502e77656270" width=600px>

2. Download dan jalankan kode dari source code sesuai project.

### Keluaran

1. Pengirim
 
<img src="https://camo.githubusercontent.com/9e77a9e24019784108247b4d4d3d136e1ac613d8d3ace77f17140b1cbd92a760/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313034383936343932323936363534303330392f422e5f53696d706c65785f5054505f53656e6465722e706e67" width=600px>

2. Penerima 

<img src="https://camo.githubusercontent.com/8dd078242a41132e197a647ac9b7fdf87b482a45e694b96b70ee48928b292bf8/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313034383936343935353734393233323731302f422e5f53696d706c65785f5054505f52656365697665722e706e67" width=600px>

### Tugas B No. 8-11

<img src="https://camo.githubusercontent.com/dd3cee4074b9d579f6614e8e3171cd22e35eac828743e183122a8f31d527a5ca/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313034383937353537373831393931303136342f696d6167652e706e67" width=600px>

Percobaan dilakukan di dalam ruangan lab komputer (meja dan kursi) serta terdapat beberapa orang dan ESP32 lain pada ruangan yang sama. Jarak antar ESP adalah 1 meter, 2 meter, 3 meter, 4 meter, dan 5 meter pada ketinggian masing-masing yaitu ground level, 30cm, dan 1m diatas tanah secara LOS (Line of Sight) dan halangan berupa tangan dan buku.

Hasil yang didapatkan dari percobaan adalah 100% diterima dan 0% loss. Hal ini dikarenakan salah satu dari ESP yaitu ESP pengirim adalah seri ESP32U V4 yang memiliki antena eksternal dengan gain +3dB. Sehingga pada jarak 5 meter baik secara LOS maupun diberikan halangan, daya pancar antena sudah lebih dari cukup untuk mengcover keseluruhan area, sehingga penerima dengan mudah menerima sinyal tanpa kerusakan atau rugi-rugi berarti.

## Percobaan C. One-Way, One-to-Many Communication (Simplex Point to Multipoint)
### Rangkaian & Instalasi
1. Siapkan 3 atau lebih ESP32 yang sudah diketahui Mac Address wifinya.

<img src="https://camo.githubusercontent.com/e761413198128d8bbaaae1980d74304009868318135b64cbf1a2df5057a6159a/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313334393237323239393332333435322f432e5f53696d706c65785f50544d2e706e67" width=600px>

2. Download dan jalankan kode dari source code sesuai project.

### Keluaran
1. Pengirim

<img src="https://camo.githubusercontent.com/11dd41d2f58aec2c6173495a7653ecda3279d038eed8939f9e96bcada5eb5e53/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335313237343437393638313539362f432e5f53696d706c65785f50544d5f53656e6465722e706e67" width=600px>

2. Penerima

<img src="https://camo.githubusercontent.com/d3fc3bfcf52e4557b1b4e3ab248768b70143e1c50f3daa22afe8c280e1a812a5/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335313331313933393032363939342f432e5f53696d706c65785f50544d5f52656365697665722e706e67" width=600px>

Percobaan menggunakan 4 board ESP, satu sebagai master dan 3 sebagai slave. Board master akan melakukan broadcast yang pada prinsipnya (code) adalah mengirim data satu per satu ke ESP slaves. MAC dari slaves harus diidentifikasi pada master sebagai address tujuan dan membuat masing-masing peer sehingga master dapat mengirimkan data. Menggunakan fungsi data dan callback event yang sama, maka hasil pada serial monitor berupa data yang sama pada semua slaves.

### Tugas C No. 9
<img src="https://camo.githubusercontent.com/48135f636f0e68bb0c4dd0443d0dbaf62981e7eb0761655edc2994d86818f2e7/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335323233383532333639393333302f432e5f53696d706c65785f50544d5f54756761735f312e706e67" width=600px>

Percobaan menggunakan 3 board ESP, satu sebagai master dan 2 sebagai slave. Prinsip kerja yang dipakai adalah sama, akan tetapi board slave pada percobaan ini diputus salah satu. Sehingga hasil keluaranya menjadi sebagai berikut pada board master:

### Tugas C No. 10-11
<img src="https://camo.githubusercontent.com/7f0bf866f674a1f9518b8e25ad018fbe51019c07d6480935fc00aa246c533162/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335323736323332393335343238302f432e5f53696d706c65785f50544d5f54756761735f322e706e67" width=600px>

Percobaan hanya dapat menggunakan hingga 5 board saja karena keterbatasan ESP yang ada. Pada pengiriman 4 slaves tidak ada kendala sama sekali. Sedangkan menurut https://randomnerdtutorials.com/ ESP-NOW dapat berkomunikasi dengan peer terenkripsi hingga 10 ESP. Nb. Untuk menambah jumlah ESP dalam jaringan, maka selain menambah variabel mac juga perlu menambah peer untuk masing-masing slaves. Board slave menggunakan kode yang sama seperti sebelumnya.

### Tugas C (b)
1. Pengirim

<img src="https://camo.githubusercontent.com/5d7a880427c4d697a73bcd71e0f4745ce412be3e2c518249346283b27adb4726/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335343334383331373332373339302f432e5f53696d706c65785f50544d5f54756761735f33622e706e67" width=600px>

2. Penerima 1

<img src="https://camo.githubusercontent.com/23ab04e38e16bf53dbc84824ef2e9fa4f1b40b682fd6fb2d405749b65731b1ac/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335353234383233343631303737382f432e5f53696d706c65785f50544d5f54756761735f33625f536c6176655f312e706e67" width=600px>

3. Penerima 2

<img src="https://camo.githubusercontent.com/d6ca8dd2b3dd7fc441bc033b2286f0aa0dfe106364eea7af2fe7263e75d29f76/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335353234383532343032313736302f432e5f53696d706c65785f50544d5f54756761735f33625f536c6176655f322e6a706567" width=600px>

4. Penerima 3

<img src="https://camo.githubusercontent.com/543b7791f1dc7164a2b0b6fdf47415ea04d27629fca6e8ea2de228aff85252e2/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313335353234383731323735373234382f432e5f53696d706c65785f50544d5f54756761735f33625f536c6176655f332e706e67" width=600px>

Percobaan menggunakan 4 board ESP, satu sebagai master dan 3 sebagai slave. Masing-masing ESP dibuatkan struktur data dan pada fungsi looping dilakukan routing pada masing-masing struktur data yang dibuat. Sehingga data yang diterima antar slave tidaklah sama. Sedangkan untuk board slave menggunakan kode yang sama seperti sebelumnya.

## Percobaan D. One-Way, Many-to-One Communication (Simplex Multipoint to Point)
### Rangkaian & Instalasi
1. Siapkan 3 atau lebih ESP32 yang sudah diketahui Mac Address wifinya.

<img src="https://camo.githubusercontent.com/7928b0b596db8ff65d56f6340e0eb02b3b597e2df0e67af28947eddc0ce55dc7/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313337353330363334303034303830342f442e5f53696d706c65785f4d54502e706e67" width=600px>

2. Download dan jalankan kode dari source code sesuai project.

### Keluaran
1. Pengirim

<img src="https://camo.githubusercontent.com/efd872cd0255ef1488aae57a6a0fc5735752a40c42d152defea64f9f57ee6a8e/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313337353330363632353237333837362f442e5f53696d706c65785f4d54505f4d61737465722e706e67" width=600px>

2. Penerima

<img src="https://camo.githubusercontent.com/f359abfd9a858e68181fd5e27201aa7b03247bc5dbc73c24c16cb9b50abfb405/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313337353330363838393530323832322f442e5f53696d706c65785f4d54505f536c6176652e706e67" width=600px>

Percobaan menggunakan 3 board ESP, 2 sebagai slave dan 1 sebagai master. Prinsip kerja master sama seperti pada percobaan PTP maupun PTM. Perbedaanya ada pada kode dari ESP penerima yaitu struktur dibuat dalam bentuk array yang diisi masing-masing variabel dari struktur data. Kemudian untuk mempermudah ditambahkan event callback yang mengidentifikasi mac address pengirim yang akan ditampilkan bersama dengan data yang diterima.

## Percobaan E. One-Way, Many-to-One Communication (Duplex)
### Rangkaian & Instalasi
1. Siapkan 2 ESP32 yang sudah diketahui Mac Address wifinya.

<img src="https://camo.githubusercontent.com/1f27e0e85b6ec3e12716b1924238519e8823994cb69a609b7e548d8a006cecaa/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313338303331373435313230363735362f452e5f4475706c65782e706e67" width=600px>

2. Buat rangkaian sebagai berikut.

<img src="https://camo.githubusercontent.com/6a0c995ebd344805d6cca2179c2f6f5765119336a7ae77b3d103d033b0571e8f/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313432353532393339373531383337362f452e5f52616e676b6169616e5f4448542e706e67" width=600px>

3. Download dan jalankan kode dari source code sesuai project.
4. Pastikan library DHT dan adafruit sudah terinstal. Pastikan DHTTYPE sesuai dengan tipe sensor yang digunakan, contoh DHT11, DHT21, DHT22.

### Keluaran
<img src="https://camo.githubusercontent.com/dfc3e38684b08fecb6c5f74e3864234d6ae4123b004bfe0819d77c033a6f2905/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313338303331373132343034323737322f452e5f44485431312e706e67" width=600px>

Percobaan menggunakan 1 board ESP untuk membaca sensor DHT (pada percobaan digunakan DHT11).

### Tugas E No. 6-9
<img src="https://camo.githubusercontent.com/8790312aaec076e75f687ffa8ab8348152728eedf7ab0c806bc0bcbd0a4a2824/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f313034333436323531393333363939363839342f313035313338303530373735303935373039362f452e5f4475706c65785f54756761735f312e706e67" width=600px>

Percobaan menggunakan 2 board ESP yang saling berkomunikasi. Hasil sensor ESP A dikirim ke ESP B dan juga sebaliknya dalam interval waktu tertentu. Sehingga program menggabungkan fungsi pengiriman dan penerimaan data serta pembacaan sensor sekaligus.

## Kesimpulan
   - ESP dapat berkomunikasi satu sama lain dengan protokol ESP-NOW dengan mode point to point (PTP) dan point to multipoint (PTM) atau sebaliknya. Serta untuk   komunikasi - simpleks (searah) maupun dupleks (dua arah).
   - Untuk mengirimkan data, format struktur antara pengirim dan penerima haruslah sama, jika berbeda maka tidak akan terkirim.
   - Komunikasi satu arah untuk PTP, ESP pengirim (master) harus mengetahui MAC address ESP penerima (slave). Sedangkan ESP penerima tidak perlu.
   - Komunikasi PTM, pengirim harus mengetahui seluruh MAC dari ESP yang akan dikirimkan datanya serta mengatur peer untuk dapat mengirim ke banyak tujuan. Sedangkan penerima hanya perlu menyamakan format struktur data yang akan diterima saja.
   - Komunikasi MTP, beberapa pengirim harus mengetahui MAC dari ESP penerima, dan ESP penerima harus dapat memilah data dari berbagai sumber sekaligus dengan mengidentifikasi sumber paket berdasarkan MAC address.
   - Untuk komunikasi dua arah, kedua ESP dibekali dengan kode untuk mengirim dan menerima (hybrid) dan mengetahui MAC address satu sama lain.
