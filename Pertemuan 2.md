# Pertemuan 2 : Pengenalan Dasar Flutter
## 2.1 Pengertian Flutter
Flutter adalah kerangka pengembangan perangkat lunak open-source yang dikembangkan oleh Google. Dengan menggunakan Flutter, Anda dapat membuat aplikasi yang indah dan responsif untuk berbagai platform, termasuk iOS, Android, dan web, dengan menggunakan satu basis kode sumber.

**Berikut adalah beberapa konsep dasar dalam Flutter:**

**1. Widget:**
   
   Flutter membangun antarmuka pengguna menggunakan widget. Widget adalah elemen-elemen dasar dalam Flutter, mulai dari elemen UI sederhana hingga elemen yang lebih kompleks.
   Flutter memiliki dua jenis widget: StatelessWidget (widget tanpa keadaan) dan StatefulWidget (widget dengan keadaan).
   
**2. StatelessWidget:**
   
   StatelessWidget adalah widget yang nilainya tidak berubah setelah diinisialisasi. Misalnya, teks statis atau gambar.
   Contoh:
   ```
   class MyTextWidget extends StatelessWidget {
    @override
     Widget build(BuildContext context) {
      return Text('Hello, Flutter!');
     }
    }
   ```

**3. StatefulWidget:**

   StatefulWidget adalah widget yang nilainya dapat berubah selama masa hidup widget. Misalnya, tombol yang dapat diubah statusnya.
   Contoh:
   ```
   class MyButtonWidget extends StatefulWidget {
      @override
      _MyButtonWidgetState createState() => _MyButtonWidgetState();
     }
  
      class _MyButtonWidgetState extends State<MyButtonWidget> {
      bool isPressed = false;
  
      @override
      Widget build(BuildContext context) {
        return ElevatedButton(
          onPressed: () {
            setState(() {
              isPressed = !isPressed;
            });
          },
          child: Text(isPressed ? 'Pressed' : 'Not Pressed'),
        );
      }
    }

   ```

**4. Material Design:**

   Flutter menggunakan konsep Material Design, yang dikembangkan oleh Google, untuk membuat antarmuka pengguna yang konsisten dan menarik pada platform Android.
   Anda dapat menggunakan widget dari paket material untuk membuat elemen UI sesuai dengan pedoman Material Design.

**5. Hot Reload:**

   Salah satu fitur unggulan Flutter adalah Hot Reload, yang memungkinkan Anda mengubah kode sumber aplikasi dan melihat perubahan tersebut secara langsung tanpa harus me-restart aplikasi.

**6. Dependency Management:**

   Flutter menggunakan sistem manajemen paket bernama "pub" untuk mengelola dependensi dan paket pihak ketiga.

**7. Flutter Widgets:**

   Flutter menyediakan berbagai widget yang dapat digunakan untuk membangun UI, mulai dari widget dasar seperti Container, Row, dan Column hingga widget lanjutan seperti ListView, GridView, dan banyak lagi.

**8. Dart Programming Language:**

   Flutter menggunakan bahasa pemrograman Dart. Meskipun Dart tidak seluas digunakan seperti beberapa bahasa lainnya, Flutter menyediakan pengalaman pemrograman yang efisien dan efektif.


Untuk memulai pengembangan Flutter, Anda perlu menginstal Flutter SDK dan Dart, serta menggunakan editor kode seperti Visual Studio Code atau Android Studio. Selain itu, dokumentasi resmi Flutter dan contoh kode yang tersedia di situs web Flutter dapat membantu Anda lebih memahami konsep dan praktik terbaik dalam pengembangan aplikasi menggunakan Flutter.

----------------------------------------------
_**Kosakata :**_
   https://revou.co/revoupedia/kosakata#i
