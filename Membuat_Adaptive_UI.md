# Orientation Builder

OrientationBuilder adalah widget Flutter yang memungkinkan Anda membangun UI yang berubah berdasarkan orientasi perangkat (landscape atau portrait). Widget ini memberikan cara yang mudah untuk merespons perubahan orientasi dan mengatur tata letak UI dengan benar sesuai dengan orientasi saat ini.

Berikut adalah contoh penggunaan OrientationBuilder:

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
            title: Text('OrientationBuilder Example'),
          ),
          body: OrientationBuilder(
            builder: (BuildContext context, Orientation orientation) {
              return Column(
                mainAxisAlignment: MainAxisAlignment.center,
                children: <Widget>[
                  Icon(
                    orientation == Orientation.portrait
                        ? Icons.portrait
                        : Icons.landscape,
                    size: 100.0,
                  ),
                  SizedBox(height: 20.0),
                  Text(
                    orientation == Orientation.portrait
                        ? 'Portrait Mode'
                        : 'Landscape Mode',
                    style: TextStyle(fontSize: 20.0),
                  ),
                ],
              );
            },
          ),
        );
      }
    }


Pada contoh di atas, kita menggunakan OrientationBuilder di dalam widget Column. Saat orientasi perangkat berubah antara landscape dan portrait, widget tersebut akan membangun ulang UI di dalamnya. Dalam contoh ini, kita menampilkan ikon dan teks berdasarkan orientasi perangkat.

Anda bisa menyesuaikan logika di dalam fungsi builder sesuai kebutuhan proyek Anda. OrientationBuilder memberikan kenyamanan dalam menanggapi perubahan orientasi, dan Anda dapat membangun tata letak yang berbeda, menyesuaikan margin, atau menampilkan widget yang berbeda berdasarkan kondisi orientasi.

# Adaptive Platform


Adaptive platform dalam konteks Flutter merujuk pada kemampuan framework ini untuk membuat antarmuka pengguna (UI) yang dapat beradaptasi dan memberikan pengalaman yang konsisten di berbagai platform, seperti iOS, Android, web, dan desktop. Flutter memfasilitasi pengembangan aplikasi yang dapat berjalan di berbagai platform dengan menggunakan kode Dart tunggal.

Berikut adalah beberapa contoh implementasi Adaptive Platform di Flutter:

## 1. Platform-aware Widgets:
Flutter menyediakan widget yang dapat beradaptasi dengan gaya visual platform tempat aplikasi dijalankan. Sebagai contoh, CupertinoButton adalah widget yang dirancang untuk terlihat dan berperilaku seperti tombol di iOS, sedangkan ElevatedButton sesuai dengan pedoman Material Design di Android.

    import 'package:flutter/material.dart';
    import 'package:flutter/cupertino.dart';
    
    class MyAdaptiveButton extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return (Theme.of(context).platform == TargetPlatform.iOS)
            ? CupertinoButton(
                child: Text('Tap me'),
                onPressed: () {
                  // Handle button tap on iOS
                },
              )
            : ElevatedButton(
                onPressed: () {
                  // Handle button tap on Android
                },
                child: Text('Tap me'),
              );
      }
    }


## 2. Platform Channels:
Flutter memungkinkan komunikasi antara kode Dart dan kode platform asli melalui platform channels. Ini memungkinkan pengembang untuk mengakses fitur atau fungsi platform-spesifik jika diperlukan.


    import 'package:flutter/services.dart';
    
    // Panggil metode platform-spesifik dari kode Dart
    void platformSpecificMethod() {
      const platform = MethodChannel('my_channel');
      platform.invokeMethod('myMethod');
    }


## 3. Platform Switching:
Anda dapat menyesuaikan perilaku aplikasi berdasarkan platform dengan menggunakan logika Platform.isX di Dart.

    if (Platform.isIOS) {
      // Perilaku khusus untuk iOS
    } else if (Platform.isAndroid) {
      // Perilaku khusus untuk Android
    }

## 4. Adaptive Icons:
Flutter menyediakan widget AdaptiveIcon yang memungkinkan Anda menampilkan ikon yang sesuai dengan platform saat aplikasi dijalankan pada perangkat yang berbeda.

## 5. Adaptive Theme:
Anda dapat mengatur tema aplikasi untuk beradaptasi dengan tema platform.

    theme: ThemeData(
      platform: TargetPlatform.iOS, // Sesuaikan dengan platform yang diinginkan
    ),

Melalui fitur-fitur ini, Flutter memungkinkan pengembang untuk membuat aplikasi yang dapat beradaptasi dengan baik di berbagai platform tanpa harus menulis kode UI yang terpisah untuk setiap platformnya. Ini mempermudah pengembangan lintas platform dan meminimalkan upaya untuk mencapai konsistensi UI di seluruh ekosistem.
