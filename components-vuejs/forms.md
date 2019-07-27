# Forms
--------

## Select (Vue-multiselect)
Para los formularios con carga de data usaremos [Vue-multiselect](https://vue-multiselect.js.org/) ya que nos permite realizar varias funciones como:

- Seleccionar varios elementos
- Busqueda integrada
- Etiquetadas (Taggin)
- Editar template o `slots`

### Ejemplo

`Select` para busqueda de roles, existen muchos [props](https://vue-multiselect.js.org/#sub-props). 

```html
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
