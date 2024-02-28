# Media Query


Media queries dalam Flutter digunakan untuk menyesuaikan tata letak dan gaya aplikasi berdasarkan karakteristik perangkat atau kondisi tertentu, seperti ukuran layar atau orientasi perangkat. Flutter menyediakan widget MediaQuery yang dapat digunakan untuk mengakses informasi media dan menyesuaikan tampilan aplikasi.

Berikut adalah contoh penggunaan media query dalam Flutter:

    import 'package:flutter/material.dart';
    
    void main() {
      runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: MyHomePage(),
        );
      }
    }
    
    class MyHomePage extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        // Menggunakan MediaQuery untuk mendapatkan informasi media
        final mediaQuery = MediaQuery.of(context);
    
        return Scaffold(
          appBar: AppBar(
            title: Text('Media Query Example'),
          ),
          body: Center(
            child: Container(
              // Menyesuaikan lebar container berdasarkan lebar layar
              width: mediaQuery.size.width * 0.8,
              child: Text(
                'Hello, Flutter!',
                style: TextStyle(fontSize: 20),
              ),
            ),
          ),
        );
      }
    }

Dalam contoh di atas, MediaQuery.of(context) digunakan untuk mendapatkan objek MediaQueryData, yang menyediakan informasi tentang karakteristik layar seperti size, orientation, dan lainnya. Dalam hal ini, mediaQuery.size.width digunakan untuk mengatur lebar kontainer menjadi 80% dari lebar layar.

# Fleksibel

Flexible adalah widget di Flutter yang digunakan untuk memberikan fleksibilitas dalam menentukan bagian ruang yang akan diisi oleh widget dalam suatu tata letak. Widget ini biasanya digunakan di dalam widget seperti Row atau Column untuk menentukan seberapa banyak ruang yang akan diambil oleh masing-masing anak widget.

Berikut adalah contoh penggunaan Flexible dalam suatu Row:

    import 'package:flutter/material.dart';
    
    void main() {
      runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: MyHomePage(),
        );
      }
    }
    
    class MyHomePage extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text('Flexible Example'),
          ),
          body: Row(
            children: [
              // Widget yang tidak fleksibel
              Container(
                color: Colors.blue,
                height: 100,
                width: 100,
              ),
              // Widget flexible dengan flex 1
              Flexible(
                flex: 1,
                child: Container(
                  color: Colors.red,
                  height: 100,
                ),
              ),
              // Widget yang tidak fleksibel
              Container(
                color: Colors.green,
                height: 100,
                width: 100,
              ),
            ],
          ),
        );
      }
    }

Pada contoh di atas, Flexible digunakan di antara dua container. Container yang memiliki Flexible akan memanfaatkan ruang yang tersedia sesuai dengan nilai flex yang ditentukan. Dalam hal ini, container berwarna merah akan memanfaatkan lebih banyak ruang dibandingkan dengan container berwarna biru dan hijau.

Anda dapat menyesuaikan nilai flex sesuai dengan seberapa banyak ruang yang ingin Anda berikan pada masing-masing widget flexible. Semakin besar nilai flex, semakin banyak ruang yang akan diambil oleh widget tersebut. Jika semua widget dalam satu baris memiliki nilai flex yang sama, mereka akan mendapatkan ruang yang sama secara proporsional.


#Expanded

Expanded adalah widget Flutter yang sering digunakan bersamaan dengan Column, Row, atau Flex untuk memberikan fleksibilitas dan mengatur seberapa banyak ruang harus diambil oleh anak-anak widget di dalamnya. Expanded memberi tahu Flutter untuk memberikan sebanyak mungkin ruang yang tersedia pada widget tersebut.

Berikut adalah contoh penggunaan Expanded dalam suatu Row:

    import 'package:flutter/material.dart';
    
    void main() {
      runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          home: MyHomePage(),
        );
      }
    }
    
    class MyHomePage extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text('Expanded Example'),
          ),
          body: Row(
            children: [
              // Widget yang tidak diperluas (fixed size)
              Container(
                color: Colors.blue,
                height: 100,
                width: 100,
              ),
              // Widget yang diperluas (mengambil sisa ruang yang tersedia)
              Expanded(
                child: Container(
                  color: Colors.red,
                  height: 100,
                ),
              ),
              // Widget yang tidak diperluas (fixed size)
              Container(
                color: Colors.green,
                height: 100,
                width: 100,
              ),
            ],
          ),
        );
      }
    }

Pada contoh di atas, Expanded digunakan di antara dua container. Container yang berada dalam Expanded akan mengambil sebanyak mungkin ruang yang tersedia di dalam baris, dan ini akan memaksa container tersebut untuk mengisi sisa ruang yang tidak diambil oleh container yang memiliki ukuran tetap.

Anda dapat menggunakan Expanded baik di dalam Row, Column, atau Flex untuk memberikan fleksibilitas pada tata letak Anda, dan seiring dengan widget-widget lain seperti Flexible, Spacer, dan sebagainya, Anda dapat membuat tata letak yang responsif dan dinamis.



