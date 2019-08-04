# General
---------

## Header

Siempre debe de contener un header en el cual se divide en 2 partes a la izquierda siempre tiene que haber un titulo y una descripción. En la parte derecha se puede agregar botones, opciones rapidas o accesos rapidos.



<!-- tabs:start -->

#### **Resultado**

![header-page](../_images/header-page.png 'Header Page')


#### **HTML**

```html

<div class="header-section">
    <div class="d-flex justify-content-between">
        <div class="align-self-center">
            <div class="title-section">Empresas</div>
            <p class="description-section">Lista de todas las empresas activas.</p>
        </div>
        <div class="align-self-center">
            <a href="{{ route('company.create') }}" class="btn btn-primary">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="none"
                    stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                    class="feather feather-plus">
                    <path d="M12 5v14M5 12h14" />
                </svg>
                Agregar empresa
            </a>
        </div>
    </div>
</div>

```
<!-- tabs:end -->