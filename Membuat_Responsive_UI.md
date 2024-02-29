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



# Expanded

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



# Fitted Box


FittedBox adalah widget di Flutter yang digunakan untuk menyesuaikan ukuran widget anaknya agar sesuai dengan ruang yang tersedia, dengan tetap mempertahankan aspek rasio widget tersebut. Jika widget anak memiliki ukuran yang lebih besar dari ruang yang tersedia, FittedBox akan menyesuaikannya agar sesuai, sementara jika ukurannya lebih kecil, FittedBox akan mempertahankan ukuran aslinya.

Berikut adalah contoh penggunaan FittedBox:

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
            title: Text('FittedBox Example'),
          ),
          body: Center(
            child: Container(
              color: Colors.blue,
              width: 200,
              height: 200,
              child: FittedBox(
                fit: BoxFit.contain,
                child: Image.network(
                  'https://example.com/your-image-url.jpg',
                ),
              ),
            ),
          ),
        );
      }
    }


Pada contoh di atas, kita menggunakan FittedBox di dalam suatu Container dengan ukuran tetap (200x200). FittedBox menyesuaikan ukuran gambar agar sesuai dengan ruang yang tersedia tanpa merusak aspek rasio gambar. Anda dapat mengubah nilai properti fit sesuai kebutuhan:

**BoxFit.contain:** Mengecilkan atau memperbesar gambar agar sesuai dengan ruang yang tersedia tanpa merusak aspek rasio.
**BoxFit.cover:** Mengecilkan atau memperbesar gambar agar menutupi seluruh ruang yang tersedia tanpa merusak aspek rasio.
**BoxFit.fill:** Memperbesar gambar untuk mengisi seluruh ruang yang tersedia, merusak aspek rasio.
**BoxFit.fitWidth:** Mengecilkan atau memperbesar gambar agar lebar sesuai dengan lebar ruang yang tersedia tanpa merusak aspek rasio.
**BoxFit.fitHeight:** Mengecilkan atau memperbesar gambar agar tinggi sesuai dengan tinggi ruang yang tersedia tanpa merusak aspek rasio.
Anda bisa memilih nilai yang sesuai dengan kebutuhan tata letak dan desain aplikasi Anda.



# Wrap


Wrap adalah widget di Flutter yang digunakan untuk mengatur tata letak widget-widget anaknya dalam baris atau kolom, dan jika widget anak melebihi batas lebar atau tinggi yang tersedia, widget tersebut akan dipindahkan ke baris atau kolom berikutnya. Wrap sangat berguna ketika Anda memiliki sejumlah widget yang ingin diatur dalam satu area, dan Anda ingin agar mereka berada dalam satu baris atau kolom dan secara otomatis bergerak ke baris atau kolom berikutnya jika tidak cukup ruang.

Berikut adalah contoh penggunaan Wrap:

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
            title: Text('Wrap Example'),
          ),
          body: Wrap(
            spacing: 8.0, // Jarak antara widget anak
            runSpacing: 8.0, // Jarak antara baris atau kolom
            children: [
              Chip(
                label: Text('Apple'),
                backgroundColor: Colors.red,
              ),
              Chip(
                label: Text('Banana'),
                backgroundColor: Colors.yellow,
              ),
              Chip(
                label: Text('Cherry'),
                backgroundColor: Colors.pink,
              ),
              Chip(
                label: Text('Date'),
                backgroundColor: Colors.brown,
              ),
              Chip(
                label: Text('Grape'),
                backgroundColor: Colors.purple,
              ),
              Chip(
                label: Text('Kiwi'),
                backgroundColor: Colors.green,
              ),
              Chip(
                label: Text('Orange'),
                backgroundColor: Colors.orange,
              ),
            ],
          ),
        );
      }
    }



Pada contoh di atas, kita menggunakan Wrap untuk mengelompokkan beberapa Chip dalam satu area. spacing mengatur jarak antara widget anak di dalam satu baris atau kolom, sedangkan runSpacing mengatur jarak antara baris atau kolom. Jika ruang tidak cukup untuk menampung semua widget dalam satu baris atau kolom, widget akan dipindahkan ke baris atau kolom berikutnya.

Wrap memungkinkan Anda membuat tata letak yang responsif dan dinamis, terutama ketika jumlah dan ukuran widget anak dapat bervariasi.



# Fitur GetX


Dalam GetX, Get.width dan Get.height adalah variabel global yang dapat digunakan untuk mendapatkan lebar dan tinggi layar atau widget dengan mudah. Ini sering digunakan untuk mengatur lebar atau tinggi widget berdasarkan ukuran layar atau parent widget.

Contoh penggunaan Get.width dan Get.height:


    import 'package:flutter/material.dart';
    import 'package:get/get.dart';
    
    class MyHomePage extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text('GetX Width and Height Example'),
          ),
          body: Center(
            child: Container(
              width: Get.width * 0.8, // Mengatur lebar container menjadi 80% dari lebar layar
              height: Get.height * 0.5, // Mengatur tinggi container menjadi 50% dari tinggi layar
              color: Colors.blue,
              child: Center(
                child: Text(
                  'Hello, GetX!',
                  style: TextStyle(fontSize: 20, color: Colors.white),
                ),
              ),
            ),
          ),
        );
      }
    }
    
    void main() {
      runApp(
        GetMaterialApp(
          home: MyHomePage(),
        ),
      );
    }


Dalam contoh di atas, Get.width digunakan untuk mendapatkan lebar layar dan kemudian digunakan untuk mengatur lebar container menjadi 80% dari lebar layar. Demikian pula, Get.height digunakan untuk mendapatkan tinggi layar dan digunakan untuk mengatur tinggi container menjadi 50% dari tinggi layar. Ini memungkinkan penyesuaian ukuran widget dengan mudah berdasarkan ukuran layar yang berbeda.



# Layout Builder


LayoutBuilder adalah widget di Flutter yang digunakan untuk membangun suatu widget berdasarkan batasan (constraints) yang diberikan oleh parent widget. Dengan LayoutBuilder, Anda dapat mengakses dan menggunakan batasan lebar dan tinggi yang diberikan ke widget tersebut.

Berikut adalah contoh penggunaan LayoutBuilder:

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
            title: Text('LayoutBuilder Example'),
          ),
          body: Center(
            child: LayoutBuilder(
              builder: (BuildContext context, BoxConstraints constraints) {
                // Menggunakan batasan (constraints) untuk mengatur tata letak
                return Container(
                  width: constraints.maxWidth * 0.8,
                  height: constraints.maxHeight * 0.5,
                  color: Colors.blue,
                  child: Center(
                    child: Text(
                      'Hello, LayoutBuilder!',
                      style: TextStyle(fontSize: 20, color: Colors.white),
                    ),
                  ),
                );
              },
            ),
          ),
        );
      }
    }




Dalam contoh di atas, LayoutBuilder digunakan untuk mendapatkan batasan (constraints) yang diberikan oleh parent widget. Kemudian, batasan tersebut digunakan untuk mengatur lebar dan tinggi container sesuai dengan persentase tertentu dari batasan tersebut.

Pentingnya LayoutBuilder terletak pada kemampuannya untuk membuat widget yang responsif terhadap perubahan ukuran layar atau parent widget, sehingga memungkinkan penyesuaian yang dinamis sesuai dengan kondisi tata letak.





# COnstrained Box


ConstrainedBox adalah widget Flutter yang memungkinkan Anda menetapkan batasan (constraints) tertentu pada widget anaknya. Dengan menggunakan ConstrainedBox, Anda dapat mengatur batasan lebar, tinggi, atau kedua-duanya untuk mempengaruhi tata letak dan ukuran widget anak.

Berikut adalah contoh penggunaan ConstrainedBox:


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
            title: Text('ConstrainedBox Example'),
          ),
          body: Center(
            child: ConstrainedBox(
              constraints: BoxConstraints(
                maxWidth: 200.0,
                maxHeight: 100.0,
              ),
              child: Container(
                color: Colors.blue,
                child: Center(
                  child: Text(
                    'Hello, ConstrainedBox!',
                    style: TextStyle(fontSize: 20, color: Colors.white),
                  ),
                ),
              ),
            ),
          ),
        );
      }
    }



Dalam contoh ini, ConstrainedBox digunakan untuk mengatur batasan lebar maksimum (maxWidth) dan tinggi maksimum (maxHeight) dari container. Sebagai hasilnya, kontennya tidak akan melebihi batasan yang ditetapkan.

Anda dapat menyesuaikan BoxConstraints sesuai kebutuhan proyek Anda, dan ConstrainedBox akan memastikan bahwa batasan tersebut diterapkan pada widget anaknya. Ini berguna ketika Anda ingin memberikan batasan pada ukuran widget agar sesuai dengan kebutuhan desain atau tata letak tertentu.
