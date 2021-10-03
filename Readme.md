# GP3 - Charlie
Pada grup project 3 ini kami ingin membuat sebuah Backend aplikasi yang berfokus pada lingkungan sekolah yaitu pengelompokan dan pengolahan nilai siswa, tujuan dari aplikasi yang kita buat ini adalah untuk memudahkan guru dan pegawai sekolah untuk memantau dan menyimpan nilai siswa siswi dari sekolah tersebut yang bentuk akhirnya berupa sebuah raport yang berisikan nama siswa, kelas siswa, serta nilai dari siswa tersebut.

Dengan beranggotakan Wira Sebagai ketua serta Iqbal dan Yusril sebagai anggota, kita harap dalam grup project ini dapat kita selesaikan tepat waktu.

Rancangan ERD bisa di lihat melalui link berikut :
https://1drv.ms/u/s!AvyjxC2Xxt29mgNKKwQFOMBaqZBu?e=khSRsb


### USER

+ Login User
   - Endpoint : /users
   - Method : POST
   - request : body
   #
    ```
    {
      email : "admin@gmail.com",
      password : "admin123",
    }
    ```
   #
   #### Respon Success
   Ini adalah tampilan ketika anda dapat melakukan login
   
    ```{
    "message": "Login Berhasil, Selamat Datang admin",
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEsInJvbGUiOiJhZG1pbiIsImlhdCI6MTYzMzI3NTMxMn0.a4iRMrlR9KNLxCXu9ZKROVm-1NkxZNNha1WeQes6s1U",
    "payload": {
        "userId": 1,
        "role": "admin"
    }
    ```
#
+ Register User
   - Endpoint : /users
   - Method : POST
   - request : body
   #
    ```
    {
      name : "Yusril"
      email : "yusril@gmail.com",
      password : "123456",
    }
    ```
   #
   #### Respon Success Status Code (201)
   Berikut adalah gambaran apabila data berhasil di buat.
   
    ```{
    {
    "message": "user created",
    "teacher": {
        "Nama_Guru": "Yusril",
        "ID": 2,
        "email": "yusril@gmail.com",
        "Role": "teacher"
    }
    ```
   #
   #### Respon Error Code (409)
   Error dikarenakan akibat data yang di inputkan sudah tersedia di dalam database sehingga ketika melakukan registrasi datanya akan conflict.
         
   
    ```{
    {
    "message": "email already exist"
    }
    ```

+ GET All Users
   - Endpoint : /users
   - Method : GET

   #
   #### Respon Success Status Code (201)
   Berikut adalah tampilan apabila user berhasil menampilkan semua data menggunakan Method GET.
   
    ```{
    {
    "users": [
        {
            "id": 1,
            "name": "admin",
            "email": "admin@gmail.com",
            "role": "admin",
            "Class": null
        },
        {
            "id": 2,
            "name": "Yusril",
            "email": "yusril@gmail.com",
            "role": "teacher",
            "Class": null
        }
    ],
    "currentUser": {
        "id": 1,
        "name": "admin",
        "email": "admin@gmail.com",
        "role": "admin",
        "Class": null
    }
    ```
   #
   #### Respon Error Code (409)
   Error dikarenakan akibat data yang di inputkan sudah tersedia di dalam database sehingga ketika melakukan registrasi datanya akan conflict.
         
   
    ```{
    {
    "message": "email already exist"
    }
    ```
    
