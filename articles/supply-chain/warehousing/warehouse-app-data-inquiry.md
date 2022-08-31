---
title: Consultar datos mediante los desvíos de la aplicación móvil Warehouse Management
description: Este artículo describe cómo configurar los elementos del menú del dispositivo móvil de consulta de datos y usarlos como parte de los desvíos.
author: perlynne
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cc013e962b4da803764f16e451b1d433666e75c2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336617"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Consultar datos mediante los desvíos de la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Introducción a la característica

Al proporcionar la capacidad de escanear códigos de barras, la aplicación móvil Warehouse Management le brinda una manera fácil y precisa de capturar datos como parte de los procesos de su almacén. Sin embargo, los códigos de barras a veces se dañan y se vuelven ilegibles, o es posible que la información de datos requerida no exista como un código de barras en los flujos de su proceso comercial. En estos casos, la entrada manual de los datos puede llevar mucho tiempo e incluso puede provocar que se capturen datos incorrectos. Los resultados pueden ser una efectividad reducida y un nivel de servicio más bajo.

Mediante el uso de un proceso de consulta de datos flexible, los trabajadores pueden buscar fácilmente la información requerida como parte de los flujos de la aplicación móvil integrada de gestión de almacenes y aplicar opciones de filtrado para que solo se muestren los datos relevantes. Por lo tanto, la selección manual es más rápida y precisa.

Por ejemplo, en el flujo de recepción de órdenes de compra, se requiere un número de orden de compra para que coincida con el inventario entrante. Como parte de este proceso, puede configurar fácilmente elementos de menú para proporcionar una vista de lista de tarjetas de los números de orden de compra relevantes. De esta forma, puede continuar el flujo de recepción utilizando un enfoque rápido de apuntar para seleccionar. Este artículo proporciona escenarios de ejemplo, pero la funcionalidad también se puede usar dentro de cualquiera o todos los flujos de la aplicación móvil de gestión de almacenes.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Active la función de flujo de consulta de datos y sus requisitos previos

Antes de que pueda usar la funcionalidad que se describe en este artículo, debe completar el siguiente procedimiento para activar las funciones requeridas.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**. (Para obtener más información acerca de cómo usar el espacio de trabajo **Administración de características**, consulte [Visión general de la Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)).
1. Si ejecuta Supply Chain Management versión 10.0.28 o anterior, active la función que se muestra de la siguiente manera:

    - **Módulo:** *Gestión de almacén*
    - **Nombre de la función:** *Instrucciones de los pasos de la aplicación de almacén*

    Esta característica es un requisito previo para la característica *Flujo de consulta de datos de la aplicación Warehouse Management*. A partir de la versión 10.0.29 de Supply Chain Management, es obligatoria y no se puede desactivar. Para obtener más información sobre la característica *Instrucciones de los pasos de la aplicación de almacén*, consulte [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](mobile-app-titles-instructions.md).

1. Active la característica que se enumera de la siguiente manera:

    - **Módulo:** *Gestión de almacén*
    - **Nombre de la característica**: *Desvíos de aplicaciones de Warehouse Management*

    Esta característica es un requisito previo para la característica *Flujo de consulta de datos de la aplicación Warehouse Management*. A partir de la versión 10.0.29 de Supply Chain Management, está activada de forma predeterminada. Para obtener más información sobre la característica *Desvíos de la aplicación de gestión de almacenes*, vea [Configurar desvíos para los pasos en los elementos del menú del dispositivo móvil](warehouse-app-detours.md).

1. Si la característica *Desvíos de la aplicación Warehouse Management* no estaba ya activada, actualice los nombres de los campos en la aplicación móvil Warehouse Management yendo a **Warehouse Management \> Configuración \> Dispositivo móvil \> Nombres de campo de Warehouse Management** y seleccione **Crear configuración predeterminada**. Repita este paso para cada entidad jurídica (empresa) en la que utilice la aplicación móvil Warehouse Management. Para más información, consulte [Configurar campos para la aplicación](configure-app-field-names-priorities-warehouse.md).
1. Active la característica que se enumera de la siguiente manera:

    - **Módulo:** *Gestión de almacén*
    - **Nombre de característica**: *Flujo de solicitudes de datos en la aplicación de Warehouse Management*

    Esta característica es una que se describe en este artículo.

## <a name="example-scenarios"></a>Escenarios de ejemplo

Este artículo usa escenarios de ejemplo para mostrar cómo puede usar la característica *Flujo de consulta de datos de la aplicación de gestión de almacenes* para mejorar el flujo de recibo de compra. Los escenarios utilizan los datos de muestra estándar, que incluyen un flujo denominado *Recepción de compra*. Este flujo comienza pidiendo a los trabajadores que identifiquen un número de orden de compra contra el que recibirán. Para ayudar a los trabajadores a identificar más fácilmente la orden de compra, mejorará la primera página del flujo agregando las siguientes opciones de consulta nuevas como [desvíos](warehouse-app-detours.md):

- **Buscar órdenes de compra por proveedor** – Abra una página que solicite a los trabajadores que ingresen el nombre de un proveedor o parte del nombre de un proveedor. Se pueden utilizar caracteres comodín. Por ejemplo, si un trabajador espera una entrega entrante hoy de un proveedor que incluye *Tailspin* en su nombre, pueden entrar **Tail\*** para ver un conjunto de tarjetas para órdenes de compra abiertas que incluyen este texto. Cada tarjeta tiene varios campos que brindan información sobre cada orden de compra. Además del nombre del proveedor, puede diseñar las tarjetas para que muestren el número de cuenta del proveedor, la fecha de entrega y el estado del documento.
- **Buscar órdenes de compra para hoy** – Abra una página que no pida a los trabajadores que ingresen datos, sino que muestre filtros preconfigurados (como la fecha de hoy). Luego, la página muestra un conjunto de tarjetas que coinciden con el filtro. Los trabajadores proceden seleccionando una tarjeta para la orden de compra contra la que desean registrar artículos de inventario.
- **Buscar órdenes de compra por artículo** – Abra una página que solicite a los trabajadores que escaneen el código de barras de cualquier artículo en el inventario llegado. A continuación, el flujo enumera todos los pedidos de compra abiertos que contienen líneas para el número de artículo escaneado. Para cubrir situaciones en las que no se puede leer un código de barras, puede agregar otra búsqueda de desvío a esta página que permita a los trabajadores buscar números de artículo dentro de una orden de compra específica.

En cada caso, el trabajador identifica una orden de compra seleccionando una tarjeta y luego regresa a la primera página, que muestra el número de orden de compra seleccionado. Luego, el trabajador puede continuar con el flujo de registro de artículos de inventario entrante.

## <a name="enable-sample-data"></a>Habilitar datos de muestra

Para resolver los escenarios de ejemplo que se describen en este artículo, debe estar en un sistema donde se instalen [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal (empresa) *USMF* antes de empezar.

## <a name="configure-the-mobile-device-menu-items"></a>Configurar los elementos de menú de dispositivos móviles

Para crear cada una de las nuevas opciones de consulta que debe agregar a la primera página del flujo, debe configurarlo como un elemento de menú del dispositivo móvil. Posteriormente, hará que las opciones de consulta estén disponibles como desvíos al flujo *Recepción de compra*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Cree el elemento de menú "Buscar órdenes de compra por proveedor"

Cree el elemento de menú **Buscar órdenes de compra por proveedor** siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú de dispositivo móvil**.
1. En el panel Acciones, seleccione **Nuevo** para agregar un elemento de menú para el dispositivo móvil.
1. Establezca los siguientes valores para el elemento de menú:

    - **Nombre de elemento de menú**: *Buscar órdenes de compra por proveedor*
    - **Título:** *Buscar órdenes de compra por proveedor*
    - **Modo:** *Indirecto*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Código de actividad:** *Consulta de datos*
    - **Utilice la guía de proceso:** *Sí* (Este valor se selecciona automáticamente).
    - **Nombre de la tabla:** *PurchTable* (Desea buscar números de órdenes de compra en esta tabla).

1. En el panel de acciones, seleccione **Editar consulta** para definir una consulta que se base en la tabla base seleccionada (en este caso, la tabla de órdenes de compra).
1. En el cuadro editor de consultas, en la pestaña **Rango**, añada las líneas siguientes a la cuadrícula:

    | Tabla | Tabla derivada | Campo | Criterios |
    |---|---|---|---|
    | Pedidos de compra | Pedidos de compra | Estado de pedido de compra | Pedido abierto |
    | Pedidos de compra | Pedidos de compra | Fecha de entrega | (dayRange(-10,10)) |
    | Pedidos de compra | Pedidos de compra | Nombre del proveedor | |

1. Seleccione **Aceptar**.

    En este ejemplo, el nuevo elemento de menú está configurado para buscar pedidos de compra abiertos que se espera que lleguen en cualquier momento entre 10 días en el pasado y 10 días en el futuro.

    En la consulta, la columna **Criterios** de *Nombre del vendedor* se ha dejado en blanco. Por lo tanto, los trabajadores podrán especificar este valor mientras usan la aplicación móvil de Gestión de almacenes.

    Si desea especificar cómo se ordenará la lista, puede configurar la clasificación en la pestaña **Clasificación**.

1. Además de definir la consulta, debe seleccionar qué campos se mostrarán en las tarjetas en la página de lista de consultas. Por tanto, en el panel de acciones, seleccione **Lista de campos**.
1. En la página **Lista de campos**, establezca los valores siguientes:

    - **Campo de visualización 1:** *PurchId* (Este campo se mostrará como el encabezado de cada tarjeta).
    - **Campo de visualización 2:** *PurchStatus*
    - **Campo de visualización 3:** *PurchName*
    - **Campo de visualización 4:** *OrderAccount*
    - **Campo de visualización 5:** *DeliveryDate*
    - **Campo de visualización 6:** *displayDocumentStatus()* (Este valor es un método de visualización, como indica el "()" al final).

1. En el panel Acciones, seleccione **Guardar**. A continuación, cierre la página.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Cree el elemento de menú "Buscar órdenes de compra para hoy"

Cree el elemento de menú **Buscar órdenes de compra para hoy** siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú de dispositivo móvil**.
1. En el panel Acciones, seleccione **Nuevo** para agregar un elemento de menú para el dispositivo móvil.
1. Establezca los siguientes valores para el nuevo elemento:

    - **Nombre de elemento de menú**: *Buscar órdenes de compra para hoy*
    - **Título:** *Buscar órdenes de compra para hoy*
    - **Modo:** *Indirecto*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Código de actividad:** *Consulta de datos*
    - **Utilice la guía de proceso:** *Sí* (Este valor se selecciona automáticamente).
    - **Nombre de la tabla:** *PurchTable* (Desea buscar números de órdenes de compra en esta tabla).

1. En el panel de acciones, seleccione **Editar consulta** para definir una consulta que se base en la tabla base seleccionada (en este caso, la tabla de órdenes de compra).
1. En el cuadro editor de consultas, en la pestaña **Rango**, añada las líneas siguientes a la cuadrícula:

    | Tabla | Tabla derivada | Campo | Criterios |
    |---|---|---|---|
    | Pedido de compra | Pedido de compra | Estado de pedido de compra | Pedido abierto |
    | Pedido de compra | Pedido de compra | Fecha de entrega | (Day(0)) |

1. Seleccione **Aceptar**.

    En este ejemplo, el nuevo elemento de menú está configurado para buscar pedidos de compra abiertos que se espera que lleguen hoy.

    Si desea especificar cómo se ordenará la lista, puede configurar la clasificación en la pestaña **Clasificación**.

1. Además de definir la consulta, debe seleccionar qué campos se mostrarán en las tarjetas en la página de lista de consultas. Por tanto, en el panel de acciones, seleccione **Lista de campos**.
1. En la página **Lista de campos**, establezca los valores siguientes:

    - **Campo de visualización 1:** *PurchName* (Este campo se mostrará como el encabezado de cada tarjeta).
    - **Campo de visualización 2:** *PurchId*
    - **Campo de visualización 3:** *PurchStatus*
    - **Campo de visualización 4:** *DlvMode*
    - **Campo de visualización 5:** *DlvTerm*
    - **Campo de visualización 6:** *OrderAccount*
    - **Campo de visualización 7:** *VendorName()* (Este valor es un método de visualización, como indica el "()" al final).

1. En el panel Acciones, seleccione **Guardar**. A continuación, cierre la página.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Cree el elemento de menú "Buscar órdenes de compra por elemento"

Cree el elemento de menú **Buscar órdenes de compra por elemento** siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú de dispositivo móvil**.
1. En el panel Acciones, seleccione **Nuevo** para agregar un elemento de menú para el dispositivo móvil.
1. Establezca los siguientes valores para el nuevo elemento:

    - **Nombre de elemento de menú**: *Buscar órdenes de compra por elemento*
    - **Título:** *Buscar órdenes de compra por elemento*
    - **Modo:** *Indirecto*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Código de actividad:** *Consulta de datos*
    - **Utilice la guía de proceso:** *Sí* (Este valor se selecciona automáticamente).
    - **Nombre de la tabla:** *PurchLine* (Desea buscar números de orden de compra según el número de artículo a través de los datos de línea).

1. En el panel de acciones, seleccione **Editar consulta** para definir una consulta que se basa en la tabla base seleccionada (en este caso, la tabla de líneas de orden de compra, pero puede usar cualquiera de los valores que están relacionados con el encabezado uniéndose a *PurchTable*).
1. En el cuadro editor de consultas, en la pestaña **Rango**, añada las líneas siguientes a la cuadrícula:

    | Tabla | Tabla derivada | Campo | Criterios |
    |---|---|---|---|
    | Líneas de pedido de compra | Líneas de pedido de compra | Estado de línea | Pedido abierto |
    | Líneas de pedido de compra | Líneas de pedido de compra | Fecha de entrega | (dayRange(-10,10)) |
    | Líneas de pedido de compra | Líneas de pedido de compra | Número de artículo | |

1. Seleccione **Aceptar**.

    En este ejemplo, el nuevo elemento de menú está configurado para buscar líneas de pedidos de compra abiertos que se espera que lleguen en cualquier momento entre 10 días en el pasado y 10 días en el futuro.

    En la consulta, la columna **Criterios** de *Número de artículo* se ha dejado en blanco. Por lo tanto, los trabajadores podrán especificar este valor mientras usan la aplicación móvil de Gestión de almacenes.

    Si desea especificar cómo se ordenará la lista, puede configurar la clasificación en la pestaña **Clasificación**.

1. Además de definir la consulta, debe seleccionar qué campos se mostrarán en las tarjetas en la página de lista de consultas. Por tanto, en el panel de acciones, seleccione **Lista de campos**.
1. En la página **Lista de campos**, establezca los valores siguientes:

    - **Campo de visualización 1:** *PurchId* (Este valor de campo se usará como el encabezado de cada tarjeta).
    - **Campo de visualización 2:** *VendAccount*
    - **Campo de visualización 3:** *PurchQty*
    - **Campo de visualización 4:** *PurchUnit*
    - **Campo de visualización 5:** *PurchStatus*

1. En el panel Acciones, seleccione **Guardar**. A continuación, cierre la página.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Agregar los nuevos elementos de menú del dispositivo móvil a un menú

Los tres nuevos elementos del menú del dispositivo móvil ahora están listos para agregarse al menú del dispositivo móvil. Esta tarea debe completarse antes de que los elementos del menú se puedan usar como parte de un proceso de desvío. En este ejemplo, creará un nuevo submenú y le agregará los nuevos elementos de menú.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado del nuevo registro:

    - **Nombre:** *Consulta*
    - **Descripción:** *Consulta*

1. En la lista **Menús disponibles y elementos de menú**, seleccione el primero de los elementos de menú de dispositivo móvil que acaba de crear. Luego seleccione el botón de flecha derecha para mover ese elemento en la lista **Estructura del menú**.
1. Repita el paso anterior para los otros dos nuevos elementos del menú.
1. En el panel de la lista de la izquierda, seleccione el menú **Principal**.
1. En la lista **Menús y elementos de menú disponibles**, desplácese hacia abajo hasta la sección **Menús** y seleccione el nuevo menú **Consulta**. Luego seleccione el botón de flecha derecha para mover ese elemento en la lista **Estructura del menú**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Configurar desvíos en sus pasos del dispositivo móvil

Para completar la configuración, ahora debe usar la configuración de desvío en la página **Pasos del dispositivo móvil** para agregar los tres nuevos elementos del menú del dispositivo móvil al paso de identificación del pedido de compra existente en el flujo *Recepción de compra*.

1. Vaya a **Administración de almacenes \> Configuración > Dispositivo móvil \> Pasos del dispositivo móvil**.
1. En el campo **Filtro**, especifique *PONum*. Luego seleccione *Id. de paso: "PONum"* en la lista desplegable.
1. Mientras el registro que se encuentra está seleccionado en la cuarícula, seleccione **Agregar configuración de pasos** en el Panel de acciones. En el cuadro de diálogo desplegable que aparece, establezca el campo **Elemento de menú** en *Recepción de compra*. Luego seleccione **Aceptar** para cerrar el cuadro de diálogo.
1. En la página de detalles de la nueva configuración de pasos (**Recepciń de compra: PONum**), en la ficha **Desvíos disponibles (elementos del menú)**, seleccione **Agregar** en la barra de herramientas.
1. En el cuadro de diálogo **Añadir desvío**, busque y seleccione el elemento de menú **Buscar órdenes de compra por proveedor** que creó anteriormente.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo y agregar el elemento de menú seleccionado a la lista de desvíos.
1. Seleccione el nuevo desvío y luego seleccione **Seleccionar campos para enviar** en la barra de herramientas.
1. En el cuadro de diálogo **Seleccionar campos para enviar**, no agregue nada a la sección **Enviar desde recepción de compra**, porque no desea pasar ningún valor al elemento de menú de desvío. Sin embargo, en la sección **Recuperar desde la búsqueda de órdenes de compra por proveedor**, establezca el siguiente valor para la fila vacía que ya se ha agregado allí:

    - **Copiar de Buscar órdenes de compra por proveedor:** *Orden de compra*
    - **Pegar en Compra Recibir:** *Orden de compra*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. Repita los pasos del 4 al 9 para los otros dos nuevos elementos del menú (**Buscar órdenes de compra para hoy** y **Buscar órdenes de compra por artículo**). En cuanto al elemento de menú **Buscar órdenes de compra por proveedor**, no desea enviar ningún dato a estos desvíos, pero desea devolver un número de orden de compra.
1. Cierre la página.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Pruebe un flujo de recepción de compras que tenga una consulta de datos como parte de un desvío

Siga estos pasos para probar la configuración de su nueva aplicación móvil.

1. Cree varias órdenes de compra que tengan líneas para el almacén 51.
1. Vaya a un dispositivo móvil o emulador que esté ejecutando la aplicación móvil de gestión de almacenes e inicie sesión en el almacén 51 utilizando *51* como id. de usuario y *1* como contraseña.
1. En el menú de la aplicación móvil, seleccione **Entrante** y luego **Recepción de compra**.

    Debería ver la siguiente página, que incluye los tres nuevos elementos del menú.

    ![Recepción de compras usando el número de orden de compra.](media/wma-purchase-receive-po-num-with-detours.png "Recepción de compras usando el número de orden de compra")

1. Pruebe las diferentes capacidades y observe que puede devolver un número de orden de compra seleccionando una de las tarjetas de la lista.

    ![Recepción de compras utilizando la búsqueda de órdenes de compra por proveedor, ejemplo 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Recepción de compras utilizando la búsqueda de órdenes de compra por proveedor, ejemplo 1")

    ![Recepción de compras utilizando la búsqueda de órdenes de compra por proveedor, ejemplo 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Recepción de compras utilizando la búsqueda de órdenes de compra por proveedor, ejemplo 2")

> [!TIP]
> En lugar de ejecutar el flujo de recepción haciendo una búsqueda desde el elemento del menú **Recepción de compra**, puede comenzar desde un flujo de consulta (**Principal \> Consulta \> Buscar órdenes de compra por proveedor**) e invoque un desvío para ejecutar el flujo deseado seleccionando una de las tarjetas de la lista. Para utilizar este enfoque, puede definir un desvío en la página **Pasos del dispositivo móvil** para el paso que tiene un valor **ID de paso** de *GenericDataInquiryList*. Debido a que este flujo es un flujo de desvío, no puede invocar más desvíos desde él. Por lo tanto, cuando llegue a la pantalla de entrada de número de artículo, por ejemplo, la búsqueda no estará disponible en ella, porque el sistema actualmente solo admite un nivel de desvíos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
