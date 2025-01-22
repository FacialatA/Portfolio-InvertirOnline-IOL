Este proyecto permite conectarse a la API de Invertir Online (IOL) para consultar, procesar y visualizar la composición y valorización de un portafolio de inversiones.
Además, se realizan análisis sobre los activos, como distribución de valorización por tipo de activo y conversión de valores a USD MEP.

#Características del Proyecto
## 1. Conexión a la API de Invertir Online
Agrega tus credenciales en un archivo ".env"
Conexión mediante el endpoint de autenticación de la API de IOL.
Uso de credenciales personales (usuario y contraseña) para obtener un token de acceso.

## 2. Consulta de Portafolio
Obtención del portafolio por país a través del endpoint:
```
/api/v2/portafolio/{pais}
```
El pais por defecto es Argentina pero se puede alterar.
El resultado se organiza en un DataFrame que incluye las columnas:
Simbolo: El título del activo.
Descripcion: Descripción del activo.
Cantidad: Cantidad de unidades del activo.
Valorizado: Valor en la moneda original.
Moneda: Moneda en la que está valorizado el activo.
Tipo de Activo: Tipo de inversión (CEDEARS, Bonos, etc.).

## 3. Obtención de valor dolar MEP y conversión de activos a USD MEP
Consulta del precio del dólar MEP usando el endpoint:
```
/api/v2/Cotizaciones/MEP/{simbolo}
```
Utiliza por defecto el bono AL30.
Convierte automaticamente valores en Pesos Argentinos a USD MEP

## 4. Análisis de Portafolio
División del portafolio por tipo de activo y cálculo del total valorizado en USD MEP para cada uno.
Arroja el total en USD MEP para cada tipo de activo y el total valorizado del portfolio en USD MEP.

## 5. Visualizaciones
### Gráfico de Torta
Muestra la distribución del total valorizado en USD MEP por tipo de activo.
### Gráfico de Barras
Gráfico para cada tipo de activo mostrando el simbolo y su valorización en USD MEP.
