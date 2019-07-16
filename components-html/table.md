
# Tablas
--------

## Table Primary

![Table Primary](../_images/table-primary.png 'Table Primary')

#### Componentes:
- [Tabla Boostrap Vuejs](https://bootstrap-vue.js.org/docs/components/table/#tables)
- [Pagination Boostrap Vuejs](https://bootstrap-vue.js.org/docs/components/pagination/#pagination)

?> **Nota:** Tiene que llevar el componente `pagination` cuando hay muchos elementos que mostrar.

```html
<b-table :per-page="perPage" :current-page="currentPage" :stacked="stacked" hover outlined :items="items" :fields="fields" :filter="filter" @filtered="onFiltered" class="table-dps my-4">
    <template slot="name" slot-scope="row">
        {{ row.value }} {{ row.item.last_name }}
    </template>
    <template slot="actions" slot-scope="row">
        <button href class="btn btn-primary btn-hidden">button</button>
    </template>
</b-table>

<b-pagination :hide-goto-end-buttons="true" v-model="currentPage" :total-rows="totalRows" :per-page="perPage" :hide-ellipsis="true" size="sm" class="my-3">
    <template slot="prev-text">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-chevron-left">
            <path d="M15 18l-6-6 6-6" />
        </svg>
    </template>
    <template slot="next-text">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-chevron-right">
            <path d="M9 18l6-6-6-6" />
        </svg>
    </template>
</b-pagination>
```

Como lo indica la documentación de **BVJS** (Bootstrap Vuejs), se tienen que usar varios `props` para el componente de `b-table`, estos son algunos de que se uso en el componente de Vuejs con el nombre [ListUsersCompanyComponent.vue](https://bitbucket.org/opteren/dps-ac/src/dev/resources/js/components/company/ListUsersCompanyComponent.vue)

```javascript
data() {
    return {
        totalRows: 1,
        currentPage: 1,
        perPage: 5,
        items: JSON.parse(this.data),
        stacked: "md",
        fields: [
            {
                key: "name",
                label: this.nameUser,
                sortable: true,
                sortDirection: "desc"
            },
            {
                key: "email",
                label: this.emailUser,
                sortable: false
            },
            {
                key: "actions",
                label: this.acctions
            }
        ]
    };
},
```

!> Posiblemente se va a realizar un componente para la paginacion y dejarlo como default este componente anterior.


---

### Referencias
- [Tables BVJS](https://bootstrap-vue.js.org/docs/components/table/#tables)