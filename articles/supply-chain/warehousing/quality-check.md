---
title: Control de calidad
description: Este tema proporciona información acerca de la característica Control de calidad. Esta característica permite que los trabajadores del almacén realicen verificaciones rápidas de calidad mientras reciben artículos en la zona del muelle de llegada.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: dfb71f74732d65409003c4f6f74145442a1efa3f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437251"
---
# <a name="quality-check"></a>Control de calidad

[!include [banner](../includes/banner.md)]

La característica *Control de calidad* permite que los trabajadores del almacén realicen verificaciones rápidas de calidad mientras reciben artículos en la zona del muelle de llegada. Estas comprobaciones puntuales son ventajosas cuando los trabajadores inspeccionan el embalaje u otras partes fácilmente reconocibles de un artículo. La característica guía a los trabajadores a echar un vistazo rápido para ver si algo está obviamente defectuoso o dañado antes de almacenar el inventario en su ubicación de almacenamiento.

Esta característica es una alternativa al proceso de control de calidad estándar. Ofrece más flexibilidad y un procesamiento más rápido.

Cuando utiliza esta función, el control de llegada y calidad se realiza de la siguiente manera:

1. Cuando llega un envío, un trabajador del almacén registra la llegada. El trabajador también escanea una matrícula de entidad de almacén para registrar la ubicación.
1. El trabajador realiza un rápido control de calidad y registra el resultado (aprobado o no) para esa matrícula de entidad de almacén.
1. Se produce una de las acciones siguientes:

    - Si se pasa el control de calidad, la matrícula de entidad de almacén se acepta y se lleva a un lugar de recepción, como de costumbre.
    - Si falla el control de calidad, la matrícula de entidad de almacén se rechaza y el trabajo de almacenamiento existente para ello se redirige a una ubicación alternativa para su posterior inspección. Se crea un nuevo pedido de calidad. Para ver el pedido de calidad creado a partir del control de calidad con error, vaya a **Gestión de inventarios \> Tareas periódicas \> Administración de la calidad \> Pedidos de calidad**.

Este proceso también se puede configurar para que todas las matrículas de entidad escaneadas se desvíen inmediatamente a la ubicación del control de calidad.

## <a name="turn-on-the-quality-check-feature"></a>Active la función de control de calidad

Antes de poder usar la característica *Control de calidad*, debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica**: *Control de calidad*

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configure la función para el escenario de ejemplo

Esta sección proporciona pautas y un ejemplo que muestra cómo configurar la característica *Control de calidad* y preparar datos de muestra para el escenario de ejemplo que se proporciona más adelante en este tema.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

### <a name="quality-check-template"></a><a name="quality-template"></a>Plantilla de control de calidad

La plantilla de control de calidad define las reglas para realizar controles rápidos de calidad en el momento de la recepción.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de control de calidad**.
1. Seleccione **Nuevo** para agregar una plantilla a la cuadrícula.
1. Establezca los siguientes valores para definir la plantilla nueva:

    - **Nombre de la plantilla de control de calidad**: *Comprobación de muelle*

        Especifique un nombre que identifique las políticas aplicadas para esta plantilla.

    - **Política de aceptación**: *Preguntar al usuario*

        Especifique si se debe solicitar a los usuarios que acepten o rechacen la calidad del inventario mientras procesan el trabajo, o si la calidad debe rechazarse automáticamente. Las opciones disponibles son *Rechazo automático* y *Preguntar al usuario*.

    - **Directiva de procesamiento de calidad**: *Crear orden de calidad*

        Seleccionar la directiva que se utilizará cuando se rechaza la calidad del inventario. Las siguientes opciones están disponibles:

        - *Crear solo trabajo*: simplemente se crea trabajo para facilitar el movimiento del inventario.
        - *Crear pedido de calidad*: crear un pedido de calidad para facilitar las pruebas de calidad.

    - **Grupo de prueba**: *Recinto*

        Especifique el grupo de prueba que se debe usar en el pedido de calidad que se crea. Los grupos de prueba se configuran en el módulo **Gestión de inventarios**.

        Deje desactivada la opción **Texto destructivo** para el grupo de prueba. Esta opción define si la muestra debe destruirse como parte de las pruebas del grupo de pruebas. Si se utiliza la prueba destructiva, el sistema genera una transacción de inventario cuando se crea el pedido de calidad para un artículo. La nueva transacción de inventario predice la reducción del inventario para la cantidad de la prueba. La reducción del inventario se produce cuando se completa el pedido de calidad a través del paso de validación. La transacción de inventario se identifica como pedido de calidad.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Clase de trabajo: control de calidad

Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil.

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. Seleccione **Nuevo** para crear una clase de trabajo.
1. Establezca los siguientes valores en el encabezado:

    - **Id. de la clase de trabajo**: *Control de calidad*

        Especifique un nombre que identifique la clase de trabajo.

    - **Descripción**: *Control de calidad*

        Escriba una breve descripción que indique para qué se utiliza la clase de trabajo.

    - **Tipo de orden de trabajo**: *Calidad en control de calidad*

        Seleccione el tipo de orden de trabajo que crea la clase de trabajo. Cuando configure el trabajo de control de calidad, seleccione siempre *Calidad en control de calidad*.

1. En la ficha desplegable **Tipos de ubicación de colocación válidos**, deje el campo **Tipo de ubicación** en blanco.

    Si selecciona un tipo de ubicación, limita las ubicaciones donde se pueden colocar los artículos después de que se seleccionan. El capo se usa cuando una directiva de ubicación intenta resolver la ubicación, o si un trabajador del almacén especifica manualmente la ubicación para el elemento de menú del dispositivo móvil.

Para obtener más información sobre las clases de trabajo y cómo crearlas, vea [Crear una clase de trabajo](tasks/create-work-class.md).

### <a name="work-template"></a>Plantilla de trabajo

La página Plantillas de trabajo le permite definir las operaciones de trabajo que se deben realizar en el almacén. Normalmente, las operaciones de trabajo del almacén constan de un par de acciones: un trabajador de almacén recoge inventario disponible en una ubicación y después pone el inventario seleccionado en otra ubicación. Una plantilla de trabajo para el control de calidad define las operaciones de trabajo para realizar controles de calidad.

#### <a name="purchase-orders"></a>Pedidos de compra

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el encabezado, establezca el campo **Tipo de orden de trabajo** en *Pedidos de compra*.
1. En el panel Acciones, seleccione **Editar**.
1. Seleccione una plantilla de trabajo que incluya un paso de control de calidad. En la sección **Visión general**, en el campo **Plantilla de trabajo**, seleccione *Recibo de 51 PO*.
1. En la sección **Detalles de plantilla de trabajo**, observe que la cuadrícula tiene dos líneas existentes: una para *Recoger* y otra para *Colocar*.
1. En la sección **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una fila para el control de calidad a la cuadrícula. Tenga en cuenta que el campo **Número de línea** para la nueva línea se establece en *3*.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados del resto de campos.

    - **Tipo de trabajo**: *Control de calidad*
    - **Id. de la clase de trabajo**: *Compra*
    - **Nombre de la plantilla de control de calidad**: *Comprobación de muelle*

        Seleccione el identificador único de la clase de trabajo. Usa este valor para configurar los elementos de menú en el dispositivo móvil y los tipos de trabajo que estos elementos de menú pueden procesar.

1. En el panel Acciones, seleccione **Guardar** para guardar su trabajo hasta ahora.

    Recibirá un mensaje informativo que dice: "No válido: el control de calidad debe realizarse directamente después de una selección". Por lo tanto, debe cambiar el valor **Número de línea** para la línea que acaba de agregar.

1. Siga estos pasos para cambiar el valor **Número de línea** para la nueva línea:

    1. En la sección **Detalles de plantilla de trabajo**, seleccione la línea donde el campo **Tipo de trabajo** se establece en *Control de calidad*.
    2. Seleccione el botón **Ascender** o **Descender** para mover la línea *Control de calidad* para que esté después de la línea *Recoger*.

1. En el panel Acciones, seleccione **Guardar**.

#### <a name="quality-in-quality-check"></a>Calidad en control de calidad

A continuación, cree una plantilla de trabajo para el control de calidad.

1. En el encabezado de la página **Plantillas de trabajo**, cambie el valor de **Tipo de orden de trabajo** a *Calidad en control de calidad*.
1. En el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula en la sección **Visión general**.
1. Establezca los siguientes valores en la fila nueva:

    - **Plantilla de trabajo**: *Control de calidad 51*

        Especifique un nombre para la plantilla.

    - **Descripción de plantilla de trabajo**: *Control de calidad 51*

1. En el panel Acciones, seleccione **Guardar** para tener disponible la sección **Detalles de plantilla de trabajo**.
1. Mientras la nueva plantilla todavía está seleccionada en la sección **Visión general**, seleccione **Nuevo** en la sección **Detalles de la plantilla de trabajo** para agregar una fila a la cuadrícula allí.
1. Establezca los siguientes valores en la fila nueva:

    - **Tipo de trabajo**: *Recoger*
    - **Id. de la clase de trabajo**: *Control de calidad*

        Seleccione el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.

1. En la sección **Detalles de la plantilla de trabajo**, vuelva a seleccionar **Nuevo** para agregar otra fila.
1. Establezca los siguientes valores en la fila nueva:

    - **Tipo de trabajo**: *Ubicar*
    - **Id. de la clase de trabajo**: *Control de calidad*

        Seleccione el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.

1. En el panel Acciones, seleccione **Guardar**.

Para obtener más información sobre las plantillas de trabajo, consulte [Controlar el trabajo de almacén con plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).

### <a name="location-directive--quality-failures"></a>Directiva de ubicación: Fallos de calidad

Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados. Debe configurar una regla de directiva de ubicación para definir cómo se manejarán los controles de calidad con error.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, configure el campo **Tipo de orden de trabajo** en *Pedidos de compra* para trabajar con directivas de ubicación de ese tipo.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva para controles de calidad.
1. Establezca los siguientes valores en el encabezado:

    - **Número de secuencia:** acepte el valor predeterminado.
    - **Nombre**: *51 a calidad*

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes. Acepte los valores predeterminados del resto de campos.

    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *5*
    - **Almacén**: *51*

1. En el panel Acciones, seleccione **Guardar** para guardar la directiva y que la ficha desplegable **Líneas** esté disponible.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados del resto de campos.

    - **Cantidad inicial**: *1*
    - **Cantidad final**: *1000000*

1. En el panel Acciones, seleccione **Guardar** para guardar la línea nueva y que la ficha desplegable **Acciones de directiva de ubicación** esté disponible.
1. Mientras la nueva línea todavía está seleccionada en la ficha desplegable **Líneas**, seleccione **Nuevo** en la ficha desplegable **Ubicación de acciones de directiva** para agregar una fila a la cuadrícula allí, para que pueda configurar una acción para la línea.
1. En la nueva fila, establezca el campo **Nombre** en *Calidad*. Acepte los valores predeterminados del resto de campos.
1. En el panel Acciones, seleccione **Guardar** para tener disponible el botón **Editar consulta** en la ficha desplegable **Acciones de directiva de ubicación**.
1. Si bien la línea que acaba de agregar todavía está seleccionada en la ficha desplegable **Ubicación de las acciones de directiva**, seleccione **Editar consulta**, para abrir un cuadro de diálogo donde puede editar la consulta de la acción.
1. En la pestaña **Intervalo**, seleccione **Agregar** para agregar una fila a la consulta.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo:** *Ubicación*
    - **Criterios**: *QMS*

    La ubicación *QMS* es una ubicación de almacén de calidad.

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. Ahora debe cambiar la secuencia de las directivas de ubicación de pedidos de compra para el almacén *51*. Guardar la nueva directiva de ubicación *51 a Calidad*, actualice la página y seleccione la directiva de ubicación en la lista. Luego use los botones **Ascender** y **Descender** en el panel Acciones para colocar la directiva de ubicación para el almacén *51* en el siguiente orden. (Antes de seleccionar **Ascender** o **Descender**, debe seleccionar una directiva de ubicación en la lista).

    1. 51 a Calidad
    2. 51 PO directo
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

Configure un elemento de menú para que los dispositivos móviles puedan realizar la función **Control de calidad**.

#### <a name="purchase-putaway"></a>Ubicación de compra

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En la lista, seleccione el elemento de menú **Ubicación de compra**.
1. En el panel Acciones, seleccione **Editar**.
1. En la sección **Clases de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Id. de la clase de trabajo**: *Control de calidad*

        Especifique el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.

    - **Tipo de orden de trabajo**: *Calidad en control de calidad*

1. En el panel Acciones, seleccione **Guardar**.

#### <a name="purchase-order-line-receiving"></a>Recepción de línea del pedido de compra

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento del menú:** *Recepción de línea de pedido*
    - **Título:** *Recepción de línea de pedido*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes. Acepte los valores predeterminados del resto de campos.

    - **Proceso de creación de trabajo** *Recepción y colocación de línea de pedido de compra*
    - **Generar matrícula de entidad de almacén:** *Sí*
    - **Plantilla de trabajo:**: *Recepción de 51 PO*

1. En el panel Acciones, seleccione **Guardar**.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Agregar el elemento de menú a un menú de dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En el panel de la izquierda, selección el menú **Entrada**.
1. En el panel Acciones, seleccione **Editar**.
1. En la columna **Menús disponibles y elementos de menú**, seleccione el nuevo elemento de menú **Recepción de línea de pedido**.
1. Seleccione el botón de flecha derecha para mover **Recepción de línea de pedido+** a la columna **Estructura del menú**.
1. En la columna **Estructura del menú**, seleccione **Recepción de línea de pedido** y luego seleccione el botón de flecha hacia arriba o hacia abajo para mover el elemento del menú a la posición deseada en el menú del dispositivo móvil.
1. En el panel Acciones, seleccione **Guardar**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Supuesto de ejemplo

Después de haber puesto a disposición todos los datos de ejemplo descritos anteriormente y configurarlos, puede trabajar en este escenario para probar la característica *Control de calidad*. Los valores que se muestran en este escenario suponen que está trabajando con los datos de demostración estándar, que seleccionó la entidad jurídica **USMF** y que preparó los registros de ejemplo que se describen anteriormente en este tema. Este escenario también sirve como ejemplo que muestra cómo se puede usar la característica en una configuración de producción.

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:

    - **Cuenta del proveedor:** *104*
    - **Almacén**: *51*

1. Seleccione **Aceptar** para crear el nuevo cuadro de diálogo y abrir el nuevo pedido de compras.
1. En la ficha desplegable **Líneas de pedido de ventas**, la cuadrícula contiene una nueva línea vacía. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *M9203*
    - **Cantidad:** *3*
    - **Unidad:** *PL*

1. En el panel Acciones, seleccione **Guardar**.

### <a name="process-quality-check-receiving"></a>Proceso de control de calidad de recepción

Una vez que se ha creado el pedido de compra, se puede recibir utilizando el elemento de menú **Recepción de línea de pedido** y la característica *Control de calidad*.

#### <a name="receive-pallet-1"></a>Recibir pallet1

1. Inicie sesión en la aplicación de almacén como un usuario en el almacén *51*. (Escriba *51* como el identificador de usuario y *1* como la contraseña).
1. Vaya a **Entrante \> Recepción de línea de pedido**.
1. En el campo **PONUM**, introduzca el número de orden de compra.
1. Confirme el número pedido de compra.
1. En el capo **LINENO**, escriba el número de la línea de pedido de compra que se está recibiendo. Debido a que el pedido solo tiene una línea en este escenario, especificará *1* en el campo **LINENO** para cada paso de recepción.
1. Confirmar el número de línea.
1. En el campo **CANT.**, indique la cantidad a recibir. Debido a que el pedido de compra es para tres pallets (*PL*) en este escenario, y hay tres pasos de recepción, ingresará *1* en el camp **CANT.** para cada paso de recepción.
1. Confirme la cantidad.

    La página **Control de calidad** que aparece no tiene campos de entrada. Solo tiene el botón de confirmación (marca de verificación) en la parte inferior y el botón Menú (**≡**) en la parte superior. (El botón Menú a veces se denomina hamburguesa o botón de hamburguesa). Para acelerar el proceso de control de calidad, cuando el pallet pase el control de calidad, el usuario simplemente confirma la página **Control de calidad**.

    ![Página Control de calidad](media/quality-check.png "Página Control de calidad")

1. Seleccione el botón de confirmación para pasar el control de calidad para el pallet 1 desde la línea 1.

    La página **Pedidos de compra: colocar** que aparece muestra detalles del trabajo de colocación:

    - **UBI.**: la ubicación determinada por el sistema.

        Esta ubicación es la ubicación de almacenamiento designada para recibir el pedido de compra.

    - **LP**: el identificador de la matricula de entidad generado por el sistema.
    - **Artículo**: *M9203*
    - **Cant.**: *1 PL: 100 ea*

    La descripción del artículo también se muestra.

1. Confirme el trabajo de ubicación.

    En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado". El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.

#### <a name="receive-pallet-2"></a>Recibir pallet2

Para este escenario, el pallet 2 será rechazado.

1. En campo **LINENO**, especifique *1* y confirme el número de línea.
1. El campo **CANT.** está ahora disponible. Escriba *1* y confirme la cantidad.

    Aparece la página **Control de calidad**. Para este recibo, el pallet será rechazado por calidad y se colocará en la ubicación de calidad *QMS*.

1. Seleccione el botón Menú (**≡**) en la parte superior de la página y luego, en el menú, seleccione **Rechazar**.
1. En la página **Tarea** que aparece, especifique **QMS** como la ubicación de *Colocar* para enviar el pallet para una inspección más detallada.

    La página **Calidad en control de calidad: colocar** que aparece muestra detalles del trabajo de colocación:

    - **UBI.**: *QMS*

        Esta ubicación es la ubicación de almacenamiento designada para recibir la calidad rechazada.

    - **LP**: el identificador de la matricula de entidad generado por el sistema.
    - **Artículo**: *M9203*
    - **Cant.**: *1 PL: 100 ea*

    La descripción del artículo también se muestra.

1. Confirme el trabajo de ubicación.

    En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado". El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.

Ahora ha completado el control de calidad y ha creado un pedido de calidad para el pallet rechazado. Para ver el pedido de calidad que se ha creado a partir del control de calidad con error, vaya a **Gestión de inventarios \> Tareas periódicas \> Administración de la calidad \> Pedidos de calidad**.

Las pruebas de pedidos de calidad ahora se pueden procesar. Las pruebas de calidad no están cubiertas en este tema.

Para obtener más información acerca de la administración de calidad, consulte [Visión general de la Administración de calidad](../inventory/enable-quality-management.md).

#### <a name="receive-pallet-3"></a>Recibir pallet3

Para este escenario, el pallet 3 será aceptado.

1. En campo **LINENO**, especifique *1* y confirme el número de línea.
1. El campo **CANT.** está ahora disponible. Escriba *1* y confirme la cantidad.

    Aparece la página **Control de calidad**. Para este recibo, el pallet será aceptado por calidad y se colocará en la ubicación de colocación masiva.

1. Seleccione el botón de confirmación para pasar el control de calidad.

    La página **Pedidos de compra: colocar** que aparece muestra detalles del trabajo de colocación:

    - **UBI.**: la ubicación determinada por el sistema.

        Esta ubicación es la ubicación de almacenamiento designada para recibir el pedido de compra.

    - **LP**: el identificador de la matricula de entidad generado por el sistema.
    - **Artículo**: *M9203*
    - **Cant.**: *1 PL: 100 ea*

    La descripción del artículo también se muestra.

1. Confirme el trabajo de ubicación.

    En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado". El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.

1. Seleccione el botón Menú (**≡**) en la parte superior de la página y luego, en el menú, seleccione **Cancelar** para regresar al menú.

Ahora puede cerrar la aplicación móvil.
