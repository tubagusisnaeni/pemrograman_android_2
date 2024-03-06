# Membuat Adaptive UI
## 1. Orientation Builder

OrientationBuilder adalah widget Flutter yang memungkinkan Anda membangun UI yang berubah berdasarkan orientasi perangkat (landscape atau portrait). Widget ini memberikan cara yang mudah untuk merespons perubahan orientasi dan mengatur tata letak UI dengan benar sesuai dengan orientasi saat ini.

Berikut adalah contoh penggunaan OrientationBuilder:

- Buat file baru **adaptip.dart**, ketik kode berikut :
> Contoh 1:

        import 'package:flutter/material.dart';
    
        class Adaptip extends StatefulWidget{
          const Adaptip({super.key});
        
          @override
          State<StatefulWidget> createState()=> _AdaptipState();
        }
        class _AdaptipState extends State<Adaptip>{
          @override
            Widget build(BuildContext context)
            {
              return Scaffold(
                body: Center(
                  child: (MediaQuery.of(context).orientation == Orientation.portrait)?
                  Container(
                    height: 300,
                    width: 300,
                    color: Colors.amber,
                    child: Image.asset('assets/unival.png',
                      fit: BoxFit.fill,),
                  ):
                  Container(
                    height: 300,
                    width: 600,
                    color: Colors.blue,
                    child: Image.asset('assets/unival.png',
                      fit: BoxFit.fitHeight,),
                  ),
                ),
              );
            }
        }



Pada contoh di atas, kita menggunakan OrientationBuilder di dalam widget Center. Saat orientasi perangkat berubah antara landscape dan portrait, widget tersebut akan membangun ulang UI di dalamnya. Dalam contoh ini, kita menampilkan sebuah logo Unival di dalam kotak persegi berwarna amber saat device kita dalam mode potrait, begitu mode device menjadi landscape maka tampilan UI berubah menjadi logo unival di dalam kotak persegi panjang berwarna biru.

Anda bisa menyesuaikan logika di dalam fungsi builder sesuai kebutuhan proyek Anda. OrientationBuilder memberikan kenyamanan dalam menanggapi perubahan orientasi, dan Anda dapat membangun tata letak yang berbeda, menyesuaikan margin, atau menampilkan widget yang berbeda berdasarkan kondisi orientasi.

> Contoh 2 :

    import 'package:flutter/material.dart';
    
    class Adaptip extends StatefulWidget {
      const Adaptip({Key? key}) : super(key: key);
    
      @override
      State<StatefulWidget> createState() => _AdaptipState();
    }
    
    class _AdaptipState extends State<Adaptip> {
      @override
      Widget build(BuildContext context) {
        return OrientationBuilder(
          builder: (context, orientation) {
            return orientation == Orientation.portrait
                ? WidgetPortrait()
                : WidgetLandscape();
          },
        );
      }
    }
    
    class WidgetPortrait extends StatelessWidget {
      const WidgetPortrait({
        Key? key,
      }) : super(key: key);
    
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
            child: Container(
              height: 300,
              width: 300,
              color: Colors.amber,
              child: Image.asset(
                'assets/unival.png',
                fit: BoxFit.fill,
              ),
            ),
          ),
        );
      }
    }
    
    class WidgetLandscape extends StatelessWidget {
      const WidgetLandscape({
        Key? key,
      }) : super(key: key);
    
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
            child: Container(
              height: 300,
              width: 600,
              color: Colors.blue,
              child: Image.asset(
                'assets/unival.png',
                fit: BoxFit.fitHeight,
              ),
            ),
          ),
        );
      }
    }


## 2. Adaptive Platform


Adaptive platform dalam konteks Flutter merujuk pada kemampuan framework ini untuk membuat antarmuka pengguna (UI) yang dapat beradaptasi dan memberikan pengalaman yang konsisten di berbagai platform, seperti iOS, Android, web, dan desktop. Flutter memfasilitasi pengembangan aplikasi yang dapat berjalan di berbagai platform dengan menggunakan kode Dart tunggal.

Flutter menyediakan widget yang dapat beradaptasi dengan gaya visual platform tempat aplikasi dijalankan. Sebagai contoh, kita gunakan package get.dart untuk mengambil nilai platform device. Ketika kita buka aplikasi menggunakan Device Android maka tampilan yang berlaku adalah kotak berwarna hitam. Sedangkan menggunakan Device IOS yang tampil adalah kotak berwarna orange.

> Ikuti Langkah pada Web berikut untuk menambahkan dependency Get :
  https://pub.dev/packages/get/install



    import 'package:flutter/material.dart';
    import 'package:get/get.dart';
    
    class Adaptip extends StatefulWidget {
      const Adaptip({Key? key}) : super(key: key);
    
      @override
      State<StatefulWidget> createState() => _AdaptipState();
    }
    
    class _AdaptipState extends State<Adaptip> {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
          child: (GetPlatform.isAndroid)
                ? WidgetAndroid()
                : WidgetIOS(),
          ),
        );
      }
    }
    
    class WidgetAndroid extends StatelessWidget {
      const WidgetAndroid({
        Key? key,
      }) : super(key: key);
    
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
            child: Container(
              height: 300,
              width: 300,
              color: Colors.black,
              child: Image.asset(
                'assets/unival.png',
                fit: BoxFit.fill,
              ),
            ),
          ),
        );
      }
    }
    
    class WidgetIOS extends StatelessWidget {
      const WidgetIOS({
        Key? key,
      }) : super(key: key);
    
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
            child: Container(
              height: 300,
              width: 300,
              color: Colors.orange,
              child: Image.asset(
                'assets/unival.png',
                fit: BoxFit.fitHeight,
              ),
            ),
          ),
        );
      }
    }
