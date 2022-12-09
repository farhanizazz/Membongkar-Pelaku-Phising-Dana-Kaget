
# Membongkar Penipuan Bermodus Dana Kaget

Kemarin saya menemukan sebuah postingan di fb yang membagikan link yang katanya "link penipuan dana kaget". Karena penasaran saya mencoba membuka link tersebut dan berikut tampilan yang saya dapatkan  


## Screenshots

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050701845007450182/image.png?width=1025&height=362)

Dari screenshot diatas, bisa kita lihat tampilannya sudah persis banget dengan tampilan dana pada aslinya, hanya saja ini bukan dana aslinya karena jika kita memasukkan data kita lalu mengklik "lanjut" data kita akan diteruskan kepada si penipu 🤣. Lalu bagaimana si penipu bisa mengambil data kita? mari kita telusuri lebih dalam web satu ini. Pertama-tama saya akan mulai dengan membuka dev-tools bawaan yang ada di browser saya. 

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050703265190395924/image.png?width=1025&height=365)

di tab sources, kita bisa melihat source code dari website dana kaget palsu, dimana jika kita buka file "function.js" lalu kita scroll ke bagian paling bawah, kita bisa melihat
adanya command "fetch()". Didalam command "fetch()" ini, website akan melakukan hit ke api bot telegram dengan konten pesan yang dikirim ke bot itu adalah sebagai berikut

chat_id : ini merupakan user id dari penipu,  
text : ini merupakan isi konten dari pesan yang dikirimkan ke bot telegram.

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050704979524079657/image.png)

nah lalu apa id telegram dari penipunya? kita bisa melihat id telegram penipu pada file bernama telegram.js

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050705819194372116/image.png)

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050706043409276988/image.png)

Di file ini bisa kita lihat id_telegram dan id bot telegram dari si penipu nih, lalu buat dapetin username si penipu bagaimana? mudah saja, kita tinggal lakukan 
hit ke api penipu, nanti api telegram akan mengembalikan username penipu

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050707193382584320/image.png)

disini saya menggunakan aplikasi postman untuk melakukan hit api telegram penipu, saya mengisikan chat_id dengan id telegram penipu. setelah itu, data akan saya send, dan berikut ini adalah data yang dikembalikan oleh api bot telegramnya

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050707671822639104/WhatsApp_Image_2022-12-09_at_15.34.34.jpg?width=847&height=468)

Disini bisa kita lihat, username telegram dari penipu adalah @Mandasyfr, kita bisa coba search username itu di telegram dan berikut penampakan akun tele penipu
![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050746963093618730/WhatsApp_Image_2022-12-09_at_19.11.11.jpg?width=211&height=468)

Di akun tele diatas terdapat website yang bisa klik, website itu akan mengarah ke halaman berikut.

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050708222505394176/image.png?width=959&height=468)

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050708455188602900/image.png?width=975&height=468)
Tampilan website penipu  
\
\
Disini bisa kita lihat, penipu ini ternyata melakukan jual beli untuk website penipuan serta apk penyadap sms seperti yang pernah dibongkar disini  "https://nikkoenggaliano.my.id/read.php?id=7&fbclid=IwAR0fwRkXEjfavBJB3DvDmiEvsygC1e8u_lvquiiBLsbuHbiGtbY2V9KVq-w"
\
\
di website ini kita bisa lihat kalau di background web ini ada info instagram dan nomor handphone yang tertutup oleh konten web, kita tinggal membuka devtools lalu masuk ke tab sources seperti sebelumnya, lalu kita tinggal folder images

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050710379782750268/image.png)

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050710289416458340/bg_penipu.png?width=1025&height=366)

disitu bisa kita lihat nama telegram penipunya cocok seperti yang kita temukan ketika hit api telegram tadi, ketika saya cek getcontact untuk nomor penipu, beginilah hasilnya

![App Screenshot](https://media.discordapp.net/attachments/1041957790895321098/1050722881593692180/getcontanct.jpg?width=211&height=468)

Terimakasih sudah menyempatkan waktu untuk membaca, semua informasi yang ada disini saya dapatkan hanya dengan informasi yang ada di Google. Semoga kita menjadi lebih bijak sebelum mengisikan informasi data pribadi kita di website-website yang tidak kita kenal.

