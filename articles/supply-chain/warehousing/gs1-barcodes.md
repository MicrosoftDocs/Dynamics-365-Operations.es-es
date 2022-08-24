---
title: Códigos de barras GS1
description: En este artículo se describe cómo configurar códigos de barras GS1 y códigos QR para que las etiquetas se puedan escanear en un almacén.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 34f74c2a889b3a659831897897e2086b277256e0
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219790"
---
# <a name="gs1-bar-codes"></a>Códigos de barras GS1

[!include [banner](../includes/banner.md)]

A menudo, los trabajadores del almacén tienen que realizar varias tareas cuando utilizan un escáner de dispositivo móvil para registrar los movimientos de un artículo, palé o contenedor. Estas tareas pueden incluir tanto escanear códigos de barras como introducir manualmente información en el dispositivo móvil. Los códigos de barras utilizan un formato específico de la empresa que usted define y administra mediante Microsoft Dynamics 365 Supply Chain Management.

Los códigos de barras GS1 para etiquetas de envío se desarrollaron para proporcionar un estándar global para el intercambio de datos entre empresas. Están disponibles en simbologías lineales (1D) (formatos de códigos de barras), como GS1-128, y simbologías 2D, como GS1 DataMatrix y códigos QR GS1. Los códigos de barras GS1 no solo codifican los datos, sino que también le permiten usar una lista predefinida de *identificadores de aplicación* para definir el significado de esos datos. El estándar GS1 define el formato de datos y los diversos tipos de datos que se pueden usar para la codificación. A diferencia de los códigos de barras estándar más antiguos, los códigos de barras GS1 pueden tener varios elementos de datos. Por tanto, un solo escaneo de código de barras puede capturar varios tipos de información del producto, como el lote y la fecha de vencimiento.

La compatibilidad con GS1 en Supply Chain Management simplifica drásticamente el proceso de escaneo en los almacenes donde los palés y contenedores se etiquetan usando códigos de barras en formato GS1. Los trabajadores del almacén pueden extraer toda la información necesaria con un solo escaneo de un código de barras GS1. Al eliminar la necesidad de realizar varios escaneos y de introducir información manualmente, los códigos de barras GS1 ayudan a reducir el tiempo asociado a las tareas. Al mismo tiempo, también ayudan a mejorar la precisión.

Los directores de logística deben configurar la lista necesaria de identificadores de aplicación y asociar cada uno de ellos a los elementos del menú del dispositivo móvil correspondientes. Entonces, los identificadores de aplicación se pueden utilizar en los almacenes como una configuración global para fines de desplazamiento y embalaje. Por tanto, todas las etiquetas de envío tendrán un formato unificado.

A menos que se indique lo contrario, en este artículo se utiliza el término *código de barras* para hacer referencia tanto a los códigos de barras lineales (1D) como a los códigos de barras 2D.

## <a name="the-gs1-bar-code-format"></a>Formato de código de barras GS1

Las especificaciones generales de GS1 especifican qué simbologías se pueden usar para los códigos de barras GS1 y cómo codificar los datos en el código de barras. Esta sección proporciona una breve introducción al artículo. Para obtener detalles completos, consulte las [Especificaciones Generales de GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf) que publica GS1. El documento de especificaciones de GS1 se actualiza regularmente y la información que proporciona está actualizada con la versión 22.0 de las especificaciones generales de GS1.

Los códigos de barras GS1 utilizan las siguientes simbologías:

- **Códigos de barras lineales o 1D**: GS1-128 y GS1 DataBar
- **Códigos de barras 2D**: GS1 DataMatrix, Código QR GS1 y GS1 Dotcode

Tenga en cuenta que hay menciones especiales de GS1 en GS1-128, que es un caso especial del código de barras lineal común Code-128, GS1 DataMatrix y Código QR GS1. La diferencia entre la versión GS1 y la versión no GS1 es la presencia de un carácter especial (FNC1) como primer carácter en los datos del código de barras. La presencia de un carácter FNC1 indica que los datos del código de barras deben interpretarse de acuerdo con la especificación GS1.

Los datos del propio código de barras consisten en múltiples elementos de datos, cada uno de los cuales está identificado por un identificador de aplicación al comienzo del campo. Por lo general, los datos también se presentan bajo el código de barras en un formato legible por humanos, donde el identificador de la aplicación se muestra entre paréntesis. Este es un ejemplo: `(01) 09521101530001 (17) 210119 (10) AB-123`. Este código de barras contiene tres elementos:

- **Identificador de aplicación 01**: el número de artículo comercial global (GTIN) GS1 del artículo.
- **Identificador de aplicación 17**: la fecha de expiración.
- **Identificador de aplicación 10**: el número de lote.

Para cada elemento, los datos pueden tener una longitud predefinida o una longitud variable. Hay una lista fija de identificadores de aplicaciones que tienen longitudes predefinidas. Todos los demás identificadores de aplicaciones tienen una longitud variable, y la lista de identificadores de aplicaciones GS1 especifica la longitud máxima y el formato de los datos. Por ejemplo, el identificador de aplicación 01 tiene una longitud predefinida de 16 caracteres (dos para el propio identificador de aplicación y luego 14 para el GTIN), y el identificador de aplicación 17 tiene una longitud predefinida de ocho caracteres (dos para el propio identificador de aplicación y luego seis para la fecha). Sin embargo, el identificador de aplicación 10 tiene dos números para el propio identificador de aplicación y luego hasta 20 caracteres alfanuméricos.

Cuando los elementos se juntan, si un elemento sigue a un elemento de longitud variable, se debe usar un carácter separador. Este separador puede ser el carácter especial FNC1 o el carácter separador de grupo (un carácter no imprimible que tiene el código ASCII 29 y el código hexadecimal 1D). El separador no debe usarse después del último elemento. Aunque el separador tampoco debe usarse después de elementos que tienen una longitud predefinida, su presencia no es un error crítico.

En los datos del código de barras del ejemplo anterior de un código de barras que contiene los identificadores de aplicación 01, 17 y 10, los datos en un código Code-128, código QR o símbolo DataMatrix se codificarán como `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (los identificadores de la aplicación se muestran en negrita). Como práctica recomendada, cualquier elemento que tenga una longitud variable debe colocarse al final, para eliminar la necesidad de un carácter separador de grupo adicional. Sin embargo, el código de barras también puede tener un orden diferente de elementos, cuando el separador sea obligatorio. Este es un ejemplo: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Fechas y números decimales

Las fechas siempre se representan en formato *AAMMDD*, donde el siglo del año está determinado por las especificaciones GS1. Solo se pueden representar fechas desde 49 años en el pasado hasta 50 años en el futuro (en relación con el año actual).

Algunos elementos de datos contienen números decimales. Por ejemplo, los identificadores de aplicación 3100, 3101,... 3105 representan un peso neto en kilogramos. Debido a que estos identificadores de aplicación tienen una longitud predefinida de 10, hay seis números disponibles para la cantidad. La posición del punto decimal se especifica mediante el último número del identificador de la aplicación. Por lo tanto, esta familia de identificadores de aplicación también se puede representar como *310n*. Debido a que el estándar GS1 especifica que siempre debe haber al menos un número a la izquierda del punto decimal, se permite un máximo de cinco decimales.

Aquí hay algunos ejemplos que muestran cómo el número *123456* será interpretado por diferentes identificadores de aplicación (mostrados en negrita):

- **`3100`**`123456` &rarr; 123456 (entero)
- **`3101`**`123456` &rarr; 12345,6 (un decimal)
- **`3102`**`123456` &rarr; 1234,56 (dos decimales)
- **`3103`**`123456` &rarr; 123,456 (tres decimales)
- **`3104`**`123456` &rarr; 12,3456 (cuatro decimales)
- **`3105`**`123456` &rarr; 1,23456 (cinco decimales)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Escanear códigos de barras GS1 en Supply Chain Management

Para escanear códigos de barras GS1, los trabajadores del almacén utilizan un escáner integrado o conectado a un dispositivo móvil. Luego, el escáner transmite el código de barras escaneado a la aplicación móvil Warehouse Management como una serie de eventos de teclado. Este modo de operación también se conoce como *cuña de teclado* o *cuña*. Luego, la aplicación móvil envía el texto recibido tal cual a Supply Chain Management. Cuando el sistema recibe datos de entrada, primero determina si los datos comienzan con uno de los prefijos configurados que indican que los datos son en realidad un código de barras GS1 (consulte la sección [Configurar opciones globales de GS1](#set-gs1-options)). Si los datos escaneados comienzan con uno de esos prefijos, el sistema utiliza un analizador GS1 para analizar los datos y extraer elementos de datos individuales, de acuerdo con sus identificadores de aplicación. Una vez analizados los datos, el campo de entrada actual o varios campos se rellenarán con los datos escaneados.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Configuración del hardware y software del escáner de código de barras

Para que Supply Chain Management reconozca y decodifique correctamente los códigos de barras GS1, el escáner de hardware o el software de soporte deben estar configurados para realizar las siguientes acciones:

- Agregue un prefijo a los códigos de barras escaneados, para que el sistema pueda reconocer un código de barras GS1.
- Convierta el carácter separador de grupo ASCII no imprimible (código ASCII 29 o código hexadecimal 1D) en un carácter imprimible, como una tilde (~).

Aunque puede agregar cualquier prefijo al código de barras escaneado, una opción es agregar un identificador de simbología ISO/IEC 15424, también conocido como *Identificador de AIM*. Este identificador de tres caracteres comienza con `]`, luego tiene un carácter que identifica la simbología que se usa y luego tiene un número que se usa como un modificador adicional. Por ejemplo, el identificador AIM `]C1` especifica un código de barras Código 128 (debido al carácter `C`), y el modificador `1` especifica que hay un carácter FNC1 en la primera posición de los datos. Por otro lado, `]C0` es un código de barras Código 128 que tiene cualquier otro carácter como primer carácter de los datos.

Los siguientes cinco identificadores de simbología corresponden a códigos de barras GS1 que tienen elementos de identificación de aplicación:

- `]C1`: código 128 (`C`) con el carácter FNC1 en primera posición (`1`), también conocido como GS1-128.
- `]e0`: GS1 DataBar.
- `]d2`: DataMatrix (`d`) con ECC 200 y FNC1 en primera posición (`2`), también conocido como GS1 DataMatrix.
- `]Q3`: símbolo modelo 2 (`Q`) de código QR con FNC1 en primera posición (`3`), también conocido como Código QR GS1.
- `]J1`: GS1 DotCode.

Si usa estos identificadores, la compatibilidad con códigos de barras que no son GS1 requiere que los escáneres o el software de escaneo estén configurados para eliminar cualquier identificador que no corresponda a los identificadores GS1. Por ejemplo, si escanea un código de barras Código 39 "normal", se añadirá el prefijo `]A0`. Debido a que el sistema no entenderá este prefijo como uno de los prefijos GS1, lo interpretará como un dato y producirá resultados inesperados.

> [!NOTE]
> Para mayor comodidad, la versión 2.0.17.0 y posteriores de la aplicación móvil Warehouse Management eliminarán los prefijos de AIM que no estén incluidos en la lista anterior. Este comportamiento admite casos en los que puede configurar el escáner para agregar el prefijo AIM, pero no para eliminar los prefijos no deseados.

### <a name="single-and-multiple-field-scanning"></a>Escaneo de campo único y múltiple

Después de analizar los datos del código de barras, se introducirán en los controles de flujo del dispositivo móvil. Hay dos métodos que se procesarán a su vez:

- **Escaneo de campo único**: este método rellena solo el campo en el que se escaneó el código de barras. Por ejemplo, si escanea el código de barras `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` mientras el cursor está en el campo **Artículo**, el GTIN `09521101530001` del código de barras se introducirá en ese campo. Si escanea el mismo código de barras mientras el cursor está en el campo **Id. de lote**, se introducirá el número de lote `AB-123` del código de barras. Este modo funciona para todos los campos y en todos los flujos, y solo requiere que se configure la configuración genérica de GS1. Si un código de barras contiene varios elementos, debe escanearse varias veces, ya que solo se introducirá una parte del código de barras a la vez en el flujo del dispositivo móvil. Este comportamiento está controlado por la configuración genérica de GS1, como se describe en la sección [Establecer la configuración genérica de GS1](#generic-gs1-setup).
- **Escaneo de múltiples campos**: este método completa varios campos cuando se escanea un código de barras, al introducir datos adicionales en el estado de flujo del dispositivo móvil. Por ejemplo, la directiva está configurada para insertar el identificador de aplicación 01 en el control `ItemId` y el identificador de aplicación 10 en el campo `InventBatchId`. En este caso, si escanea el código de barras `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, los datos de ambas variables se enviarán al mismo tiempo. Por lo tanto, el sistema no le solicitará el artículo ni el número de lote en el flujo. Este comportamiento está controlado por las directivas de GS1 que están vinculadas a los elementos del menú, como se describe en la sección [Configurar las directivas de GS1 para que estén en los elementos del menú del dispositivo móvil](#policies-for-menus) sección.

> [!WARNING]
> Las directivas predeterminadas de GS1 han sido probadas para funcionar sin comportamientos inesperados. Sin embargo, la personalización de las directivas GS1 que están vinculadas a los elementos del menú puede causar un comportamiento inesperado, ya que el flujo podría no esperar que algunos datos estén disponibles en un momento determinado.

## <a name="turn-on-the-gs1-feature"></a>Activar la característica GS1

Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Escanear códigos de barras GS1*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Activar la función Analizador mejorado para la característica de códigos de barras GS1

Si usa códigos de barras GS1, le recomendamos que también active la característica *Analizador mejorado para códigos de barras GS1*. Esta característica proporciona una implementación mejorada del analizador de códigos de barras GS1. Añade las siguientes mejoras:

- Sigue el algoritmo de especificación general GS1 para el análisis de datos de símbolos y valida que los datos del símbolo sean válidos de acuerdo con la especificación.
- No requiere que usted configure un valor **Longitud máxima del identificador** y utiliza la coincidencia de prefijo más larga de los identificadores de aplicación configurados.
- Le permite configurar más fácilmente identificadores de aplicaciones decimales usando la letra *n* para hacer coincidir cualquier número. Por ejemplo, puede configurar solo un identificador de aplicación (*310n*) en lugar de identificadores de aplicación independientes (*3101*, *3102*, *3103* y así sucesivamente).
- Soluciona un problema en el que los datos codificados incorrectamente se interpretan como datos de campo.
- Viene como una clase separada que se puede reutilizar en otros contextos y permite que se use un punto de extensibilidad para manipular los datos escaneados antes de que rellenar los campos de flujo.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Configurar opciones globales de GS1

La página **Parámetros de gestión de almacén** proporciona algunas configuraciones que establecen las opciones globales de GS1.

Siga estos pasos para configurar opciones globales de GS1.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la ficha desplegable **Códigos de barras**, establezca los siguientes campos:

    - **Carácter FNC1**, **Carácter de Datamatrix** y **Carácter de código QR**: especifican los caracteres que deben interpretarse como un prefijo para cada tipo de código de barras GS1.
    - **Separador de grupos**: especifique el carácter que reemplaza al carácter separador de grupo ASCII.
    - **Longitud máxima del identificador**: especifique el número máximo de caracteres permitido para el identificador de aplicación. Este campo no es obligatorio si la característica *Analizador GS1 mejorado* está activada en su sistema.

> [!NOTE]
> Los prefijos indican al sistema que un código de barras está codificado según el estándar GS1. Se pueden utilizar hasta tres prefijos (**Carácter FNC1**, **Carácter Datamatrix** y **Carácter de código QR**) simultáneamente y para diversos fines.

## <a name="gs1-application-identifiers"></a>Identificadores de la aplicación de GS1

Los formatos GS1 no solo codifican los datos, sino que también le permiten usar una lista predefinida de identificadores de aplicación para definir el significado de los datos. Los directores de logística deben configurar la lista necesaria de identificadores de aplicación y asociar cada uno de ellos a los elementos del menú del dispositivo móvil correspondientes. Entonces, los identificadores se pueden utilizar en los almacenes como una configuración global para fines de desplazamiento y embalaje. Por tanto, todas las etiquetas de envío tendrán un formato unificado.

El sistema utiliza los datos, especialmente los identificadores de aplicación predefinidos, para establecer las reglas que deben aplicarse a la información escaneada relevante.

Cada identificador de aplicación indica al sistema que los caracteres siguientes del código de barras escaneado deben considerarse un bloque de información cifrada. La configuración de los identificadores de aplicación define cómo el sistema debe interpretar un código de barras y guardarlo como un valor en el sistema.

Los directores de logística pueden utilizar identificadores de aplicación internacionales estándar o crear los suyos propios.

### <a name="load-the-standard-application-identifiers"></a>Cargar los identificadores de aplicación estándar

Para comenzar rápidamente, puede cargar una lista de identificadores de aplicación internacionales comunes. Puede ampliar o editar la lista más tarde, según según necesario.

Para cargar los identificadores de aplicación estándar, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> GS1 \> Identificadores de aplicación GS1**.
1. En el panel de acciones, seleccione **Crear configuración predeterminada**.

> [!WARNING]
> El comando **Crear configuración predeterminada** elimina todos los identificadores de aplicación definidos actualmente y los reemplaza con la lista estándar. Sin embargo, después de cargar la configuración predeterminada, puede personalizar la lista según sus necesidades.

### <a name="set-up-custom-application-identifiers"></a>Configurar identificadores de aplicación personalizados

Si algunos o todos los identificadores de aplicación que utiliza su empresa difieren del conjunto estándar, puede crear sus propios códigos desde cero o personalizar el conjunto estándar según sus necesidades.

Para configurar y personalizar sus propios identificadores de aplicación GS1, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> GS1 \> Identificadores de aplicación GS1**.
1. Siga uno de estos pasos:

    - Para crear un nuevo identificador: en el panel de acciones, seleccione **Nueva**.
    - Para editar un identificador existente: seleccione el identificador y después, en el panel de acciones, seleccione **Editar**.

1. Configure los siguientes campos para el identificador nuevo o seleccionado:

    - **Identificador de aplicación**: escriba el código de identificación para el identificador de aplicación. Normalmente, este código es un entero de dos dígitos, pero puede ser más largo. En los valores decimales, el último dígito indica el número de posiciones decimales. Para obtener más información, consulte la descripción de la casilla **Decimal** más adelante en esta lista. Si la característica *Analizador mejorado para códigos de barras GS1* está habilitada, puede crear un único identificador de aplicación para todas las variantes de lugares decimales usando la letra *n* como último carácter en el identificador de la aplicación. Por ejemplo, puede configurar solo un identificador de aplicación (*310n*) en lugar de un identificador de aplicación para cada número de lugares decimales (*3101*, *3102*, *3103* y así sucesivamente).
    - **Descripción**: especifique una breve descripción del identificador.
    - **Longitud fija**: active esta casilla si los valores que se escanean con este identificador de aplicación tienen un número fijo de caracteres. Desactive esta casilla si la longitud de los valores es variable. En este caso, debe indicar el final del valor utilizando el carácter separador de grupo que especificó en la página **Parámetros de gestión de almacenes**.
    - **Longitud**: indique el número máximo de caracteres que pueden aparecer en los valores que se escanean usando este identificador de aplicación. Si la casilla **Longitud fija** está activada, se espera exactamente este número de caracteres.
    - **Tipo**: seleccione el tipo de valor que se escanea utilizando este identificador de aplicación (*Numérico*, *Alfanumérico* o *Fecha*). Para obtener más información acerca de cómo se representan las fechas y los números en los datos de códigos de barras, consulte la sección [Fechas y números decimales](#dates-and-decimal-numbers).
    - **Decimal**: active esta casilla si el valor incluye un separador decimal implícito. Si se activa esta casilla, el sistema utilizará el último dígito del identificador de aplicación para determinar el número de decimales. Para obtener más información acerca de cómo se representan las fechas y los números en los datos de códigos de barras, consulte la sección [Fechas y números decimales](#dates-and-decimal-numbers).

> [!WARNING]
> Aunque el sistema le permitirá configurar la casilla **Longitud fija** para cualquier identificador de aplicación, debe usarse solo para el subconjunto de identificadores de aplicación que tengan una longitud predefinida según las Especificaciones Generales GS1. El analizador GS1 mejorado ya contiene la lista de todos los identificadores de aplicaciones que tienen longitudes predefinidas.

> [!NOTE]
> El valor **Separador de grupos** que se especifica en la página **Parámetros de gestión de almacenes** es opcional si un valor seguido de un identificador de aplicación tiene longitud fija.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Establecer la configuración genérica de GS1

La configuración genérica de GS1 establece una colección de asignaciones comunes. Estas asignaciones hacen coincidir cada campo de entrada relevante de la aplicación móvil con el identificador de aplicación que controla cómo se deben interpretar y almacenar los valores de los códigos de barras escaneados en ese campo. De forma predeterminada, esta configuración se aplica a todos los escaneos de todos los elementos de menú del dispositivo móvil. Sin embargo, una directiva GS1 asignada a un elemento de menú específico puede sobrescribirla para uno o más campos específicos.

La configuración genérica de GS1 solo permite escanear un valor cada vez. Por tanto, si desea cargar varios valores de campo de un solo escaneo, debe configurar una directiva GS1 para los elementos de menú relevantes.

Para obtener más información sobre las directivas GS1, consulte la próxima sección.

### <a name="load-the-standard-generic-gs1-setup"></a>Cargar la configuración genérica de GS1 estándar

La página **Configuración genérica de GS1** le permite cargar un conjunto estándar de asignaciones entre los campos del dispositivo móvil y los identificadores de aplicación estándar que crea la configuración predeterminada.

Para establecer la configuración genérica de GS1, vaya a **Gestión de almacenes \> Configuración \> GS1 \> Configuración genérica de GS1**. Seleccione **Crear configuración predeterminada** para asignar automáticamente un identificador de aplicación adecuado a cada campo que suelen utilizar los elementos de menú del dispositivo móvil.

> [!WARNING]
> Si ya existe alguna configuración genérica de GS1, el comando **Crear configuración predeterminada** lo elimina por completo y carga la configuración estándar.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personalizar la configuración genérica de GS1 estándar

Para personalizar la configuración genérica de GS1, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> GS1 \> Configuración genérica de GS1**.
1. Siga uno de estos pasos:

    - Para crear una nueva asignación: en el panel de acciones, seleccione **Nuevo**.
    - Para editar una asignación existente: seleccione la asignación y después, en el panel de acciones, seleccione **Editar**.

1. Configure los siguientes campos para la asignación nueva o seleccionada:

    - **Campo**: seleccione o especifique el campo de entrada de la aplicación móvil al que se debe asignar el valor entrante. El valor no es el nombre para mostrar que verán los trabajadores. Es el nombre de clave que se asigna al campo en el código subyacente. La configuración predeterminada proporciona una colección de campos que probablemente sean útiles e incluye nombres de clave intuitivos para cada campo y funciones programadas coincidentes. Sin embargo, es posible que deba hablar con sus socios de desarrollo para encontrar las selecciones correctas para su implementación.
    - **Identificador de aplicación**: seleccione el identificador de aplicación aplicable, tal como se define en la página **Identificadores de aplicación GS1**. El identificador establece cómo se interpretará y almacenará el código de barras como un valor para el campo con nombre. Después de seleccionar un identificador de aplicación, el campo **Descripción** muestra la descripción del mismo.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Configurar directivas GS1 para ser elementos de menú del dispositivo móvil

El propósito del estándar GS1 es permitir que los trabajadores carguen varios valores cuando escanean una vez un solo código de barras. Para lograr este propósito, los directores de logística deben configurar directivas GS1 que indiquen al sistema cómo interpretar los códigos de barras que contienen varios valores. Más tarde, puede asignar directivas a elementos de menú del dispositivo móvil para controlar cómo se interpretará un código de barras cuando los trabajadores lo escaneen mientras utilizan un elemento de menú específico.

Si no se asigna ninguna directiva GS1 a un elemento de menú, el sistema solo puede capturar un valor. Este valor se aplica a la entrada de la aplicación móvil que está seleccionada cuando el trabajador realiza el escaneo, según especifique la configuración genérica de GS1. Si se asigna una directiva GS1 al elemento de menú, el sistema sigue usando la configuración genérica de GS1 para asignar el primer valor del código de barras al campo seleccionado. Sin embargo, puede capturar después valores de campo adicionales, según especifique la directiva aplicable.

### <a name="load-the-standard-specific-gs1-policies"></a>Cargar las directivas específicas de GS1 estándar

Para comenzar rápidamente, puede cargar un conjunto de directivas GS1. Puede ampliar o editar las directivas más tarde, según según necesario.

Para cargar los identificadores de aplicación estándar, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> GS1 \> Directiva GS1**.
1. En el panel de acciones, seleccione **Crear configuración predeterminada**.

> [!WARNING]
> El comando **Crear configuración predeterminada** elimina todas las directivas definidas actualmente y las reemplaza con el conjunto de directivas estándar. Sin embargo, después de cargar la configuración predeterminada, puede personalizar las directivas según sus necesidades.

### <a name="set-up-custom-specific-gs1-policies"></a>Configurar directivas de GS1 específicas personalizadas

> [!WARNING]
> Es posible que algunas directivas de GS1 no funcionen con todos los flujos móviles que utilice. Cuando configura directivas GS1 personalizadas, debe probar el flujo del dispositivo móvil utilizando diferentes piezas de información que se escanean en diferentes puntos del flujo. De esta manera, puede determinar si el flujo se comporta como espera.

Siga estos pasos para configurar y personalizar sus directivas GS1.

1. Vaya a **Gestión de almacenes \> Configuración \> GS1 \> Directiva GS1**.
1. Siga uno de estos pasos:

    - Para crear una nueva directiva: en el panel de acciones, seleccione **Nuevo**.
    - Para editar una directiva existente: selecciónela en el panel de lista.

1. En el encabezado de la directiva nueva o seleccionada, establezca los siguientes campos:

    - **Nombre de directiva**: escriba un nombre para la directiva.
    - **Descripción**: especifique una breve descripción de la directiva.

1. En la ficha desplegable debajo del encabezado, asigne nombres de campo a identificadores de aplicación según sea necesario para la directiva actual. Utilice los botones de la barra de herramientas para agregar o quitar filas según sea necesario. Para cada fila, establezca los siguientes campos:

    - **Campo**: seleccione o especifique el campo de entrada de la aplicación móvil al que se debe asignar el valor entrante. El valor no es el nombre para mostrar que verán los trabajadores. Es el nombre de clave que se asigna al campo en el código subyacente. La configuración predeterminada proporciona una colección de campos que probablemente sean útiles e incluye nombres de clave intuitivos para cada campo y funciones programadas coincidentes. Sin embargo, es posible que deba hablar con sus socios de desarrollo para encontrar las selecciones correctas para su implementación.
    - **Identificador de aplicación**: seleccione el identificador de aplicación aplicable, tal como se define en la página **Identificadores de aplicación GS1**. El identificador establece cómo se interpretará y almacenará el código de barras como un valor para el campo con nombre. Después de seleccionar un identificador de aplicación, el campo **Descripción** muestra la descripción del mismo.
    - **Ordenación**: cada código de barras con varios valores incluye una serie de identificadores de aplicación, cada uno de los cuales va seguido de un valor. La directiva GS1 aplicable identifica qué identificador de aplicación se asigna a cada campo de la base de datos. Sin embargo, si un código de barras usa el mismo identificador de aplicación más de una vez, el sistema usa el orden en el que aparecen los identificadores de aplicación en el código para asignarlos a los campos. Para las filas que comparten un identificador de aplicación con una o más filas distintas, utilice este campo para establecer el orden en el que se procesan las filas coincidentes. La fila que tiene el valor de ordenación más bajo se procesará primero.

> [!NOTE]
> Para los códigos de barras que incluyen más de un identificador de aplicación idéntico, *debe* utilizar el campo **Ordenación** para establecer el orden de los campos.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Asignar directivas GS1 a elementos de menú del dispositivo móvil

De forma predeterminada, todos los elementos de menú de los dispositivos móviles proporcionan campos de entrada donde los trabajadores pueden escanear un solo valor, de acuerdo con la configuración genérica de GS1. Si desea que los trabajadores puedan escanear más de un valor de campo en una sola operación de escaneo para cualquier elemento de menú del dispositivo móvil, debe estos pasos para asignar una directiva de GS1.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Cree o abra un elemento de menú.
1. En la ficha desplegable **General**, establezca el campo **Directiva GS1** en la directiva que se aplica al elemento de menú.

## <a name="gs1-setup-example"></a>Ejemplo de configuración de GS1

Este ejemplo se aplica a un sistema en el que las opciones de GS1 están configuradas de la siguiente manera:

- En la página **Parámetros de gestión de almacenes**, se han establecido las siguientes configuraciones globales:

    - **Carácter FNC1:** *\]C1*
    - **Separador de grupos:** *\~*

- En la página **Identificadores de aplicación GS1**, los siguientes identificadores de aplicación son relevantes para este ejemplo.

    | Identificador de la aplicación | Descripción | Longitud fija | Longitud | Tipo | Decimal |
    |---|---|---|---|---|---|
    | 01 | GTIN | Seleccionadas | 14 | Numérico | Compensado |
    | 10 | Número de lote | Compensado | 20 | Alfanumérico | Compensado |
    | 17 | Fecha de expiración | Seleccionadas | 6 | Fecha | Compensado |
    | 30 | Cantidad de recepción | Compensado | 8 | Numérico | Compensado |

- En la página **Configuración genérica de GS1**, las siguientes configuraciones para la directiva genérica de GS1 son relevantes para este ejemplo.

    | Campo | Identificador de la aplicación | Descripción |
    |---|---|---|
    | ItemId | 01 | GTIN |

- En la página **Directiva GS1**, hay una directiva en la que el campo **Nombre de directiva** está configurado en *Recepción de compra*. Esta directiva incluye las siguientes líneas.

    | Campo | Identificador de la aplicación | Descripción | Ordenación |
    |---|---|---|---|
    | ExpDate | 17 | Fecha de expiración | 0 |
    | InventBatchId | 10 | Número de lote | 0 |
    | Cant. | 30 | Cantidad de recepción | 0 |

- En la página **Elementos de menú del dispositivo móvil** hay un elemento de menú que se llama *Recepción de compra*. Su campo **Directiva GS1** está configurado en *Recepción de compra*.

Una vez que las mercancías para un pedido de compra llegan al almacén, el trabajador sigue estos pasos.

1. En el dispositivo móvil, selecciona el elemento de menú **Recepción de compra**.
1. Escribe el número de pedido de compra.
1. Seleccione el campo **Artículo** y escanee el siguiente código de barras: `]C10100000012345678~3030~10b1~17220215`.

Debido a la configuración establecida para este ejemplo, el sistema analiza el código de barras escaneado de la siguiente manera.

| Clave de campo | Id. de la aplicación | Valor | Billete |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Como el trabajador escaneó el campo **Artículo**, el primer valor del código de barras se asigna a ese campo. La asignación se toma de la configuración genérica de GS1. |
| Cant. | 30 | 30 | Puesto que se capturan varios valores de campo en un solo escaneo, esta asignación y todas las asignaciones restantes se toman de la directiva GS1 asignada al elemento de menú **Recepción de compra**. Este valor es la cantidad que se ha recibido. |
| InventBatchId | 10 | b1 | Este valor es el identificador de lote. |
| ExpDate | 17 | 220215 | El formato de fecha es AAMMDD. Por tanto, la fecha de caducidad es el 15 de febrero de 2022. |

A continuación, se registra la recepción y se introducen los valores relevantes de la base de datos después del escaneo único.
