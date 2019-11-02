# Forms
--------

## Select (Vue-multiselect)

Para los formularios con carga de data usaremos [Vue-multiselect](https://vue-multiselect.js.org/) ya que nos permite realizar varias funciones como:

* Seleccionar varios elementos
* Busqueda integrada
* Etiquetadas (Taggin)
* Editar template o `slots` 

### Ejemplo

`Select` para busqueda de roles, existen muchos [props](https://vue-multiselect.js.org/#sub-props).

``` vuejs
<multiselect
    v-validate="'required'"
    v-model="user.selectdRol"
    deselect-label="Can't remove this value"
    track-by="name"
    label="name"
    :options="allRoles"
    :searchable="false"
    placeholder="Pick a value"
    :hideSelected="false"
    :closeOnSelect="true"
    :show-labels="false"
    :close-on-select="false"
    name="role"
></multiselect>
```

## Helper Icon

Para mostrar texto de ayuda usaremos este componente.

| Property    | Type    | Description                             |
|-------------|---------|-----------------------------------------|
| `message` |  string | Es el mensaje que mostrara el `tooltip`   |

<!-- tabs:start -->

#### **Resultado**

![form-helper-icon](../_images/form-helper-icon.png 'Form Helper Icon')

#### **HTML**

```html
<form-icon-helper message="{{ _i('Slug generado automaticamente. Pero puede ser editado por uno personalizado.') }}">
</form-icon-helper>
```

<!-- tabs:end -->

## Add Comment

Este componente es para mostrar el todo el fomrulario de Agregar comentario, por esta versión no se necesita `props` por el momento.

Este componente tiene el regreso de varios `input` con los `name` :

* `comment` 
* `visibility` 
* `files[]` 

Para `files[]` , se creo un helper en **Laravel** para poder "organizar" el `array` , se encuentra en: `app/Http/Helpers/General.php` la funcion se llama `generateObjectFiles` , usandolo de esta manera:


```php
if (count($_FILES['files']['name']) > 1) {
    foreach (generateObjectFiles($_FILES['files']) as $file) {
        $fileName = $file['name'];
        Storage::disk('files_discussion_comments')->put($fileName, file_get_contents($file['tmp_name']));
    }
}
```

<!-- tabs:start -->

#### **Resultado**

![form-add-comment](../_images/form-add-comment.png 'Form Add Comment')

#### **HTML**

```vuejs
<form-add-comment></form-add-comment>
```

<!-- tabs:end -->

## Comment item
Muestra un commentario unico, es decir que tenemos que correr un `foreach` en PHP o en VueJS.

| Property    | Type     | Description                                                                 |
|-------------|----------|-----------------------------------------------------------------------------|
| `id-admin`  |  boolean | Value opcionalm pero dejarlo por si se requiere en un futuro                |
| `data`      |  object  | Todo la data del comentario                                                 |
| `is-owner`  |  boolean | Value para saber si es el es el creador del commentario y pueda modificarlo |

De la la propiedad `data` se usa:
* `comment`
* `created_at`
* `userName` para generar el nombre con; `$comment->user()->first()->name`


<!-- tabs:start -->

#### **Resultado**

![comment-item](../_images/comment-item.png 'Comment Item')

#### **HTML**

```php
 @foreach ($comments as $comment)
    <form-item-comment :id-admin="false" :data="{{ $comment }}"
        @if (Auth::user()->id === $comment->user_id)
            :is-owner="@json(true)"
        @else
            :is-owner="@json(false)"
        @endif
        user-name="{{ $comment->user()->first()->name }}">
    </form-item-comment>
@endforeach
```

<!-- tabs:end -->

 