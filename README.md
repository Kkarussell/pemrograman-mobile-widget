# coba_flutter

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## Deskripsi Widget

Penjelasan widget-widget yang digunakan di `lib/main.dart`, apa yang dilakukan setiap widget, dan di bagian mana widget tersebut digunakan

- **MaterialApp**: Widget root mengemas keseluruhan aplikasi, berisikan tema, navigasi, dan konfigurasi tingkat aplikasi lainnya. Digunakan dalam metode `build` dari kelas `MyApp`.
  ```dart
  return MaterialApp(
    title: 'Flutter Demo',
    theme: ThemeData(
      colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      useMaterial3: true,
    ),
    home: const RowColumnPage(),
  );
  ```

- **Scaffold**: Struktur visual dasar untuk tampilan layar aplikasi, termasuk app bar, body, dan elemen UI umum lainnya. Digunakan dalam metode `build` dari kelas `RowColumnPage`.
  ```dart
  return Scaffold(
    appBar: AppBar(
      title: const Text(
        'My First App',
        style: TextStyle(color: Colors.black),
      ),
      backgroundColor: Colors.orange[200],
      centerTitle: true,
    ),
    body: Column(...),
  );
  ```

- **AppBar**: Menampilkan app bar material design di bagian atas layar, biasanya berisi judul dan aksi. Digunakan di dalam properti `appBar` dari `Scaffold` di kelas `RowColumnPage`.
  ```dart
  appBar: AppBar(
    title: const Text(
      'My First App',
      style: TextStyle(color: Colors.black),
    ),
    backgroundColor: Colors.orange[200],
    centerTitle: true,
  ),
  ```

- **Text**: Menampilkan string teks dengan gaya opsional. Digunakan di `title` dari `AppBar`, dan di widget `Container` pink dan kuning dalam body dari `RowColumnPage`.
  ```dart
  title: const Text(
    'My First App',
    style: TextStyle(color: Colors.black),
  ),
  ```
  ```dart
  child: Text('What image is that', style: TextStyle(fontSize: 16)),
  ```

- **Column**: Mengatur children-nya secara vertikal dalam tata letak kolom. Digunakan sebagai `body` utama dari `Scaffold` di `RowColumnPage`, dan di dalam `Row` untuk mengelompokkan ikon dan teks.
  ```dart
  body: Column(
    crossAxisAlignment: CrossAxisAlignment.center,
    mainAxisAlignment: MainAxisAlignment.center,
    children: <Widget>[...],
  ),
  ```
  ```dart
  Column(children: [Icon(Icons.food_bank), Text("Food")]),
  ```

- **Container**: Widget serbaguna yang menggabungkan widget painting, positioning, dan sizing umum. Digunakan beberapa kali di body dari `RowColumnPage` untuk menerapkan margin, padding, warna, dan berisi widget lainnya.
  ```dart
  Container(
    child: AspectRatio(
      aspectRatio: 1.0,
      child: Container(...),
    ),
  ),
  ```
  ```dart
  Container(
    width: MediaQuery.of(context).size.width,
    margin: EdgeInsets.fromLTRB(20.0, 5.0, 20.0, 10.0),
    padding: EdgeInsets.all(20.0),
    color: Colors.pink[200],
    child: Text('What image is that', style: TextStyle(fontSize: 16)),
  ),
  ```

- **AspectRatio**: Membuat child untuk mempertahankan rasio aspek tertentu (lebar/tinggi). Digunakan di dalam `Container` pertama di body dari `RowColumnPage` untuk membatasi container gambar.
  ```dart
  AspectRatio(
    aspectRatio: 1.0,
    child: Container(...),
  ),
  ```

- **Center**: Memposisikan widget child nya ke center di dalam dirinya sendiri. Digunakan di dalam `Container` child dari `AspectRatio` di `RowColumnPage`.
  ```dart
  child: Center(
    child: Image.network(
      'https://picsum.photos/200',
      fit: BoxFit.cover,
      width: 500,
    ),
  ),
  ```

- **Image.network**: Memuat dan menampilkan gambar dari URL jaringan. Digunakan di dalam `Center` dalam body dari `RowColumnPage`.
  ```dart
  Image.network(
    'https://picsum.photos/200',
    fit: BoxFit.cover,
    width: 500,
  ),
  ```

- **Row**: Mengatur children secara horizontal dalam tata letak baris. Digunakan di dalam `Container` terakhir di body dari `RowColumnPage`.
  ```dart
  child: Row(
    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
    crossAxisAlignment: CrossAxisAlignment.start,
    children: <Widget>[...],
  ),
  ```

- **Icon**: Menampilkan ikon material design. Digunakan di dalam widget `Column` dalam `Row` di `RowColumnPage`.
  ```dart
  Icon(Icons.food_bank),
  ```
