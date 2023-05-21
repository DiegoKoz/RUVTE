
<!-- README.md is generated from README.Rmd. Please edit that file -->

# presentes

<!-- badges: start -->

[![Travis build
status](https://travis-ci.org/DiegoKoz/presentes.svg?branch=master)](https://travis-ci.org/DiegoKoz/presentes)
[![CRAN
status](https://www.r-pkg.org/badges/version/presentes)](https://cran.r-project.org/package=presentes)
[![](http://cranlogs.r-pkg.org/badges/grand-total/presentes?color=blue)](https://cran.r-project.org/package=presentes)
[![](http://cranlogs.r-pkg.org/badges/last-month/presentes?color=blue)](https://cran.r-project.org/package=presentes)
<!-- badges: end -->

El objetivo de la librería `presentes` es poner a disposición la
información oficial sobre víctimas del terrorismo de estado provista en:

  - <http://datos.jus.gob.ar/dataset/registro-unificado-de-victimas-del-terrorismo-de-estado-ruvte>
  - <https://www.argentina.gob.ar/sitiosdememoria/ruvte/informe>
  - <http://basededatos.parquedelamemoria.org.ar/registros/>

## Son 30.000

Consideramos pertinente realizar la aclaración de que, aunque la
información provista por este dataset no cuenta con 30.000 registros,
esto no se debe a que no haya sido esa cantidad de víctimas del
terrorismo de Estado en Argentina durante la úlitma dictadura militar,
sino a que un gran número de casos no pudieron ser identificados y
sistematizados.

## Instalación

Puede instalar este paquete desde CRAN con: 

```r
install.packages("presentes") 
```

O puede instalarlo desde [GitHub](https://github.com/) con:

``` r
# install.packages("devtools")
devtools::install_github("DiegoKoz/presentes")
```

## Ejemplo de uso

``` r
library(presentes)
library(tidyverse)
```

``` r

presentes::apodos %>% glimpse()
#> Observations: 5,362
#> Variables: 4
#> $ id_unico_ruvte   <chr> "7420", "821", "17237", "8014", "12976", "3247"…
#> $ nombre           <chr> "SOBKO PEDRO MIGUEL", "CABILLA VERÓNICA MARÍA",…
#> $ apellido_materno <chr> "KOLENKO", "ÁVALOS GOYCOOLEA", "RAVIER", "VIGNE…
#> $ apodo            <chr> "ADOLFO SCHMIDT", "ADRIANA SALAS", "AGUSTÍN AMA…
presentes::centros_clandestinos_detencion %>% glimpse()
#> Observations: 762
#> Variables: 7
#> $ ID                            <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 13,…
#> $ lugar_emplazamiento_propiedad <chr> "POLICÍA FEDERAL", "EJÉRCITO", "AR…
#> $ denominacion                  <chr> "OLIMPO", "LA PERLA", "ESCUELA DE …
#> $ espacio_de_memoria            <lgl> TRUE, TRUE, TRUE, FALSE, FALSE, FA…
#> $ ubicacion                     <chr> "RAMÓN FALCÓN 4151 · Vélez Sarsfie…
#> $ lon                           <dbl> -58.38779, -64.35177, -58.46405, -…
#> $ lat                           <dbl> -34.61296, -31.46093, -34.53999, -…
presentes::parque_de_la_memoria %>% glimpse()
#> Observations: 8,751
#> Variables: 30
#> $ id                         <chr> "2123", "2125", "50", "2126", "2124",…
#> $ link                       <chr> "http://basededatos.parquedelamemoria…
#> $ nombre                     <chr> "Abachian, Juan Carlos", "Abad, Ana C…
#> $ edad                       <chr> "26", "24", "23", "25", "54", "23", "…
#> $ embarazada                 <chr> "", "", "", "", "", "", "Sí", "", "",…
#> $ estado                     <chr> "Detenido/a desaparecido/a", "Detenid…
#> $ ano_en_monumento           <chr> "1977", "1976", "1976", "1976", "1975…
#> $ domicilios                 <chr> "Calle 7 N° 579, La Plata", NA, "Libe…
#> $ estado_civil               <chr> "Soltero/a", "Casado/a", NA, "Soltero…
#> $ estudios                   <chr> "Universitario: UNLP, Derecho Derecho…
#> $ fecha_de_nacimiento        <chr> "01/09/1950", "04/11/1951", "03/08/19…
#> $ fecha_de_secuestro         <chr> "02/01/1977", "15/08/1976", "01/07/19…
#> $ lugar_de_nacimiento        <chr> "Mar Del Plata, Bs. As.", "General Sa…
#> $ lugar_de_secuestro         <chr> "LA PLATA. BS. AS.", "CORDOBA CAPITAL…
#> $ nacionalidad               <chr> "Argentina", "Argentina", NA, "Argent…
#> $ ocupaciones                <chr> "Estudiante Universitario            …
#> $ sexo                       <chr> "Masculino", "Femenino", "Masculino",…
#> $ victimas_simultaneas       <chr> "No hay información.", "No hay inform…
#> $ foto                       <chr> "http://basededatos.parquedelamemoria…
#> $ apodos                     <chr> NA, "La Turca", "Teniente Armando Neg…
#> $ cantidad_de_hijos          <chr> NA, "1", NA, NA, NA, NA, NA, NA, NA, …
#> $ victimas_relacionadas      <chr> NA, "Perucca, Jose Carlos (esposo)", …
#> $ casos_relacionados         <list> [NULL, <tbl_df[1 x 2]>, NULL, <tbl_d…
#> $ militancia                 <list> [<tbl_df[0 x 1]>, <tbl_df[0 x 1]>, <…
#> $ articulos_periodisticos    <list> [<tbl_df[0 x 1]>, <tbl_df[0 x 1]>, <…
#> $ datos_de_la_identificacion <chr> NA, NA, NA, "Aparición:21/10/76 Camin…
#> $ fecha_de_asesinado         <chr> NA, NA, NA, "21/10/1976", NA, NA, "21…
#> $ lugar_de_asesinato         <chr> NA, NA, NA, "MAGDALENA. BS. AS.", NA,…
#> $ observaciones              <chr> NA, NA, NA, NA, NA, NA, "Asesinada em…
#> $ datos_familiares           <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
presentes::victimas_accionar_represivo_ilegal %>% glimpse()
#> Observations: 8,753
#> Variables: 20
#> $ id_unico_ruvte                       <chr> "5389", "87", "11788", "990…
#> $ anio_denuncia                        <dbl> 1984, 1984, 1984, 1984, 198…
#> $ tipificacion_ruvte                   <chr> "DESAPARICION FORZADA", "DE…
#> $ apellido_paterno_nombres             <chr> "ABACHIAN  JUAN CARLOS", "A…
#> $ apellido_materno                     <chr> "BEDROSSIAN", "SCARLATA", "…
#> $ apellido_casada                      <chr> NA, "PERUCCA", NA, NA, NA, …
#> $ edad_al_momento_del_hecho            <chr> "26 años", "24 años", "21 a…
#> $ documentos                           <chr> "LE 8293245", "LC 10048122"…
#> $ anio_nacimiento                      <chr> "1950", "1951", "1954", "19…
#> $ provincia_nacimiento                 <chr> "BUENOS AIRES", "MENDOZA", …
#> $ pais_nacimiento                      <chr> "ARGENTINA", "ARGENTINA", "…
#> $ nacionalidad                         <chr> "ARGENTINA", "ARGENTINA", "…
#> $ embarazo                             <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ fecha_detencion_secuestro            <chr> "26/12/1976", "15/08/1976",…
#> $ lugar_detencion_secuestro            <chr> "LA PLATA  BUENOS AIRES", "…
#> $ fecha_asesinato_o_hallazgo_de_restos <chr> NA, NA, NA, "21/10/1976", N…
#> $ lugar_asesinato_o_hallazgo_de_restos <chr> NA, NA, NA, "GRAL. MANSILLA…
#> $ fotografia                           <chr> "Sí", "Sí", "No", "No", "Sí…
#> $ provincia_nacimiento_indec_id        <chr> "06", "50", "90", "06", "02…
#> $ pais_nacimiento_indec_id             <chr> "ARG", "ARG", "ARG", "ARG",…
presentes::victimas_accionar_represivo_ilegal_sin_denuncia_formal %>% glimpse()
#> Observations: 784
#> Variables: 21
#> $ id_unico_ruvte                       <chr> "103", "5390", "117", "118"…
#> $ anio_denuncia                        <dbl> 1984, 1984, 1984, 1984, 198…
#> $ tipificacion_ruvte                   <chr> "PRESUNCION DE DESAPARICION…
#> $ apellido_paterno_nombres             <chr> "ABRERA  LORENZO MIGUEL", "…
#> $ apellido_materno                     <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ apellido_casada                      <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ edad_al_momento_del_hecho            <chr> "sin datos", "sin datos", "…
#> $ documentos                           <chr> "sin datos", "sin datos", "…
#> $ anio_nacimiento                      <chr> "sin datos", "sin datos", "…
#> $ provincia_nacimiento                 <chr> "sin datos", "sin datos", "…
#> $ pais_nacimiento                      <chr> "sin datos", "sin datos", "…
#> $ nacionalidad                         <chr> "ARGENTINA", "ARGENTINA", "…
#> $ embarazo                             <lgl> NA, NA, NA, NA, NA, NA, NA,…
#> $ fecha_detencion_secuestro            <chr> NA, "ABR/1976", NA, NA, "06…
#> $ lugar_detencion_secuestro            <chr> NA, NA, NA, NA, "CORDOBA", …
#> $ fecha_asesinato_o_hallazgo_de_restos <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ lugar_asesinato_o_hallazgo_de_restos <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ fotografia                           <chr> "No", "No", "No", "No", "No…
#> $ fuente_original                      <chr> "Listado Clamor", "Listado …
#> $ provincia_nacimiento_indec_id        <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ pais_nacimiento_indec_id             <chr> NA, NA, NA, NA, NA, NA, NA,…
```
