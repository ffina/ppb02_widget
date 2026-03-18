# Widget

<img width="323" height="737" alt="image" src="https://github.com/user-attachments/assets/d79c16bb-31bb-4b48-b61b-4ee118da7514" />

Berikut rincian fungsional dari widget-widget yang digunakan dalam aplikasi ini:

## MaterialApp
Root aplikasi yang mengatur tema dan navigasi utama. Pada widget ini didefinisikan identitas global ``ThemeData``  dan halaman utama yang akan ditampilkan pertama kali.
```
return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const RowColumnPage(),
);
```

## Scaffold
Sebagai struktur dasar halaman untuk tempat ``AppBar`` dan ``Body``.
```
return Scaffold(
      appBar: AppBar(
        
        . . .

      ),
      body: Column(

        . . .

      ),
);
```

## AppBar
Menampilkan bar aplikasi pada bagian atas dengan judul "My First App" dengan warna belakang _orange_.

<img width="322" height="72" alt="image" src="https://github.com/user-attachments/assets/8bb98437-7f77-41bf-b42c-09df801aca66" />

```
appBar: AppBar(
        title: const Text(
          'My First App',
          style: TextStyle(color: Colors.black),
        ),
        backgroundColor: Colors.orange[200],
        centerTitle: true,
)
```

## Column
Menyusun elemen-elemen secara vertikal dari atas ke bawah seperti gambar, teks, row, dan counter. 
```
body: Column(
        crossAxisAlignment: CrossAxisAlignment.center,
        mainAxisAlignment: MainAxisAlignment.center,
        children: <Widget>[
          Container(
            . . .
          ),
          Container(
            . . .
          ),
          Container(
           . . .
            ),
          ),
          CounterCard(),
        ],
),
```

## Row
Menyusun elemen-elemen secara horizontal ke samping, digunakan untuk menampilakn ikon kategori dan bagian kontrol counter.

<img width="320" height="85" alt="image" src="https://github.com/user-attachments/assets/85866334-2c8c-47ec-b6db-6bfdc295d9de" />

```
child: Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              crossAxisAlignment: CrossAxisAlignment.start,
              children: <Widget>[
                Column(children: [Icon(Icons.food_bank), Text("Food")]),
                Column(children: [Icon(Icons.landscape), Text("Scenery")]),
                Column(children: [Icon(Icons.people), Text("People")]),
              ],
)
```

```
child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween,
        children: [
          Text("Counter here: $_counter", style: TextStyle(fontSize: 16)),
          Container(
            color: Colors.cyan[200],
            padding: EdgeInsets.all(5.0),
            child: IconButton(
              onPressed: _incrementCounter,
              icon: Icon(Icons.add, color: Colors.black, size: 16),
            ),
          ),
        ],
      ),
```

## Container
Widget yang digunakan sebagai pembungkus utama yang fleksibel untuk mengatur dekorasi, dimensi, serta jarak (spacing) pada elemen UI. Misalnya dengan memberi warna latar belakang, serta mengatur padding dan margin.
```
body: Column(
        . . .
          Container(
            . . .
          ),
          Container(
            . . .
          ),
          Container(
           . . .
            ),
          ),
          CounterCard(),
        ],
),
```

```
Container(
            color: Colors.cyan[200],
            padding: EdgeInsets.all(5.0),
            child: IconButton(
              onPressed: _incrementCounter,
              icon: Icon(Icons.add, color: Colors.black, size: 16),
            ),
),
```

## Center
Memastikan kontenn berada tepat di tengah, pada kasus ini menmpatkan gambar di tengah area.

<img width="319" height="334" alt="image" src="https://github.com/user-attachments/assets/1b409fc0-5ced-4803-83cf-f424e9ff67d7" />

```
child: Center(
                  child: Image.network(
                    'https://picsum.photos/200',
                    fit: BoxFit.cover,
                    width: 500,
                  ),
),
```

## AspectRatio
Menjaga perbandingan ukuran widget gambar tetap 1.0 agar berbentuk persegi.
<img width="261" height="266" alt="image" src="https://github.com/user-attachments/assets/d9b58513-b5db-4897-964d-05f455a6b993" />

```
child: AspectRatio(
              aspectRatio: 1.0,
              child: Container(
                . . .
                child: Center(
                  . . .
                  ),
                ),
              ),
),
```

## Image.network
Menampilkan gambar secara dinamis dari URL internet.

<img width="261" height="266" alt="image" src="https://github.com/user-attachments/assets/834bbdfc-0883-46a2-8fae-e83e8ac23443" />

```
child: Image.network(
                    'https://picsum.photos/200',
                    fit: BoxFit.cover,
                    width: 500,
)
```

## Text 
Menampilkan teks dengan pengaturan ``TextStyle``.
```
title: const Text(
          'My First App',
          style: TextStyle(color: Colors.black),
)
```

## Icon
Menampilkan simbol seperti ``Icons.food_bank``, ``Icons.landscape``, dan ``Icons.people``.
```
icon: Icon(Icons.add, color: Colors.black, size: 16)
```

## IconButton
Tombol interaktif berupa ikon yang akan men-trigger fungsi _increment counter_.
```
child: IconButton(
              onPressed: _incrementCounter,
              icon: Icon(Icons.add, color: Colors.black, size: 16),
)
```

## StatelessWidget
Widget bersufat statis (tidak berubah), pada aplikasi ini digunakan untuk halaman utama karena warna dan posisi kolom tidak perlu berubah-ubah saat aplikasi berjalan.
```
class RowColumnPage extends StatelessWidget {
      . . .
}
```

## StatefullWidget
Widget dengan _state_, pada aplikasi ini menggunakan ``CounterCard`` untuk data ``_counter`` yang akan bertambah setiap kali tombol diklik.
```
class CounterCard extends StatefulWidget {
  const CounterCard({super.key});

  @override
  State<CounterCard> createState() => _CounterCardState();
}
```
