
# Aplikasi Pertambahan Dua Angka

**Pembuat**: Muhammad Irwan Habibie  
**NPM**: 2210010461  
**Latihan 1**

## Deskripsi
Aplikasi ini adalah program GUI sederhana yang dibuat dengan Java Swing untuk melakukan operasi penjumlahan pada dua angka yang dimasukkan pengguna. Aplikasi ini memungkinkan pengguna memasukkan dua angka, menampilkan hasil penjumlahan, serta menghapus input atau keluar dari aplikasi.

## Fitur
- **Penjumlahan Angka**: Menambahkan dua angka yang dimasukkan oleh pengguna dan menampilkan hasilnya.
- **Penghapusan Input**: Menghapus nilai dari input dan hasil.
- **Keluar Aplikasi**: Menutup aplikasi dengan aman.
- **Validasi Input**: Memastikan bahwa input yang dimasukkan adalah angka, dengan menampilkan pesan kesalahan jika tidak valid.

## Struktur Tampilan GUI
1. **Label Utama**: Menampilkan judul "Aplikasi Pertambahan Dua Angka".
2. **Input Field**: Text field untuk memasukkan angka pertama dan kedua.
3. **Tombol Tambah**: Tombol untuk melakukan penjumlahan.
4. **Tombol Hapus**: Tombol untuk menghapus input dan hasil.
5. **Tombol Keluar**: Tombol untuk keluar dari aplikasi.
6. **Field Hasil**: Menampilkan hasil dari penjumlahan.

## Cara Penggunaan
1. Jalankan aplikasi.
2. Masukkan angka ke dalam kolom input untuk Angka 1 dan Angka 2.
3. Klik tombol **Tambah** untuk melihat hasil penjumlahan.
4. Hasil akan ditampilkan di field hasil.
5. Klik tombol **Hapus** untuk menghapus input dan hasil.
6. Klik tombol **Keluar** untuk menutup aplikasi.

## Logika Utama
- **Penjumlahan**: Program mengambil input dari dua text field, mengonversinya menjadi integer, dan menjumlahkannya. Hasil kemudian ditampilkan di field hasil.
- **Validasi Input**: Program menggunakan `try-catch` untuk menangkap kesalahan saat mengonversi input menjadi angka, menampilkan pesan kesalahan jika input tidak valid.

## Kode Utama
### Fungsi Penjumlahan dan Tampilkan Hasil
```java
private void buttonTambahActionPerformed(java.awt.event.ActionEvent evt) {                                             
    try {
        int angka1 = Integer.parseInt(textField1.getText());
        int angka2 = Integer.parseInt(textField2.getText());
        int hasil = angka1 + angka2;
        textFieldHasil.setText(Integer.toString(hasil));
    } catch (NumberFormatException ex) {
        JOptionPane.showMessageDialog(this, "Input harus berupa angka!", "Error", JOptionPane.ERROR_MESSAGE);
    }
}                                            
```

```java
private void buttonHapusActionPerformed(java.awt.event.ActionEvent evt) {                                            
    textField1.setText("");
    textField2.setText("");
    textFieldHasil.setText("");
    textField1.requestFocus();
}                                           
```

```java
private void buttonKeluarActionPerformed(java.awt.event.ActionEvent evt) {                                             
    System.exit(0);
}                                            
```
