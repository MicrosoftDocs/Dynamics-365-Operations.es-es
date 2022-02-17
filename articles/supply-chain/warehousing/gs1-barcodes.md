---
title: Códigos de barras GS1 y códigos QR
description: En este tema se describe cómo configurar códigos de barras GS1 y códigos QR para que las etiquetas se puedan escanear en un almacén.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 702985ef9726690829e35e43d270477be318fc41
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075223"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>Códigos de barras GS1 y códigos QR

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- Preview until 10.0.25 GA -->

A menudo, los trabajadores del almacén tienen que realizar varias tareas cuando utilizan un escáner de dispositivo móvil para registrar los movimientos de un artículo, palé o contenedor. Estas tareas pueden incluir tanto escanear códigos de barras como introducir manualmente información en el dispositivo móvil. Los códigos de barras utilizan un formato específico de la empresa que usted define y administra mediante Microsoft Dynamics 365 Supply Chain Management.

Los formatos de código de barras GS1 y código QR para etiquetas de envío se desarrollaron para proporcionar un estándar global para el intercambio de datos entre empresas. Los formatos GS1 no solo codifican los datos, sino que también le permiten usar una lista predefinida de *identificadores de aplicación* para definir el significado de los datos. El estándar GS1 define el formato de datos y los diversos tipos de datos que se pueden usar para la codificación. A diferencia de los códigos de barras más antiguos, los códigos de barras GS1 pueden tener varios elementos de datos. Por tanto, un solo escaneo de código de barras puede capturar varios tipos de información del producto, como el lote y la fecha de vencimiento.

La compatibilidad con GS1 en Supply Chain Management simplifica drásticamente el proceso de escaneo en los almacenes donde los palés y contenedores se etiquetan usando códigos en formato GS1. Los trabajadores del almacén pueden extraer toda la información necesaria con un solo escaneo de un código de barras GS1. Al eliminar la necesidad de realizar varios escaneos y de introducir información manualmente, los códigos de barras GS1 ayudan a reducir el tiempo asociado a las tareas. Al mismo tiempo, también ayudan a mejorar la precisión.

Los directores de logística deben configurar la lista necesaria de identificadores de aplicación y asociar cada uno de ellos a los elementos del menú del dispositivo móvil correspondientes. Entonces, los identificadores de aplicación se pueden utilizar en los almacenes como una configuración global para fines de desplazamiento y embalaje. Por tanto, todas las etiquetas de envío tendrán un formato unificado.

A menos que se indique lo contrario, en este tema se utiliza el término *código de barras* para hacer referencia tanto a los códigos de barras como a los códigos QR.

## <a name="turn-on-the-gs1-feature"></a>Activar la característica GS1

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Escanear códigos de barras GS1*

## <a name="set-up-global-gs1-options"></a>Configurar opciones globales de GS1

La página **Parámetros de gestión de almacén** proporciona algunas configuraciones que establecen las opciones globales de GS1.

Siga estos pasos para configurar opciones globales de GS1.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la ficha desplegable **Códigos de barras**, establezca los siguientes campos:

    - **Carácter FNC1**: especifique los caracteres que deben interpretarse como un prefijo cuando se analiza un código de barras.
    - **Carácter Datamatrix**: especifique los caracteres que deben interpretarse como un prefijo cuando se analiza un Datamatrix.
    - **Carácter de código QR**: especifique los caracteres que deben interpretarse como un prefijo cuando se analiza un código QR.
    - **Separador de grupos**: especifique el carácter que identifica las distintas partes de un código de barras o un código QR.
    - **Longitud máxima del identificador**: especifique el número máximo de caracteres permitido para el identificador de aplicación.

> [!NOTE]
> Los prefijos indican al sistema que un código de barras está cifrado según el estándar GS1. Se pueden utilizar hasta tres prefijos (**Carácter FNC1**, **Carácter Datamatrix** y **Carácter de código QR**) simultáneamente y para diversos fines.

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

    - **Identificador de aplicación**: escriba el código de identificación para el identificador de aplicación. Normalmente, este código es un entero de dos dígitos, pero puede ser más largo. En los valores decimales, el último dígito indica el número de posiciones decimales. Para obtener más información, consulte la descripción de la casilla **Decimal** más adelante en esta lista.
    - **Descripción**: especifique una breve descripción del identificador.
    - **Longitud fija**: active esta casilla si los valores que se escanean con este identificador de aplicación tienen un número fijo de caracteres. Desactive esta casilla si la longitud de los valores es variable. En este caso, debe indicar el final del valor utilizando el carácter separador de grupo que especificó en la página **Parámetros de gestión de almacenes**.
    - **Longitud**: indique el número máximo de caracteres que pueden aparecer en los valores que se escanean usando este identificador de aplicación. Si la casilla **Longitud fija** está activada, se espera exactamente este número de caracteres.
    - **Tipo**: seleccione el tipo de valor que se escanea utilizando este identificador de aplicación (*Numérico*, *Alfanumérico* o *Fecha*). Para las fechas, el formato esperado es AAMMDD (sin espacios ni guiones).
    - **Decimal**: active esta casilla si el valor incluye un separador decimal implícito. Si se activa esta casilla, el sistema utilizará el último dígito del identificador de aplicación para determinar el número de decimales. Por ejemplo, si el identificador de aplicación es *3205*, los cinco dígitos situados más a la derecha del valor se interpretarán como si estuvieran después del separador decimal.

> [!NOTE]
> El separador de grupo que se especifica en la página **Parámetros de gestión de almacenes** es opcional si un valor que va seguido de un identificador de aplicación tiene una longitud fija, o si su longitud está maximizada (es decir, si la longitud es igual al valor **Longitud** que se establece para el identificador de aplicación).

## <a name="establish-the-generic-gs1-setup"></a>Establecer la configuración genérica de GS1

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

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Configurar directivas GS1 que puede asignar a elementos de menú del dispositivo móvil

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
1. Selecciona el campo **Artículo** y escanea el siguiente código de barras: *\]C10100000012345678\~3030\~10b1\~17220215*.

Debido a la configuración establecida para este ejemplo, el sistema analiza el código de barras escaneado de la siguiente manera.

| Clave de campo | Id. de la aplicación | Valor | Billete |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Como el trabajador escaneó el campo **Artículo**, el primer valor del código de barras se asigna a ese campo. La asignación se toma de la configuración genérica de GS1. |
| Cant. | 30 | 30 | Puesto que se capturan varios valores de campo en un solo escaneo, esta asignación y todas las asignaciones restantes se toman de la directiva GS1 asignada al elemento de menú **Recepción de compra**. Este valor es la cantidad que se ha recibido. |
| InventBatchId | 10 | b1 | Este valor es el identificador de lote. |
| ExpDate | 17 | 220215 | El formato de fecha es AAMMDD. Por tanto, la fecha de caducidad es el 15 de febrero de 2022. |

A continuación, se registra la recepción y se introducen los valores relevantes de la base de datos después del escaneo único.
