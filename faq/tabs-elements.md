# ¿Como crear un elemento de Tabs en Docsify?

Se puede crear un elemento con tabs, para mejorar la presentacion, por ejemplo mostrar en tabs; como quedo al final en HTML y mostrar el codigo en html.

Lo unico que se tiene que hacer es agregar las etiquetas:

`<!-- tabs:start -->`
`<!-- tabs:end -->`


Dentro de estas etiquetas agregar contenido por tabs, por ejemplo para crear una tap tenemos que agregar:

```markdown
<!-- tabs:start -->

#### **TAB 1**

Contenido tab 1


#### **TAB 2**

Contenido tab 2


<!-- tabs:end -->
```

### Resultado

Quedando de esta manera:


<!-- tabs:start -->

#### **TAB 1**

Contenido tab 1


#### **TAB 2**

Contenido tab 2


<!-- tabs:end -->

?> **Nota:** La idea princpal de esto es para minificar la manera de mostrar al hacerlo en tabs, simplificar que puedes usar varias tabs para mostrar resultado, código HTML, código CSS y hasta código JS.