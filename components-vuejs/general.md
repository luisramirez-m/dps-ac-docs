# General
---------

## Header Controls

Con el componente Header controls, se puede utilizar para mostrar un buscador y un buton para agregar items, de esta manera existe un "estandar" para este tipo de header.

Como lleva un `input` para buscar items, lo que se hizo es pasar el `value` medio de `emit` para pasar del componente `headers-controllers` (child) a el componente en que usemos (padre), por eso se tiene que crear la funcion `searchInput`, ya que pasamos en el componente (child); `v-on:emitSearch="searchInput"`.




| Property              | Type     | Description                                    |
|----------------------|-----------|------------------------------------------------|
| `add-button`         |  string   | Texto para el botón                            |
| `search-placeholder` |  string   | Texto para `placeholder` del buscador          |
| `v-on:emitSearch`    |  function | Function para recuperar los items del buscador |
| `:urlConfig`         |  string   | Ruta para el botón                             |



<!-- tabs:start -->

#### **Resultado**

![header-controls](../_images/header-controls.png 'Header Controls')


#### **HTML**
```vuejs
 <header-controls
    add-button="Agregar Discusion"
    search-placeholder="Buscar Discusion"
    v-on:emitSearch="searchInput"
    :urlConfig="route('discussion.create', project.slug)">
</header-controls>

<script>
...
methods: {
    searchInput(value) {
        this.search = value;
    }
}
...
</script>
```

<!-- tabs:end -->