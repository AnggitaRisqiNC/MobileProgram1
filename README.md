# Fibonacci Sequence
Nama : Anggita Risqi Nur Clarita

NIM : 312210450

Kelas : TI.22.A.4

Mata Kuliah : Pemrograman Mobile 1


## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Definisi Fibonacci|[Click Here](#definisi-fibonacci)|
|2|Script strings.xml|[Click Here](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/Fibonacci/strings.xml)|
|3|Script colors.xml|[Click Here](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/Fibonacci/colors.xml)|
|4|Script activity_toast.xml|[Click Here](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/Fibonacci/activity_toast.xml)|
|5|Script MainActivity.java|[Click Here](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/Fibonacci/MainActivity.java)|
|6|Script AndroidManifest.xml|[Click Here](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/Fibonacci/AndroidManifest.xml)|
|7|Output|[Click Here](#output)|


## Definisi Fibonacci
> **Deret Fibonacci** adalah deret bilangan yang dimulai dengan 0 dan 1, dan setiap angka berikutnya adalah jumlah dua angka sebelumnya. Deret ini dinamai dari Leonardo Fibonacci, seorang matematikawan Italia pada abad ke-13.
> 
> **Deret Fibonacci** adalah sebagai berikut: `0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...`
>
> **Deret Fibonacci** dapat ditemukan di berbagai bidang, termasuk matematika, sains, seni, dan arsitektur. Misalnya, deret Fibonacci dapat digunakan untuk menghitung susunan daun di batang pohon, spiral di cangkang kerang, dan komposisi lukisan.


## Penjelasan dari MainActivity.java
### Script
```java
package com.hello;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.content.ContextCompat;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {

    private long fibMinus1 = 0;
    private long fibMinus2 = 1;
    private long currentFib = 0;
    private TextView mShowFibonacci;
    private long i = 0;

    private long n = 0;
    private long limit = 0;

    private EditText mLimitInput;
```

> #### *Penjelasan*
> Program di atas adalah program untuk menghitung deret Fibonacci di Android Studio di bagian **MainActivity.java**. Program ini menggunakan variabel `fibMinus1`, `fibMinus2`, dan `currentFib` untuk menyimpan tiga angka Fibonacci terakhir.
>
> * `fibMinus1`, `fibMinus2`, dan `currentFib` adalah variabel untuk menyimpan tiga angka Fibonacci terakhir.
>
> * `mShowFibonacci` adalah variabel untuk menyimpan referensi ke TextView yang akan digunakan untuk menampilkan deret Fibonacci.
>
> * `i` adalah variabel untuk menyimpan iterasi saat ini dari for loop.
>
> * `n` adalah variabel untuk menyimpan angka Fibonacci yang akan dihitung.
>
> * `limit` adalah variabel untuk menyimpan batas deret Fibonacci.
>
> * `mLimitInput` adalah variabel untuk menyimpan referensi ke EditText yang akan digunakan untuk input batas deret Fibonacci.


### Script
```java
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_toast);
        mShowFibonacci =findViewById(R.id.show_count);
        mLimitInput =findViewById(R.id.limit_input);
        updateFibonacciDisplay();
    }
```

> #### *Penjelasan*
> Program di atas adalah program untuk menghitung deret Fibonacci di Android Studio dan menampilkannya di Toast. Program ini menggunakan metode `updateFibonacciDisplay()` untuk menghitung dan menampilkan deret Fibonacci.
> 
> #### Metode `updateFibonacciDisplay()` bekerja sebagai berikut:
> 1. Mendapatkan batas deret Fibonacci dari input EditText `mLimitInput`.
>
> 2. Inisialisasi variabel `fibMinus1` dan `fibMinus2` dengan 0 dan 1.
>
> 3. Hitung deret Fibonacci dengan menggunakan rumus berikut: `currentFib = fibMinus1 + fibMinus2`.
>
> 4. Update variabel `fibMinus1` dan `fibMinus2` dengan nilai `currentFib` dan `fibMinus1`.
> 
> 5. Ulangi langkah 3 dan 4 hingga mencapai batas deret Fibonacci.


### Script
```java
    public void countUp(View view) {
        if (mLimitInput.getText().toString().isEmpty()) {
            Toast.makeText(this, "Enter the limit first", Toast.LENGTH_SHORT).show();
            return;
        }

        limit = Long.parseLong(mLimitInput.getText().toString());

        if (n >= limit) {
            Toast.makeText(this, "Fibonacci limit reached", Toast.LENGTH_SHORT).show();
            return;
        }

        long newFib = fibMinus1 + fibMinus2;
        fibMinus2 = fibMinus1;
        fibMinus1 = newFib;
        currentFib = newFib;
        n++;

        updateFibonacciDisplay();
    }
```

> #### *Penjelasan*
> Metode `countUp()` adalah metode untuk menghitung deret Fibonacci berikutnya dan menampilkannya di UI.
> 
> * `public void countUp(View view)` Baris kode ini mendeklarasikan metode countUp() yang akan dipanggil saat tombol "Count" diklik.
>
> * `if (mLimitInput.getText().toString().isEmpty()) {` Baris kode ini memeriksa apakah input batas deret Fibonacci kosong. Jika kosong, akan ditampilkan pesan kesalahan. Jika tidak kosong, lanjutkan ke langkah berikutnya.
>
> * `Toast.makeText(this, "Enter the limit first", Toast.LENGTH_SHORT).show();` Baris kode ini menampilkan pesan kesalahan "Enter Limit" jika input batas deret Fibonacci kosong.
>
> * `return;` Baris kode ini mengembalikan metode `countUp()` jika input batas deret Fibonacci kosong.
>
> * `limit = Long.parseLong(mLimitInput.getText().toString());` Baris kode ini mendapatkan batas deret Fibonacci dari input EditText `mLimitInput`.
>
> * `if (n >= limit) {` Baris kode ini memeriksa apakah angka Fibonacci saat ini (variabel `n`) lebih besar atau sama dengan batas deret Fibonacci. Jika lebih besar atau sama, akan ditampilkan pesan kesalahan. Jika tidak, lanjutkan ke langkah berikutnya.
>
> * `Toast.makeText(this, "Fibonacci limit reached", Toast.LENGTH_SHORT).show();` Baris kode ini menampilkan pesan kesalahan "Fibonacci limit reached" jika angka Fibonacci saat ini (variabel `n`) lebih besar atau sama dengan batas deret Fibonacci.
>
> * `return;` Baris kode ini mengembalikan metode `countUp()` jika angka Fibonacci saat ini (variabel `n`) lebih besar atau sama dengan batas deret Fibonacci.
>
> * `long newFib = fibMinus1 + fibMinus2;` Baris kode ini menghitung angka Fibonacci berikutnya dengan menggunakan rumus berikut: `newFib = fibMinus1 + fibMinus2;`
>
> * `fibMinus2 = fibMinus1;` Baris kode ini memperbarui variabel fibMinus2 dengan nilai variabel fibMinus1.
>
> * `fibMinus1 = newFib;` Baris kode ini memperbarui variabel `fibMinus1` dengan nilai variabel `newFib`.
>
> * `currentFib = newFib;` Baris kode ini memperbarui variabel `currentFib` dengan nilai variabel `newFib`.
>
> * `n++;` Baris kode ini memperbarui variabel `n` dengan nilai `n + 1`.
>
> * `updateFibonacciDisplay();` Baris kode ini memanggil metode `updateFibonacciDisplay()` untuk menampilkan deret Fibonacci di UI.


### Script
```java
    public void showFibonacci(View view) {
        Toast toast = Toast.makeText(this, R.string.fibonacci_message, Toast.LENGTH_SHORT);
        toast.show();
    }
```

> #### *Penjelasan*
> * Metode `showFibonacci()` digunakan untuk menampilkan Toast yang berisi deret Fibonacci saat ini.
>
> * Membuat instance Toast dengan menggunakan pesan dari file string `R.string.fibonacci_message`.
>
> * Menampilkan Toast tersebut dengan menggunakan metode `show()`.


### Script
```java
    public void reset(View view) {
        currentFib = 0;
        fibMinus2 = 1;
        fibMinus1 = 0;
        limit = 0;
        n = 0;
        mLimitInput.setText("");
        updateFibonacciDisplay();
    }
```

> #### *Penjelasan*
> Metode `reset()` digunakan untuk mereset semua variabel yang terkait dengan deret Fibonacci. 
>
> **Metode ini bekerja sebagai berikut:**
> 1. Mengatur variabel `currentFib` menjadi 0.
>
> 2. Mengatur variabel `fibMinus2` menjadi 1.
>
> 3. Mengatur variabel `fibMinus1` menjadi 0.
>
> 4. Mengatur variabel `limit` menjadi 0.
>
> 5. Mengatur variabel `n` menjadi 0.
>
> 6. Menghapus teks dari EditText `mLimitInput`.
>
> 7. Memanggil metode `updateFibonacciDisplay()` untuk memperbarui tampilan deret Fibonacci.


### Script
```java
    private void updateFibonacciDisplay() {
        if (mShowFibonacci != null) {
            mShowFibonacci.setText(Long.toString(currentFib));
            mShowFibonacci.setTextColor(getFibonacciColor());
        }
    }
```

> #### *Penjelasan*
> Metode `updateFibonacciDisplay()` digunakan untuk memperbarui tampilan deret Fibonacci.
>
> **Metode ini bekerja sebagai berikut:**
> 1. Memeriksa apakah TextView `mShowFibonacci` tidak kosong. Jika tidak kosong, lanjutkan ke langkah berikutnya.
>
> 2. Mengatur teks TextView `mShowFibonacci` menjadi string deret Fibonacci saat ini.
>
> 3. Mengatur warna teks TextView `mShowFibonacci` menjadi warna deret Fibonacci saat ini.


### Script
```java
    private int getFibonacciColor() {
        i++;
        if (i % 2 == 0) {
            return ContextCompat.getColor(this, R.color.colorPrimary);
        } else {
            return ContextCompat.getColor(this, R.color.Berry);
        }
    }
}
```

> #### *Penjelasan*
> Metode `getFibonacciColor()` digunakan untuk mendapatkan warna deret Fibonacci saat ini.
>
> **Metode ini bekerja sebagai berikut:**
> 1. Menambahkan 1 ke variabel `i`.
>
> 2. Memeriksa apakah nilai variabel `i` habis dibagi 2. Jika habis dibagi 2, maka deret Fibonacci saat ini adalah genap.
>
> 3. Jika deret Fibonacci saat ini adalah genap, maka mengembalikan warna `colorPrimary`.
>
> 4. Jika deret Fibonacci saat ini adalah ganjil, maka mengembalikan warna `Berry`.


## Penjelasan dari strings.xml
### Script
```xml
<resources>
    <string name="app_name">HelloAppTI22A4</string>
    <string name="button_label_fibonacci">Fibonacci</string>
    <string name="button_label_count">Count</string>
    <string name="count_initial_value">0</string>
    <string name="fibonacci_message">Bilangan Fibonacci!</string>
    <string name="button_label_finish">Reset</string>
    <string name="enter_fibonacci_limit">Masukkan Limit Angka</string>
</resources>
```

> #### *Penjelasan*
> * `string name="app_name">HelloAppTI22A4</string>` String ini berisi nama aplikasi, yaitu "HelloAppTI22A4".
>
> * `<string name="button_label_fibonacci">Fibonacci</string>` String ini berisi label tombol "Fibonacci".
>
> * `<string name="count_initial_value">0</string>` String ini berisi nilai awal dari penghitung deret Fibonacci, yaitu 0.
>
> * `<string name="fibonacci_message">Bilangan Fibonacci!</string>` String ini berisi pesan yang akan ditampilkan ketika pengguna mengklik tombol "Fibonacci".
>
> * `<string name="button_label_finish">Reset</string>` String ini berisi label tombol "Reset".
>
> * `<string name="enter_fibonacci_limit">Masukkan Limit Angka</string>` String ini berisi pesan yang akan ditampilkan ketika pengguna diminta untuk memasukkan limit deret Fibonacci.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/1.png)
> **Keterangan** : Berikut adalah tampilan apabila telah berhasil di **RUN** di awali dengan angka 0.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/2.png)
> **Keterangan** : Selanjutnya, sebelum mengklik tombol *"Count"*, sebaiknya isi limit terlebih dahulu. Sebagai contoh, saya mengisi limit dengan angka 9.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/3.png)
> **Keterangan** : Selanjutnya, bisa langsung klik tombol *"Count"*. Maka, tampilannya akan berubah dari angka 0 menjadi angka 1.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/4.png)
> **Keterangan** : Deret Fibonacci memiliki pola sebagai berikut: `0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...` Oleh karena itu, setelah angka 1 muncul, angka berikutnya juga akan menjadi angka 1. Perubahan angka ini ditandai dengan perubahan warna pada angka tersebut.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/5.png)
> **Keterangan** : Selanjutnya, setelah angka 1 muncul dua kali, angka berikutnya akan menjadi 2. Angka-angka selanjutnya akan mengikuti urutan deret Fibonacci, yaitu `0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...`.

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/6.png)
> **Keterangan** : Ketika deret Fibonacci mencapai limit, maka akan tampil teks "Fibonacci limit reached". Ketika kita klik tombol "Count", maka tidak akan dilanjutkan dan hanya berhenti di angka limit tersebut. 

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/7.png)
> **Keterangan** : Selanjutnya, jika kita klik tombol *"Fibonacci"*, maka akan muncul tampilan teks "Bilangan Fibonacci!"

### Output
![image](https://github.com/AnggitaRisqiNC/MobileProgram1/blob/main/screenshot/8.png)
> **Keterangan** : Terakhir, ini adalah tampilan apabila diklik tombol *"Reset"*, semua akan kembali ke tampilan awal, dimulai dari angka 0, dan harus memasukkan limit lagi.

## Finish