# Komponen Utama Project Flutter

Berikut adalah komponen utama yang perlu diperhatikan saat membuat Project Flutter :

## 1. main.dart

> File main.dart adalah titik awal atau entry point dari aplikasi Flutter. Pada dasarnya, main.dart mengandung fungsi main() yang akan dijalankan pertama kali ketika aplikasi Flutter dijalankan. Fungsi main() ini biasanya memanggil fungsi runApp(), yang akan membuat dan menjalankan aplikasi Flutter.

>> Contoh sederhana main.dart dalam Flutter mungkin terlihat seperti ini:



    import 'package:flutter/material.dart';
    
    void main() {
      runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: Scaffold(
            appBar: AppBar(
              title: Text('My Flutter App'),
            ),
            body: Center(
              child: Text('Hello, Flutter!'),
            ),
          ),
        );
      }
    }


Dalam contoh ini, main() memanggil runApp(MyApp()), yang menginisialisasi dan menjalankan aplikasi Flutter dengan menggunakan widget MyApp. Widget MyApp sendiri adalah turunan dari StatelessWidget dan mendefinisikan tata letak sederhana dengan judul aplikasi dan teks di tengah layar.

File main.dart ini dapat dianggap sebagai pintu gerbang untuk aplikasi Flutter Anda, dan dari sini Anda dapat membangun dan mengorganisir struktur proyek serta menyusun berbagai widget dan logika aplikasi.








