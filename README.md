nama : Asep saepuloh
NIM : 312210037
kelas : TI.CI.22


ExException Handling
* Exception (eksepsi) merupakan suatu kesalahan(error) yang terjadi saat proses eksekusi program sedang berjalan
* *esalahan ini akan menyebabkan program berakhir dengan tidak normal.
Handling
* Penanganan file adalah bagian penting dari aplikasi apapun.Statement
Assertion
* Assertion (pernyataan) adalah kewajaran program yang bisa kamu aktifkan/nonaktifkan ketika kamu selesai menjalankan program.
The Assert 
* Saat menemukan pernyataan, Python mengevaluasi eskpresi yang menyertainya, yang mana semoga benar. Jika ekspresi salah, Python memunculkan pengecualian AssertionError.

def KelvinToFahrenheit(Temperature):
    assert (Temperature >= 0), "Colder than absolute zero!"
    return ((Temperature-273)*1.8)+32
print (KelvinToFahrenheit(273))
print (int(KelvinToFahrenheit(505.78)))
print (KelvinToFahrenheit(-5))

Sintaks untuk pernyataan yaitu: assert Expression[, Arguments] Jika pernyataan gagal, Python menggunakan ArgumentExpression. ArgumentExpression sebagai argumen-argumen untuk AssertionError. Pengecualian AssertionError dapat ditangkap dan ditangani seperti pengecualian lainnya menggunakan try kecuali pernyataan, tetapi jika dibiarkan mereka akan menghentikan program dan menghasilkan backtrace.

Contoh : - Berikut adalah fungsi fungsi yang mengubah suhu dari derajat Kelvin menjadi derajat Fahrenheit.Karena nol derajat Kelvin dingin, fungsi fungsi menyimpannya jika melihat negatif negatif suhu. - Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

![image1.png](ss/1.png)

Menangani Pengecualian
Jika Anda memiliki beberapa kode mencurigakan yang mungkin mengeluarkan pengecualian, Anda dapat mempertahankan program Anda letakkan kode yang mencurigakan di *try: blok. Setelah coba: blok, sertakan pernyataan sertakan *except: statement, diikuti oleh blok kode yang menangani masalah seanggun mungkin.

Contoh :

* Contoh-contoh ini membuka file, menulis konten file, dan keluar dengan aman karena ada tidak masalah
* Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

try:
    fh = open("testfile", "w")
    fh.write("This is my test file for exception handling!!")
except IOError:
    print("Error: can\ 't find file or read data ")
else:
    print("Written content in the file successfully")
    fh.close()
![image2.png](ss/2.png)

* Contoh ini mencoba membuka file yang Anda tidak memiliki izin menulis, sehingga membuat file pengecualian
* Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

try:
    fh = open("testfile", "r")
    fh.write("This is my test file for exception handling!!")
except IOError:
    print("Error: can\ 't find file or read data ")
else:
    print("Written content in the file successfully")
    fh.close()
![image3.png](ss/3.png)

Fasal kecuali Tanpa Pengecualian
* Anda juga dapat menggunakan pernyataan exception tanpa exception yang didefinisikan sebagai berikut: try: You do your operations here; ...................... except: If there is any exception, then execute this block. ...................... else: If there is no exception then execute this block. Pernyataan coba-kecuali jenis ini menangkap semua pengecualian pengecualian yang terjadi. Menggunakan percobaan seperti try-expect pernyataan tidak dianggap sebagai praktik pemrograman yang baik, karena mereka menangkap semuanya pengecualian tetapi tidak membuat programmer mengidentifikasi kemungkinan penyebab masalah terjadi
Klausa Kecuali dengan Berbagi Pengecualian
* Anda juga dapat menggunakan pernyataan exception yang sama untuk menangani beberapa exception sebagai berikut: try: You do your operations here; ...................... except(Exception1[, Exception2[,...ExceptionN]]]): If there is any exception from the given exception list, then execute this block. ...................... else: If there is no exception then execute this block.
Klausa coba-akhirnya
Contoh :

* *ika anda tidak memiliki izin untuk membuka file dalam mode tulis yang dapat ditulis, maka ini akan menghasilkan hasil berikut:

try:
    fh = open("testfile", "w")
    fh.write("This is my test file for exception handling!!")
finally:
    print ("Error: can\ 't find file or read data")
![image4.png](ss/4.png)

* Contoh yang sama dapat ditulis lebih bersih seperti berikut:

try:
    fh = open("testfile", "r")
    try:
        fh.write("This is my test file for exception handling!!")
    finally:
        print("Going to close the file")
        fh.close()
except IOError:
    print("Error: can\ 't find file or read file")
![image5.png](ss/5.png)

* Ketika exception dilempar ke dalam blok try, eksekusi segera dilanjutkan ke akhir memblok. Setelah semua pernyataan di blok akhirnya dieksekusi, pengecualian dimunculkan lagi dan ditangani dalam pernyataan kecuali jika ada di lapisan berikutnya yang lebih tinggi dari percobaan-kecuali penyataan.
Argumen Pengecualian
Contoh :

* Berikut adalah contoh untuk satu pengecualian
* Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

# Define a function here.

def temp_convert(var):
    try:
        return int(var)
    except ValueError(Argument):
        print("The argument does not contain numbers\n", Argument)
# Call above function here.

temp_convert("xyz");
![image6.png](ss/6.png)

Melempar Pengecualian
Contoh :

* Pengecualian dapat berupa string, kelas, atau objek. Sebagian besar pengecualian adalah pengecualian dari inti Python menimbulkan adalah kelas dengan argumen=argumen yang merupakan turunan dari kelas. Mendefinisikan pengecualian baru cukup mudah dan dapat dilakukan sebagai berikut:

def functionName( level ):
    if level < 1:
        raise("Invalid level!", level)
        # The code below to this would not be executed
        # if we raise the exception
![image7.png](ss/7.png)

Pengecualian yang Ditetapkan Pengguna
* Python juga memungkinkan Anda membuat pengecualian sendiri dengan menurunkan kelas-kelas dari yang standar pengecualian bawaan.
* Berikut adalah contoh-contoh yang terkait dengan RuntimeError. Di sini, kelas dibuat yang merupakan subkelas dari subkelas RuntimeError. Ini berguna saat anda perlu menampilkan tampilan informasi yang lebih spesifik saat e pengecualian tertangkap.
* Di blok try, pengecualian yang ditentukan pengguna dimunculkan dan ditangkap di blok except. Itu variabel e digunakan untuk membuat instance dari kelas Networkerror.

class Networkerror(RuntimeError):
    def __init__(self, arg):
        self.args = arg
try:
    raise Networkerror("Bad hostname")
except Networkerror(e):
    print(e.args)
![image8.png](ss/8.png)

Terima Kasih...