
</p>
<img width="1715" height="512" alt="margia-logo-blanco" src="https://github.com/user-attachments/assets/a93fd72b-1177-48f7-aa6e-d696cc4bdf61" />


<h1 align="center">Conoce tu costo. Cuida tu margen.</h1>

> **Margia** es un programa de costeo estándar para negocios que producen. Calcula cuánto *debería* costar cada producto, lo compara con lo que de verdad gastaste y te muestra **dónde se te va la ganancia**. Funciona en tu computador, **sin internet**, y tus datos se quedan contigo.

<img width="2880" height="2618" alt="margia-tablero-hd" src="https://github.com/user-attachments/assets/e5e05845-f81d-428a-ae57-bb957d218ffa" />


*Las capturas de esta guía usan datos de ejemplo de una pastelería ficticia.*

## Contenido

1. [Qué hace Margia](#1-qué-hace-margia)
2. [Descargar desde GitHub](#2-descargar-desde-github)
3. [Qué necesitas antes de iniciar](#3-qué-necesitas-antes-de-iniciar)
4. [Abrir Margia](#4-abrir-margia)
5. [Entrar y proteger tu cuenta](#5-entrar-y-proteger-tu-cuenta)
6. [Tu primera vez: la ruta de 9 pasos](#6-tu-primera-vez-la-ruta-de-9-pasos)
7. [Cada día: tablero, inventario y reportes](#7-cada-día-tablero-inventario-y-reportes)
8. [Importar y exportar con Excel](#8-importar-y-exportar-con-excel)
9. [Trabajar en equipo: usuarios, permisos y correcciones](#9-trabajar-en-equipo-usuarios-permisos-y-correcciones)
10. [Respaldos](#10-respaldos)
11. [Usarlo desde otros computadores de la red](#11-usarlo-desde-otros-computadores-de-la-red-opcional)
12. [Cómo sacarle el máximo provecho](#12-cómo-sacarle-el-máximo-provecho)
13. [Si algo falla](#13-si-algo-falla)
14. [Más información](#14-más-información)

---

## 1. Qué hace Margia

Casi todos los negocios saben cuánto venden. Pocos saben cuánto les cuesta de verdad cada producto. Margia responde tres preguntas:

| Pregunta | Qué te da Margia |
|---|---|
| **¿Cuánto debería costar?** | La **hoja de costo estándar** de cada producto: materiales (con desperdicio), mano de obra y costos indirectos (CIF). Te sugiere el precio para el margen que quieres y cuántas unidades debes vender para no perder. |
| **¿Cuánto costó de verdad, y por qué?** | Las **órdenes de producción**: registras lo que realmente se usó y, al cerrarlas, Margia calcula **seis variaciones** que te dicen qué causó la diferencia. |
| **¿Qué me queda en la bodega?** | El **inventario** con costo promedio, kardex y alertas de reposición. Al cerrar una orden descuenta solo lo que se consumió. |

También incluye: varias empresas y periodos, reportes en Excel y PDF con tu logo y colores, importar y exportar en Excel, histórico del costo estándar, usuarios con permisos por módulo, registro de actividad y respaldos automáticos.

> **Importante:** Margia calcula costos estándar y variaciones con los datos que tú cargas. **No reemplaza a un contador**: no hace contabilidad general, nómina ni declaraciones, y sus resultados no son asesoría contable ni tributaria.

---

## 2. Descargar desde GitHub

1. Abre la página del proyecto en GitHub: <https://github.com/dajed208/margia.github.io>
2. En la columna derecha, entra a **Releases** y elige la versión más reciente. Atajo: <https://github.com/dajed208/margia.github.io/releases/latest>
3. En **Assets**, descarga el archivo **`margia.zip`**.
4. Descomprímelo en una carpeta fija, por ejemplo `C:\Margia`. En Windows: clic derecho sobre el archivo → **Extraer todo…**

> **Ojo con el botón verde «Code → Download ZIP»:** descarga el contenido del *repositorio*, que no es lo mismo que el paquete del Release. Para usar Margia descarga siempre `margia.zip` desde **Releases**.

**Consejos para la carpeta**
- Evita «Archivos de programa»: ahí Windows no deja escribir y Margia necesita guardar tus datos.
- Evita carpetas sincronizadas con OneDrive o Dropbox: el archivo de la base se puede dañar si se copia justo mientras se guarda.
- Si Windows muestra una advertencia de seguridad al abrir archivos descargados de internet, elige *Ejecutar* o *Ejecutar de todas formas*, siempre que hayas bajado Margia de tu fuente oficial.

*Si venías de la versión anterior (Cifra), descomprime Margia **junto a su carpeta `cifra`**: al primer arranque el programa te ofrece copiar tus datos (el original no se toca).*

---

## 3. Qué necesitas antes de iniciar

| Necesitas | Detalle |
|---|---|
| **Un computador** | Windows 10 u 11, o Linux. En Mac debería funcionar con Python, pero todavía no se ha probado. |
| **Python 3.10 o superior** | Descárgalo de https://www.python.org/downloads/. En Windows, al instalar, **marca la casilla «Add python.exe to PATH»**. Comprueba con `python --version`. Se probó con Python 3.12 y se ha usado también con 3.14. |
| **Tres librerías** (Excel, PDF e imágenes) | `python -m pip install -r requirements.txt`. Necesitas internet **solo para este paso**; después no. Sin ellas el programa abre y puedes entrar, pero Excel, PDF e importar no funcionan (el sistema te dice qué falta). |
| **Un navegador actualizado** | Chrome, Edge o Firefox. |
| **Poder escribir en la carpeta del programa** | Ahí se guarda tu base de datos (`data\costos.db`). |

No hay que instalar ninguna base de datos ni servidor: todo viene incluido.

**Comprueba que todo está listo** (opcional, pero recomendado la primera vez). Desde una terminal abierta en la carpeta de Margia:

```
python iniciar.py --verificar
```

Debe terminar con `RESULTADO: todo listo.` Si algo falta, te dice qué.

---

## 4. Abrir Margia

**Lo más fácil, en Windows:** haz doble clic en **`Iniciar_Margia.bat`**. Comprueba que tengas Python, instala las librerías la primera vez (necesita internet) y abre Margia. Si falta algo, te dice qué hacer.

**O desde la terminal.** Ábrela en la carpeta de Margia (en Windows: abre la carpeta en el Explorador, haz clic en la barra de direcciones, escribe `cmd` y pulsa Enter) y escribe:

```
python iniciar.py
```

Si Windows dice que «python» no se reconoce, prueba `py iniciar.py`.

Aparece una **ventana negra** con este mensaje, y el navegador se abre solo:

```
Margia 1.0.0 funcionando.
  Datos guardados en: C:\Margia\data
  En este computador:   http://127.0.0.1:8765/
Deja esta ventana abierta mientras uses el sistema. Cierra con Ctrl+C.
```

Si el navegador no se abre, copia esa dirección en su barra. **Deja la ventana negra abierta mientras uses Margia**: es el motor del programa.


<img width="1100" height="656" alt="01-inicio-sesion" src="https://github.com/user-attachments/assets/18b9d56d-870b-4a7a-a4d0-bd4b4c21d854" />


> Si te entregaron una versión empaquetada (`Margia.exe`), haz doble clic en ese archivo en lugar de lo anterior. Mira `installer/LEAME.txt`.

---

## 5. Entrar y proteger tu cuenta

Los usuarios de fábrica son:

| Usuario | Contraseña | Qué puede hacer |
|---|---|---|
| `admin` | `admin123` | Todo: crear y editar datos, usuarios, respaldos. |
| `estudiante` | `estudiante123` | Consultar. El administrador decide qué más puede hacer, módulo por módulo. |

**Cambia la contraseña de inmediato**: las de fábrica son públicas (están en este mismo archivo). La primera vez que entres con una contraseña de fábrica se abre esta ventana:

<img width="1100" height="656" alt="02-primer-ingreso" src="https://github.com/user-attachments/assets/fc281e19-48bf-4adf-ac19-bf9064532219" />


Escribe la contraseña actual (`admin123`), la nueva (mínimo 6 caracteres) y repítela. Si eliges **«Más tarde»**, verás un aviso amarillo en cada pantalla hasta que lo hagas. Puedes cambiarla cuando quieras con el botón **«Cambiar contraseña»**, arriba a la derecha.

**Lo que debes saber de la sesión**
- Después de 5 intentos con una contraseña incorrecta, esa cuenta se bloquea durante 1 minuto. Las demás cuentas no se afectan.
- La sesión se cierra sola tras 2 horas sin usar el programa. Si ves «Tu sesión terminó», entra de nuevo.

**¿Olvidaste una contraseña?**
- Si es la de **otro usuario**, un administrador la cambia en **Usuarios → Editar → Nueva contraseña**.
- Si es la del **único administrador**, el programa **no tiene una forma automática de recuperarla**. Por eso conviene que **crees un segundo usuario con rol Administrador** (Usuarios → Nuevo usuario) y guardes las dos contraseñas en un lugar seguro.

---

## 6. Tu primera vez: la ruta de 9 pasos

Al entrar, el **Dashboard** muestra **«Tu ruta para empezar»**: los 9 pasos, en el orden en que el sistema necesita los datos (cada uno usa lo del anterior). **Se marcan solos** a medida que cargas tu información, y el botón **«Continuar»** te lleva al siguiente paso pendiente.

<img width="1100" height="795" alt="03-ruta-para-empezar" src="https://github.com/user-attachments/assets/5713fee9-120c-4c75-929a-fe957f107dbd" />


Un paso solo cuenta como hecho si está **completo**: un periodo sin unidades presupuestadas o un producto sin receta siguen pendientes, y la guía te dice qué falta.

### Paso 1 · Crea tu empresa
**Menú Empresas → Nueva empresa.** Código, razón social, NIT, régimen, si eres responsable de IVA y moneda. Desde la lista puedes agregarle un **logo** y elegir **colores** propios: aparecerán en la pantalla y en tus reportes PDF.

### Paso 2 · Crea un periodo contable
**Menú Periodos contables → Nuevo periodo.**

<img width="1100" height="687" alt="04-periodo" src="https://github.com/user-attachments/assets/3a4e3158-c001-4ec5-8b14-e2192b319834" />


El dato clave es **«Unidades de producción presupuestadas para el periodo»**: con él Margia reparte los costos indirectos entre tus productos. Si lo dejas en 0, el CIF se reparte de forma aproximada y el costo sale incorrecto.

### Paso 3 · Registra tus materias primas
**Menú Materias primas → Nueva materia prima.**

<img width="1100" height="763" alt="05-materia-prima" src="https://github.com/user-attachments/assets/dad3e096-d334-4774-90af-f29276e4403b" />


- **Costo estándar por unidad estándar:** lo que *debería* costar cada kilo, litro o unidad.
- **Eficiencia:** `100` = sin desperdicio. Con `95`, el 5 % se pierde, y Margia lo suma al costo.
- **Existencia mínima:** cuando el inventario baje de ahí, Margia te avisa que debes reponer.

### Paso 4 · Registra la mano de obra
**Menú Mano de obra directa → Nuevo trabajador.** Salario mensual, porcentaje de prestaciones y de cargas laborales, y **horas laborales por mes**. Margia calcula la **tarifa estándar por hora**.

<img width="1100" height="488" alt="06-mano-de-obra" src="https://github.com/user-attachments/assets/03c71885-4587-47cd-bfd5-c54c85acfb3e" />


> Registra solo a quienes **producen**: Margia usa la tarifa **promedio** de todos los trabajadores, y un administrador o un vendedor la subirían. Y las horas por mes son las del **mes** (unas 192), no las de la semana ni los días.

### Paso 5 · Define los costos indirectos (CIF)
**Menú Conceptos de CIF → Nuevo concepto de CIF.** Arriendo, gas, energía, empaques… Para cada uno: si es **fijo** o **variable**, su **valor presupuestado del periodo** y la **base de aplicación** con la que se reparte entre los productos (por ejemplo, horas de mano de obra o unidades producidas).

<img width="1100" height="488" alt="07-cif" src="https://github.com/user-attachments/assets/e38ea19c-07b5-424b-849c-05b016def246" />


### Paso 6 · Crea tus productos
**Menú Productos → Nuevo producto.** Código, descripción, unidad, **precio de venta** y **horas de mano de obra estándar por unidad**.

> Esas horas son el tiempo de **UNA unidad**, no el de toda la tanda. Si 30 galletas se hacen en 15 minutos: 15 ÷ 30 ÷ 60 = **0,0083 horas** por galleta.

### Paso 7 · Arma la receta de cada producto
**Menú Hoja de costo.** Elige el producto y, en «Materiales de la receta», agrega cada materia prima con su cantidad por unidad (**Agregar a la receta**). La hoja se calcula sola:

<img width="1100" height="1181" alt="08-hoja-costo" src="https://github.com/user-attachments/assets/c93c980d-33d4-43df-8259-5d45f6e2064f" />


- **Costo estándar unitario** = materiales + mano de obra + CIF.
- **Margen frente al precio de venta** = precio de venta − costo estándar.
- **Precio sugerido** = costo ÷ (1 − margen deseado). En el ejemplo, para ganar el 30 % hay que vender a $54.429, aunque hoy se venda a $46.000.
- **Punto de equilibrio** = costos fijos ÷ margen de contribución: cuántas unidades debes vender para no perder.

Si falta algo (por ejemplo, el CIF en cero), la hoja muestra un **aviso amarillo** que dice qué es y cómo corregirlo.

### Paso 8 · Registra una orden de producción
**Menú Órdenes de producción → Nueva orden.** Número, producto, periodo, fecha y cantidad planeada. Ábrela con **Ver** y registra lo que **realmente** se usó:

<img width="1100" height="1067" alt="09-orden-abierta" src="https://github.com/user-attachments/assets/34ee2dae-db40-4a9e-8ba7-cd0136831860" />


- **Consumo real de materiales:** cantidad y precio reales (**Agregar consumo**).
- **Horas de mano de obra directa:** trabajador, horas y tarifa reales (**Agregar registro**).
- **CIF real de la orden:** lo que costó cada concepto (**Agregar**).

### Paso 9 · Cierra la orden y lee las variaciones
En «Cerrar orden y calcular costo real», escribe la **cantidad producida** y pulsa **Cerrar orden**. Margia calcula el costo real y **seis variaciones**:

<img width="1100" height="570" alt="10-orden-cerrada" src="https://github.com/user-attachments/assets/e3764114-b237-4fe7-bb40-1bf96371d44a" />


| Variación | Qué te dice |
|---|---|
| **Precio de materiales** | Pagaste más (o menos) que el precio estándar. |
| **Cantidad de materiales** | Usaste más (o menos) material del que la receta permite. |
| **Tarifa de mano de obra** | La hora costó más (o menos) que la tarifa estándar. |
| **Eficiencia de mano de obra** | Se tardó más (o menos) de las horas estándar. |
| **Presupuesto de CIF** | Los costos indirectos reales difieren de lo presupuestado. |
| **Volumen de CIF** | Se produjo un volumen distinto al presupuestado. |

Un monto **positivo** y marcado *desfavorable* significa que **costó más de lo estándar**; uno **negativo** y *favorable*, que costó menos. Así sabes **qué corregir**, no solo que costó más.

> **Cerrar una orden** descuenta del inventario lo consumido y la bloquea para edición. Si te equivocaste, el administrador puede reabrirla con su código (ver [sección 9](#9-trabajar-en-equipo-usuarios-permisos-y-correcciones)).

Al cerrar tu **primera** orden, la guía desaparece y el Dashboard empieza a mostrar indicadores.

---

## 7. Cada día: tablero, inventario y reportes

**Dashboard.** Compara el costo estándar con el real de tus últimas órdenes, suma las variaciones y dibuja un gráfico por orden. Puedes filtrar por producto y por periodo.

<img width="1100" height="1003" alt="11-dashboard" src="https://github.com/user-attachments/assets/18108607-75bd-4029-b702-15a0c01c6e89" />


**Inventario.** Existencias valoradas a costo promedio ponderado, con alerta cuando algo baja de su mínimo. Con **Registrar movimiento** anotas compras (entradas) y salidas; cada materia tiene su **Kardex**.

<img width="1100" height="705" alt="12-inventario" src="https://github.com/user-attachments/assets/00828202-c9c6-45ab-bf5d-624fad9e1646" />


**Reportes.** Cada reporte se descarga en **Excel** o **PDF**, o se ve en **Vista previa** para imprimir: hoja de costos, materiales, mano de obra, CIF, producción, variaciones, inventario, histórico del costo estándar y estado de costos de producción. Los PDF llevan el logo y los colores de tu empresa.

<img width="1100" height="528" alt="13-reportes" src="https://github.com/user-attachments/assets/cc606b0a-f76d-4bb6-a3d9-381e7531d36d" />


**Histórico de costos.** Al cerrar un periodo, guarda el costo estándar de cada producto y compáralo con otros periodos, con flechas de subida y bajada. Así ves si tus costos van mejorando o empeorando.

---

## 8. Importar y exportar con Excel

Casi todas las pantallas tienen **«Exportar a Excel»** e **«Importar desde Excel»**: empresas, periodos, unidades, centros de costo, productos, materias primas, mano de obra, bases y conceptos de CIF, recetas (Hoja de costo) y órdenes de producción.

<img width="1100" height="687" alt="14-importar-excel" src="https://github.com/user-attachments/assets/9ad1b934-dfd5-471c-9cd3-708d4a92ed14" />


1. **Descarga la plantilla** desde esa misma ventana (trae los títulos correctos, un ejemplo y listas desplegables con *tus* códigos). La carpeta `plantillas` también trae una de cada módulo.
2. Llénala con **una fila por registro**.
3. Elige el archivo: Margia muestra una **vista previa** de qué se crea, qué se actualiza y qué filas tienen errores, con la explicación de cada uno. **No guarda nada hasta que confirmas.**

Un archivo exportado tiene el mismo formato que la plantilla: puedes **exportar, corregir en Excel y volver a importar** marcando «actualizar». Si ya tienes tus datos en Excel, impórtalos en el mismo orden de la ruta de 9 pasos.

---

## 9. Trabajar en equipo: usuarios, permisos y correcciones

**Usuarios y permisos.** En **Usuarios → Nuevo usuario** el administrador crea cuentas y elige, **módulo por módulo**, qué puede crear, editar o eliminar. Todo lo demás queda en solo consulta.

<img width="1100" height="954" alt="15-usuarios" src="https://github.com/user-attachments/assets/5d5920c4-d882-46c0-9a92-781c48e30e49" />


**Actividad.** El menú Actividad registra quién hizo qué y cuándo, incluidos los intentos de acceso fallidos.

**Corregir órdenes con un código.** Editar los datos de una orden, **reabrir** una orden cerrada o **eliminar** una orden solo se puede con un **código de autorización** que crea el administrador (botón **«Código de autorización»** en Órdenes de producción). Al reabrir una orden cerrada se descartan su costo real y sus variaciones y el inventario descontado vuelve a la bodega; al cerrarla otra vez todo se recalcula. Cada corrección queda en Actividad, con lo que cambió y el motivo.

---

## 10. Respaldos

- Tu información está en **`data\costos.db`**, un solo archivo. Para moverla a otro computador, copia la carpeta `data`.
- Margia hace **una copia automática diaria** cada vez que se abre, en `data\respaldos` (conserva las últimas 14). La primera vez que lo abres todavía no hay nada que copiar; la primera copia aparece al abrirlo por segunda vez.
- Con el menú **Respaldo** (solo administrador) descargas una copia cuando quieras y puedes **restaurar** una. **Guarda copias fuera de este computador** (memoria USB o la nube).

<img width="1100" height="488" alt="16-respaldo" src="https://github.com/user-attachments/assets/78a6aefe-a115-4961-9eb9-8740a7d6f011" />


---

## 11. Usarlo desde otros computadores de la red (opcional)

Por defecto Margia solo se abre en el computador donde corre. Para que otros equipos de tu local entren por el navegador:

1. Primero cambia la contraseña de `admin`. Si no, **Margia se niega a abrirse a la red** (por seguridad).
2. En `config\config.ini` pon `host = 0.0.0.0` y reinicia el programa.
3. La ventana negra mostrará las direcciones para los demás equipos (`http://192.168.x.x:8765/`). Es posible que Windows pida permiso en el firewall.

La conexión **no está cifrada**: úsalo solo en una red de confianza, nunca expuesto a internet. Más detalles en `docs/DESPLIEGUE.md`.

---

## 12. Cómo sacarle el máximo provecho

**Para que el costo sea correcto** (los errores más comunes)
- **Horas por unidad = tiempo de una sola unidad.** Si pones el tiempo de toda la tanda, la mano de obra sale inflada y todo parece pérdida.
- **Horas por mes = las del mes** (unas 192), no las de la semana (48) ni los días (30).
- **Solo trabajadores que producen** en «Mano de obra directa».
- **CIF y unidades presupuestadas del mismo periodo:** si cargas el arriendo del año pero las unidades de un mes, cada producto carga 12 veces lo que le toca.
- **Carga todos los costos indirectos.** Con el CIF en cero el margen sale más alto que el real.
- **Mira los avisos amarillos:** te dicen cuando un CIF no se está aplicando porque a ningún producto se le cargó su base.

**Para que sea útil**
- **Cierra cada orden con datos reales**, incluidos los precios a los que de verdad compraste.
- **Lee las variaciones de cada orden:** una desfavorable en cantidad de materiales pide revisar desperdicio; en precio, renegociar con el proveedor; en eficiencia, revisar el proceso.
- **Revisa el costo estándar de vez en cuando** (cuando suban los insumos o el salario) y **guarda el histórico** al cerrar cada periodo.
- **Compara el precio de venta con el precio sugerido** de cada producto.
- **Fija existencias mínimas** para que el inventario te avise a tiempo.

**Para cuidar tu información**
- Cambia las contraseñas de fábrica y crea un segundo administrador.
- Da a cada persona solo los permisos que necesita.
- Guarda **respaldos fuera del computador**.

---

## 13. Si algo falla

| Qué ves | Qué hacer |
|---|---|
| «python» no se reconoce como un comando | Vuelve a instalar Python marcando **Add python.exe to PATH**, o prueba con `py iniciar.py`. |
| «Falta la librería openpyxl» (o reportlab) | Ejecuta `python -m pip install -r requirements.txt`. |
| El navegador no se abre solo | Copia en el navegador la dirección que muestra la ventana negra (`http://127.0.0.1:8765/`). |
| «No se pudo abrir el puerto 8765: otro programa lo está usando» | Cambia `puerto` en `config\config.ini` (por ejemplo a `8766`) y vuelve a abrirlo. |
| La ventana negra se cierra sola al arrancar | Abre `data\margia_errores.log`: ahí queda el motivo. Envíaselo a quien te instaló el programa. |
| «Tu sesión terminó» | Entra de nuevo. También pasa cada vez que se reinicia el programa. |
| «Demasiados intentos fallidos» | Esa cuenta quedó bloqueada: espera el tiempo que indica el mensaje (1 minuto) e inténtalo otra vez. Las demás cuentas no se afectan. |

Más soluciones y la instalación en detalle: `docs/DESPLIEGUE.md`.

**Cerrar el programa:** pulsa `Ctrl+C` en la ventana negra, o ciérrala. Cerrar solo el navegador **no** apaga el programa; para volver a entrar abre `http://127.0.0.1:8765/` o ejecuta `python iniciar.py` otra vez (si ya estaba abierto, simplemente te abre el navegador). Al cerrar y abrir **no se pierde nada**.

---

## 14. Más información

Todos estos archivos vienen **dentro del paquete `margia.zip`**.

- `docs/MANUAL_USUARIO.md` — cómo usar cada pantalla, con más detalle.
- `docs/DESPLIEGUE.md` — instalar, usar en red, respaldar, actualizar y resolver problemas.
- `docs/COMPARTIR.md` — cómo compartir Margia con otras personas (descarga y página web).
- `docs/MANUAL_TECNICO.md` — arquitectura, modelo de datos y cómo extenderlo.
- `docs/MARCA.md` — nombre, frase, logo y colores.
- `tests/README.md` — pruebas automáticas.

**Para desarrolladores.** Margia es Python (servidor `http.server`, base SQLite) y una interfaz en HTML, CSS y JavaScript sin librerías externas: no carga nada de internet. Las pruebas se ejecutan con los scripts de `tests/` (ver `tests/README.md`).

---

<img width="3587" height="320" alt="margia-logo-lema-blanco" src="https://github.com/user-attachments/assets/f566658d-dd0b-4131-8a12-f4d879c8662e" />


