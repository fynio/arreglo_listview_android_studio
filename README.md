# Bienvenido a un nuevo minitutorial

El día de hoy les enseñaré como recorrer un arreglo utilizando un ListView.


![ListView](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tn66aljj3kmab3p2ppm8.png)



## Vamos al código!

# activity_main.xml

En nuestro **activiy_main.xml** agregaremos un **linearlayout** con orientación vertical y agregaremos un **listview** al cual le asignaremos un id al que llamaremos **listView1**

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">


    <ListView
        android:id="@+id/listView1"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
</LinearLayout>
```

# MainActivity

En nuestro MainActivity crearemos un objeto llamado **lista** de tipo **ListView**. Dentro del método onCreate le asignaremos el id que creamos en el activity_main el cual era **ListView1** de manera que el código quede así:

```

public class MainActivity extends AppCompatActivity {

    ListView lista;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        lista = findViewById(R.id.listView1);
}};


```
Debajo de nuestra lista crearemos un arreglo de tipo **String** al cual llamaremos **datos**.

```        
final String[] datos = new String[]{"UNO", "DOS", "TRES"};
```

Posteriormente agregaremos un **ArrayAdapter** tipo **String** y le asignaremos un layout tipo simple_list_item_1 y le pasaremos el arreglo llamado **datos**

```
ArrayAdapter<String> adaptador = new ArrayAdapter<String>(
                getApplicationContext(),
                android.R.layout.simple_list_item_1, datos);

```

Por último solo nos resta asignar ese adapter a nuestro listView llamado lista.

```
lista.setAdapter(adaptador);
```

Si desean obtener el valor seleccionado de la lista les dejo el siguiente código

```
     lista.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> adapterView, View view, int i, long l) 
{
 Toast.makeText(getApplicationContext(), "Opcion seleccionada" + adapterView.getItemAtPosition(i)                        .toString(), Toast.LENGTH_SHORT).show();

}
        });
```

Con esto hemos finalizado el tutorial. Espero seguirles enseñando más de Android Studio en los próximos días, ¡¡¡saludos!!!.

Les dejo el código completo en el siguiente enlace [Clic aquí para ver el código](https://github.com/fynio/arreglo_listview_android_studio.git)

## Hasta la próxima.
