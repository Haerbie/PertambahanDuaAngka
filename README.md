# Latihan 1: Aplikasi Pertambahan Dua Angka

### Pembuat
- **Nama**: Muhammad Irwan Habibie
- **NPM**: 2210010461
- **Latihan 1**

---

## 1. Deskripsi Program
Aplikasi ini merupakan kalkulator sederhana yang memungkinkan pengguna untuk:
- Memasukkan dua angka pada dua TextField.
- Menampilkan hasil penambahan saat tombol **Tambah** diklik.
- Menghapus input di kedua TextField dan mengarahkan fokus ke TextField pertama saat tombol **Hapus** diklik.

## 2. Komponen GUI
- **JFrame**: Window utama aplikasi.
- **JPanel**: Panel untuk menampung komponen.
- **JLabel**: Label deskripsi input dan hasil.
- **JTextField**: Input angka pertama, angka kedua, dan hasil.
- **JButton**: Tombol untuk melakukan operasi **Tambah**, **Hapus**, dan **Keluar**.

## 3. Logika Program
- Operasi penambahan dua angka.
- Validasi input untuk memastikan pengguna memasukkan angka.

## 4. Events
Menggunakan **ActionListener** untuk menangani event dari tombol **Tambah**, **Hapus**, dan **Keluar**:

### A. Tombol Tambah
Menampilkan hasil penambahan setelah memvalidasi input.
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

### B. Tombol Hapus
```java
    private void buttonHapusActionPerformed(java.awt.event.ActionEvent evt) {                                            
        textField1.setText("");
        textField2.setText("");
        textFieldHasil.setText("");
        textField1.requestFocus();
    }  
```
### C. Tombol Hapus
```java
    private void buttonKeluarActionPerformed(java.awt.event.ActionEvent evt) {                                             
        System.exit(0);
    }                                           
```     
## 5. Variasi:
### A. KeyAdapter pada JTextField untuk membatasi input hanya angka
```java
        char karakter = evt.getKeyChar();
        if (!Character.isDigit(karakter)) {
            evt.consume();
        }
    } 
```
### B. Gunakan JOptionPane untuk menampilkan error input
```java
    catch (NumberFormatException ex) {
            JOptionPane.showMessageDialog(this, "Input harus berupa angka!", "Error", JOptionPane.ERROR_MESSAGE);
    }
```
### C. Implementasikan FocusListener untuk membersihkan JTextField saat mendapatkan fokus.
```java
    private void textField1FocusGained(java.awt.event.FocusEvent evt) {                                       
        textField1.setText("");
    }                                      
    private void textField2FocusGained(java.awt.event.FocusEvent evt) {                                       
        textField2.setText("");
    }                                      
    private void textFieldHasilFocusGained(java.awt.event.FocusEvent evt) {                                           
        textFieldHasil.setText("");
    }                                          
```
## 6. Tampilan Saat di Run :
   
   ![TampilanPertambahanDuaAngka](https://github.com/user-attachments/assets/5afcf256-29df-4259-a5f4-361f582c9b65)

## Indikator Penilaian:

| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    20    |
|  2  | Logika Program   |    20    |
|  3  | Kesesuaian UI    |    15    |
|  4  | Constructor      |    15    |
|  5  | Memenuhi Variasi |    30    |
|     | TOTAL        | 100 |
