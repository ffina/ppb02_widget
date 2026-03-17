# Widget

Berikut rincian fungsional dari widget-widget yang digunakan dalam aplikasi ini:

## MaterialApp
Root aplikasi yang mengatur tema dan navigasi utama. Pada widget ini didefinisikan identitas ``global ThemeData``  dan halaman utama yang akan ditampilkan pertama kali 
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
Sebagai struktur dasar halaman untuk tempat AppBar dan Body.
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
