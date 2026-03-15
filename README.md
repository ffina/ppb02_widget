# Widget

Pada aplikasi ini terdapat beberapa jenis widget, diantaranya:

## MaterialApp
Root aplikasi yang mnehatur tema dan navigasi utama
``` return MaterialApp(
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
``` return Scaffold(
      appBar: AppBar(
        
        . . .

      ),
      body: Column(

        . . .

      ),
    );
```
