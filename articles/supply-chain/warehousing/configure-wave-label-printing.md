---
title: Impresión de etiquetas de oleadas
description: Este tema describe la impresión de etiquetas de oleada y explica cómo configurarla.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 3040406af731e2e35fff456804f893108e7eb896bfa0132082986c09ad128952
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777680"
---
# <a name="wave-label-printing"></a>Impresión de etiquetas de oleadas

[!include [banner](../includes/banner.md)]

La impresión de etiquetas de oleada ofrece un enfoque alternativo a la impresión de etiquetas al introducir un método de nuevo paso de oleada que permite crear e imprimir etiquetas directamente desde la plantilla de oleada durante la ejecución de la oleada. Por lo tanto, las etiquetas ya estarán disponibles antes de que los trabajadores ejecuten la orden de trabajo en un dispositivo móvil. Después, los trabajadores pueden adjuntar las etiquetas requeridas durante la recogida en vez de después de esta.

La impresión de etiquetas de oleadas utiliza el lenguaje de programación Zebra (ZPL) para crear los diseños de las etiquetas. Un diseño de etiqueta se divide en tres secciones (encabezado, cuerpo y pie de página) para permitir etiquetas que tengan una estructura repetitiva. Las plantillas de etiquetas de oleadas le indican al sistema qué diseño de etiqueta usar. Los usuarios pueden especificar qué impresora se utiliza. También pueden imprimir etiquetas en varias impresoras al mismo tiempo, según lo requieran. La página **Historial de etiquetas de oleada** muestra un registro de todas las etiquetas que se han creado utilizando esta configuración.

Puede imprimir e intercalar etiquetas basadas en encabezados de trabajo, imprimir etiquetas de interrupción por encabezados de trabajo, además de imprimir etiquetas de contenido de contenedor, etiquetas de cajas y otras etiquetas similares.

> [!NOTE]
> Esta funcionalidad no reemplaza la funcionalidad de impresión de etiquetas existente que se basa en el enrutamiento de documentos.

La impresión de etiquetas de oleadas ofrece las siguientes mejoras:

- Imprimir etiquetas de acuerdo con el número de cajas en una sola línea de trabajo, sin utilizar la creación de contenedores. (Una "caja" es una unidad designada en líneas de grupo de secuencia de unidades.)
- Imprimir varias secuencias de etiquetas diferentes (por ejemplo, etiquetas de cajas y pallets).
- Incluir la enumeración de etiquetas (por ejemplo, 1/124, 2/124, ... 124/124) y definir el rango de enumeración (por ejemplo, línea de trabajo, línea de carga o envío).
- Crear e imprimir un id. de conocimiento de embarque en las etiquetas antes de que se genere el conocimiento de embarque.
- Crear un código único de contenedor de envío en serie (SSCC) para cada caja e incluirlo en cada etiqueta.
- Crear secuencias numéricos que cumplan con GS1 para id. de conocimiento de embarque y SSCC.
- Volver a imprimir etiquetas desde dispositivos móviles y el cliente enriquecido.
- Anular las etiquetas (por ejemplo, en escenarios de selección corta) y volver a imprimirlas.
- Limpiar el historial de etiquetas de oleadas.
- Las mejoras en los diseños de enrutamiento de documentos se comparten entre los diseños de enrutamiento de documentos y los diseños de etiquetas de oleadas. (Para más información, consulte [Diseño de enrutamiento de documentos para matrículas](../warehousing/document-routing-layout-for-license-plates.md).)

Estas mejoras hacen que el etiquetado de cajas antes de la paletización sea más eficiente. Benefician especialmente a las empresas que envían a grandes minoristas que confirman automáticamente los recibos de los pedidos escaneando cada caja por separado.

> [!NOTE]
> Puede implementar los escenarios de configuración que se describen en este tema por separado o en combinación, según los requisitos de su negocio. Puede diseñar varias plantillas de etiquetas de oleadas que funcionen en secuencia (como se ilustra en el escenario 3). Por ejemplo, puede usar el escenario 1 para imprimir etiquetas de cajas y el escenario 2 para imprimir etiquetas de pallets (si las pallets en existencias varían en tamaño y composición).

## <a name="turn-on-the-wave-label-printing-feature"></a>Activar la característica de impresión de etiquetas de oleada

Para poder usar la característica *Impresión de etiquetas de oleada*, debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Impresión de etiquetas de oleada*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Escenario 1: impresión de etiquetas de oleada donde se genera una única etiqueta de oleada

Este escenario muestra cómo una empresa puede imprimir etiquetas de envío para un gran minorista que confirma automáticamente los recibos de los pedidos escaneando cada caja por separado.

Este escenario muestra el flujo de extremo a extremo.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Asegúrese de que el método de etiqueta de oleada esté disponible

Es posible que tenga que regenerar los métodos de proceso de oleada para que el método de impresión de etiquetas de oleadas esté disponible.

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. Confirme que **waveLabelPrinting** está en la lista. Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.

### <a name="configure-a-wave-template"></a>Configurar una plantilla de oleada

Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a una plantilla de etiqueta de oleada correspondiente.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. Seleccione una plantilla, como **Plantilla predeterminada 62**.
1. En la ficha desplegable **Métodos**, mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.
1. En la columna **Métodos seleccionados**, seleccione el método **Impresión de etiquetas de oleada** y establezca el campo **Código de paso de oleada** en *Etiqueta de impresión*. Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Crear un diseño de etiqueta de oleada

El diseño de la etiqueta controla qué información se imprime en la etiqueta y cómo se dispone. Introduzca aquí el código ZPL que se envía a la impresora.

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.
1. Cree un registro que tenga la siguiente configuración:

    - **Id. de diseño de etiqueta:** *Caja*
    - **Descripción:** *Caja (SSCC)*

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.

    Aparece la página **Configuración de filas de etiquetas de oleadas**. Aquí, puede configurar la parte dinámica de la etiqueta.

1. Agregue una fila con la siguiente configuración:

    - **Id. de fila:** *WaveLabel*
    - **Nombre de la tabla de filas:** *WHSWaveLabel*
    - **Posición inicial de fila:** *0*

        Este campo define la posición vertical donde comenzará la fila en la etiqueta.

    - **Alto de fila:** *0*

        Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL. El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales. Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).

    - **Filas por página:** *1*

        Este campo define el número de filas que se pueden imprimir en cada etiqueta.

        > [!NOTE]
        > Esta configuración hará que se imprima una etiqueta ZPL independiente para cada registro en la tabla de etiquetas de oleada.

1. Cierre la página.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo**, seleccione una fila que tenga los siguientes parámetros.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Tipo de trabajo*
    - **Criterios:** *Seleccionar*

    Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.

1. Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones**, seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.
1. Cierre el cuadro de diálogo del editor de consultas.
1. La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado**, **Sección del cuerpo** y **Sección del pie de página**. En la **Sección del encabezado**, en el campo **Encabezado de la etiqueta**, introduzca el código para el encabezado requerido. Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. En la **Sección del cuerpo**, en el campo **Cuerpo de la etiqueta**, introduzca el código ZPL para el cuerpo requerido. He aquí un ejemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. En la **Sección del cuerpo**, en el campo **Pie de página de la etiqueta**, introduzca el código ZPL para el pie de página requerido. He aquí un ejemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuración imprimirá una copia de cada etiqueta. Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias. Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.

Su etiqueta ya está lista para usarse.

### <a name="create-a-wave-label-type"></a>Crear un tipo de etiqueta de oleada

Los tipos de etiquetas de oleadas se utilizan para vincular plantillas de etiquetas de oleadas a una unidad en una unidad de líneas de grupo de secuencias.

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Tipos de etiquetas de oleadas**.
1. Agregue un tipo de etiqueta de oleada que tenga la siguiente configuración:

    - **Tipo de etiqueta:** *Caja*
    - **Descripción:** *Caja*

### <a name="set-up-unit-sequence-groups"></a>Configurar grupos de secuencias de unidades

A continuación, configure el grupo de secuencia de unidades para el tipo de etiqueta de oleada.

1. Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Grupos de secuencias de unidades**.
1. Seleccione el grupo **Ea Box PL**.
1. En la línea **Caja** establezca el campo **Tipo de nivel de oleada** en *Caja*.

### <a name="create-a-wave-label-template"></a>Crear una plantilla de etiqueta de oleada

A continuación, cree la plantilla de etiqueta de oleada para el tipo de etiqueta de oleada.

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.
1. Agregue una plantilla de nivel de oleada y establezca los siguientes valores en el encabezado:

    - **Nombre de plantilla de etiqueta:** *Etiquetas de caja*
    - **Descripción:** *Etiquetas de caja*
    - **Código de paso de oleada:** *EtiquetaImpresión*
    - **Almacén**: *62*

1. En la ficha desplegable **General**, establezca el campo **Tipo de etiqueta de oleada** en *Caja de cartón*.
1. En la ficha desplegable **Detalles de plantilla de etiqueta de oleada**, agregue una nueva fila que tenga la siguiente configuración:

    - **Id. de diseño de etiqueta:** *Caja*
    - **Nombre de la impresora:** seleccione una impresora ZPL adecuada.
    - **Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).

1. En el panel Acciones, seleccione **Guardar**.
1. Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente. En la ficha desplegable **Detalles de plantilla de etiqueta de oleada**, seleccione **Editar consulta**. A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo**, en el cuadro de diálogo del editor de consultas.

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Número de cuenta*
    - **Criterios** introduzca el número de cuenta del cliente pertinente.

    Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación**, seleccione una fila que tenga la siguiente configuración.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *id. de línea de carga de referencia (id. de registro)*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación. Seleccione **Sí** para continuar.
1. En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.
1. En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas**, seleccione la fila donde el campo **Nombre del campo de referencia** está establecido en *Id. de línea de carga de referencia* y luego seleccione la casilla **Id. de compilación de etiqueta** de esta fila.

    > [!NOTE]
    > Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo. Esta secuencia de etiquetas se puede imprimir en el diseño de la etiqueta.

### <a name="configure-number-sequence-extensions"></a>Configurar extensiones de secuencias numéricas

Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas. Esta configuración es opcional para el escenario actual. Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Crear un pedido de ventas y liberarlo en el almacén

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *62*

1. Agregue dos líneas de pedidos de ventas que tengan la siguiente configuración:

    - Línea de pedido de ventas 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *9024*
        - **Unidad:** *ea* (9024 ea = 376 Caja = 47 PL)

    - Línea de pedido de ventas 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *9016*
        - **Unidad:** *ea* (9016 ea = 322 Caja = 46 PL)

    > [!NOTE]
    > Los artículos y cantidades que se proporcionan aquí son solo ejemplos. Deben usar el grupo de secuencias de unidades que ha definido anteriormente, las conversiones de unidades adecuadas de *ea* a *Caja* a *PL* deben definirse para ellas, y deben tener existencias en el almacén *62*. Para más información, consulte [Directivas de unidad de medida y de existencias](unit-measure-stocking-policies.md).

1. Seleccione la línea de pedido de ventas 1. A continuación, en la sección **Línea de pedido de ventas**, en el menú **Inventario**, seleccione **Reservas**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** y después cierre la página.
1. Repita los pasos 4 y 5 para la línea de pedido de ventas 2.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Se producen los eventos siguientes:

    - El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas. El diseño de la etiqueta se usará para definir el formato de la etiqueta y el resultado será una etiqueta impresa en la impresora que está seleccionada en la plantilla de la etiqueta.
    - Las etiquetas de oleadas se generan y se imprimen. El número de etiquetas será igual al número de cajas (en este ejemplo, 376 etiquetas de cajas para la línea 1 y 322 etiquetas de cajas para la línea 2).
    - Se genera un nuevo id. de conocimiento de embarque para los envíos. Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**. 

Puede ver y reimprimir etiquetas de oleada desde las siguientes páginas. En el panel de acciones de cada página, en la pestaña **Envíos** del grupo **Información relacionada**, seleccione **Etiquetas de oleada**.

- Todos los envíos \> Detalles del envío
- Todas las cargas \> Detalles de la carga
- Todas las oleadas
- Etiquetas de oleadas
- Historial de etiquetas de oleada

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Escenario 2: impresión de etiquetas de oleadas para la creación de contenedores (sin registros de etiquetas de oleadas)

Este escenario le permite imprimir etiquetas de oleadas cuando usa la creación de contenedores para dividir automáticamente los artículos en cajas y, por tanto, no requieren un registro de etiqueta de oleada. En este caso, el id. de contenedor actúa como un marcador de posición para el SSCC.

Estas son las diferencias principales entre este escenario y el escenario 1:

- **Plantillas de etiquetas de oleadas:** no seleccionará un tipo de etiqueta de oleada en la plantilla de etiqueta de oleada, y no necesitará una agrupación de compilaciones de etiquetas. De lo contrario, configurará la plantilla de etiqueta de oleada y la vinculará a la plantilla de oleada de la misma manera que se describe en el escenario 1. Debe dejar el tipo de etiqueta de oleada en blanco para evitar que se generen etiquetas de oleadas.
- **Diseños de etiquetas de oleadas:** establecerá la configuración de filas de diseño de etiquetas de oleadas para líneas de trabajo en lugar de registros de etiquetas de oleadas. Debe establecer la configuración de filas para el diseño de la etiqueta utilizando la tabla **WHSWorkLine** en lugar de la tabla **WHSWaveLabel**. La configuración **Filas por página** controla el número de filas que tendrá la sección del cuerpo. 

Esta configuración también es adecuada para escenarios de negocios en los que se empaquetan múltiples artículos diferentes en una caja etiquetada o en un pallet, y este proceso de empaquetado se puede definir por creación de trabajo (por ejemplo, trabajo que se agrupa por envío).

Este escenario muestra el flujo de extremo a extremo.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Asegúrese de que el método de etiqueta de oleada esté disponible

Es posible que tenga que regenerar los métodos de proceso de oleada para que el método de impresión de etiquetas de oleadas esté disponible.

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. Confirme que **waveLabelPrinting** está en la lista. Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.

### <a name="set-up-a-wave-template"></a>Configurar una plantilla de oleada

Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a una plantilla de etiqueta de oleada correspondiente.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. Seleccione una plantilla como **63 Creación de contenedores**.
1. En la ficha desplegable **Métodos**, mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.
1. En la columna **Métodos seleccionados**, seleccione el método **Impresión de etiquetas de oleada** y establezca el campo **Código de paso de oleada** en *Etiqueta de impresión*. Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Crear un diseño de etiqueta de oleada

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.
1. Cree un registro que tenga la siguiente configuración:

    - **Id. de diseño de etiqueta:** *Caja*
    - **Descripción:** *Caja (SSCC)*

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.

    Aparece la página **Configuración de filas de etiquetas de oleadas**. Aquí, puede configurar la parte dinámica de la etiqueta.

1. Agregue una fila con la siguiente configuración:

    - **Id de fila:** *WorkLine*
    - **Nombre de la tabla de filas:** *WHSWorkLine*
    - **Posición inicial de fila:** *500*

        Este campo define la posición vertical donde comenzará la fila en la etiqueta.

    - **Alto de fila:** *-50*

        Este campo define el alto de cada fila. El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales.

    - **Filas por página:** *5*

        Este campo define el número de filas que se pueden imprimir en cada etiqueta.

        > [!NOTE]
        > Esta configuración imprimirá varias etiquetas ZPL por trabajo, donde cada página puede contener hasta cinco líneas de trabajo. Por ejemplo, si se imprime una etiqueta para un contenedor que tiene 12 líneas, se imprimirán tres etiquetas. Si desea imprimir una etiqueta independiente para cada línea de selección, establezca este valor en *1*.

1. Cierre la página.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo**, seleccione una fila que tenga los siguientes parámetros.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Tipo de trabajo*
    - **Criterios:** *Seleccionar*

1. Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones**, seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.
1. Cierre el cuadro de diálogo del editor de consultas.
1. La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado**, **Sección del cuerpo** y **Sección del pie de página**. En la **Sección del encabezado**, en el campo **Encabezado de la etiqueta**, introduzca el código para el encabezado requerido. Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. En la **Sección del cuerpo**, en el campo **Cuerpo de la etiqueta**, introduzca el código ZPL para el cuerpo requerido. He aquí un ejemplo.

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. En la **Sección del cuerpo**, en el campo **Pie de página de la etiqueta**, introduzca el código ZPL para el pie de página requerido. He aquí un ejemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuración imprimirá una copia de cada etiqueta. Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias. Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.

Su etiqueta ya está lista para usarse.

### <a name="create-a-wave-label-template"></a>Crear una plantilla de etiqueta de oleada

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.
1. Agregue una plantilla de nivel de oleada y establezca los siguientes valores en el encabezado:

    - **Nombre de plantilla de etiqueta:** *Etiquetas de contenedor*
    - **Descripción:** *Etiquetas de contenedores*
    - **Código de paso de oleada:** *EtiquetaImpresión*
    - **Almacén**: *63*

1. En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas**, agregue una fila que tenga la siguiente configuración:

    - **Id. de diseño de etiquetas:** *Contenedor*
    - **Nombre de la impresora:** seleccione una impresora ZPL adecuada.
    - **Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).

1. En el panel Acciones, seleccione **Guardar**.
1. Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente. En la ficha desplegable **Detalles de plantilla de etiqueta de oleada**, seleccione **Editar consulta**. A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo**, en el cuadro de diálogo del editor de consultas.

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Número de cuenta*
    - **Criterios** introduzca el número de cuenta del cliente pertinente.

    Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.

### <a name="configure-number-sequence-extensions"></a>Configurar extensiones de secuencias numéricas

Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas. Esta configuración es opcional para el escenario actual. Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Crear un pedido de ventas y liberarlo en el almacén

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *63*

1. Agregar cinco líneas de pedido de ventas:

    - Línea de pedido de ventas 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *10*

    - Línea de pedido de ventas 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *20*

    - Línea de pedido de ventas 3:

        - **Código de artículo:** *L0006*
        - **Cantidad:** *20*

    - Línea de pedido de ventas 4:

        - **Código de artículo:** *L0100*
        - **Cantidad:** *40*

    - Línea de pedido de ventas 5:

        - **Código de artículo:** *L0101*
        - **Cantidad:** *50*

    > [!NOTE]
    > Los artículos y cantidades que se proporcionan aquí son solo ejemplos. Deben tener existencias en el almacén especificado.

1. Seleccione la línea de pedido de ventas 1. A continuación, en la sección **Línea de pedido de ventas**, en el menú **Inventario**, seleccione **Reservas**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** y después cierre la página.
1. Repita los pasos 4 y 5 para cada línea adicional del pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Se producen los eventos siguientes:

    - El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas. El diseño de etiqueta se usará para definir el formato de la etiqueta y el resultado final será una etiqueta que tiene cinco líneas y que se imprime en la impresora que está seleccionada en la plantilla de etiqueta.
    - Se genera un nuevo id. de conocimiento de embarque para los envíos. Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**. 

Para volver a imprimir estas etiquetas de oleadas, vaya a **Gestión de almacenes \> Consultas e informes \> Historial de etiquetas de oleada**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Escenario 3: impresión de etiquetas de oleadas para etiquetas de varios niveles

Este escenario muestra cómo utilizar la funcionalidad de impresión de etiquetas de oleada cuando los procesos de almacenamiento requieren varios niveles de etiquetas de envío. Por ejemplo, es posible que se tengan que imprimir etiquetas independientes para cajas y pallets, y se debe imprimir una etiqueta de interrupción para un envío completo. Las etiquetas de interrupción son un tipo independiente de etiqueta que se puede usar como un divisor entre rollos y contenedores, como las etiquetas para el id. de envío y un código de barras, de modo que las etiquetas pueden ordenarse con facilidad después de su impresión.

La diferencia principal entre la configuración de este escenario y la configuración del escenario 1, además del hecho de que las etiquetas de interrupción están habilitadas, es que varios tipos de etiquetas de oleadas deben estar asociados con plantillas de etiquetas de oleadas y líneas de grupos de secuencias de unidad. Para lograr esta configuración, configure los siguientes elementos para este escenario:

- **Métodos de procesamiento de oleadas:** marcará el método de etiqueta de oleada como "repetible", lo agregará dos (o más) veces a la plantilla de oleada y establecerá diferentes códigos de paso de oleada.
- **Plantillas de etiquetas de oleadas:** configurará las plantillas de etiquetas de oleadas y las vinculará a la plantilla de oleada. Cada plantilla de etiqueta de oleada tiene su propio tipo de etiqueta de oleada.
- **Diseños de etiquetas de oleadas:** creará varios diseños de etiquetas de oleadas. Habrá un diseño de etiqueta independiente para cada "nivel" de etiquetas y también habrá un diseño de etiqueta de interrupción.

Este escenario muestra el flujo de extremo a extremo.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.

### <a name="set-up-a-wave-process-method"></a>Configurar un método de proceso de oleada

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. Confirme que **waveLabelPrinting** está en la lista. Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.
1. Para el método **waveLabelPrinting**, seleccione la casilla **Convertir método en repetible**.

### <a name="set-up-a-wave-template"></a>Configurar una plantilla de oleada

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
2. Seleccione una plantilla, como **Plantilla predeterminada 62**.
3. En la ficha desplegable **Métodos**, mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.
4. En la columna **Métodos seleccionados**, asigne un valor **Código de paso de oleada**, como *Caja*, al método **Impresión de etiquetas de oleadas**. Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).
5. Mueva de nuevo el método **Impresión de etiquetas de oleadas** a la columna **Métodos seleccionados**.
6. En la columna **Métodos seleccionados**, asigne un valor diferente **Código de paso de oleada**, como *Pallet*, al segundo método método **Impresión de etiquetas de oleadas**. Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Crear tres diseños de etiquetas de oleadas

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.
1. Cree un registro que tenga la siguiente configuración:

    - **Id. de diseño de etiqueta:** *Caja*
    - **Descripción:** *Caja (SSCC)*

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.

    Aparece la página **Configuración de filas de etiquetas de oleadas**. Aquí, puede configurar la parte dinámica de la etiqueta.

1. Agregue una fila con la siguiente configuración:

    - **Id. de fila:** *WaveLabel*
    - **Nombre de la tabla de filas:** *WHSWaveLabel*
    - **Posición inicial de fila:** *0*

        Este campo define la posición vertical donde comenzará la fila en la etiqueta.

    - **Alto de fila:** *0*

        Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL. El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales. Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).

    - **Filas por página:** *1*

        Este campo define el número de filas que se pueden imprimir en cada etiqueta.

        > [!NOTE]
        > Esta configuración hará que se imprima una etiqueta ZPL independiente para cada registro en la tabla de etiquetas de oleada.

1. Cierre la página.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo**, seleccione una fila que tenga los siguientes parámetros.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Tipo de trabajo*
    - **Criterios:** *Seleccionar*

    Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.

1. Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones**, seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**. 
1. Cierre el cuadro de diálogo del editor de consultas.
1. La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado**, **Sección del cuerpo** y **Sección del pie de página**. En la **Sección del encabezado**, en el campo **Encabezado de la etiqueta**, introduzca el código para el encabezado requerido. Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. En la **Sección del cuerpo**, en el campo **Cuerpo de la etiqueta**, introduzca el código ZPL para el cuerpo requerido. He aquí un ejemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. En la **Sección del cuerpo**, en el campo **Pie de página de la etiqueta**, introduzca el código ZPL para el pie de página requerido. He aquí un ejemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuración imprimirá una copia de cada etiqueta. Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias. Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.

1. La primera etiqueta ya está lista para usarse.
1. Cree un segundo registro de diseño que tenga la siguiente configuración:

    - **Id. de diseño de etiquetas:** *Pallet*
    - **Descripción:** *Pallet*

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.

    Aparece la página **Configuración de filas de etiquetas de oleadas**. Aquí, puede configurar la parte dinámica de la etiqueta.

1. Agregue una fila con la siguiente configuración:

    - **Id. de fila:** *WaveLabel*
    - **Nombre de la tabla de filas:** *WHSWaveLabel*
    - **Posición inicial de fila:** *0*

        Este campo define la posición vertical donde comenzará la fila en la etiqueta.

    - **Alto de fila:** *0*

        Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL. El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales. Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).

    - **Filas por página:** *1*

        Este campo define el número de filas que se pueden imprimir en cada etiqueta.

        > [!NOTE]
        > Esta configuración causa que se imprima una etiqueta ZPL independiente para cada registro de la tabla de etiquetas de oleadas.

1. Cierre la página.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo**, seleccione una fila que tenga los siguientes parámetros.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Tipo de trabajo*
    - **Criterios:** *Seleccionar*

    Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.

1. Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones**, seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.
1. Cierre el cuadro de diálogo del editor de consultas.
1. La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado**, **Sección del cuerpo** y **Sección del pie de página**. En la **Sección del encabezado**, en el campo **Encabezado de la etiqueta**, introduzca el código para el encabezado requerido. Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. En la **Sección del cuerpo**, en el campo **Cuerpo de la etiqueta**, introduzca el código ZPL para el cuerpo requerido. He aquí un ejemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. En la **Sección del cuerpo**, en el campo **Pie de página de la etiqueta**, introduzca el código ZPL para el pie de página requerido. He aquí un ejemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuración imprimirá una copia de cada etiqueta. Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias. Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.

1. La segunda etiqueta ya está lista para usarse.
1. Cree un tercer registro de diseño que tenga la siguiente configuración:

    - **Id. de diseño de etiquetas:** *Interrupción*
    - **Descripción:** *Etiqueta de interrupción*

1. En el panel Acciones, seleccione **Guardar**.
1. La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado**, **Sección del cuerpo** y **Sección del pie de página**. En **Sección del encabezado**, en el campo **Encabezado de la etiqueta**, introduzca el código ZPL para el encabezado requerido. He aquí un ejemplo.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Esta vez, el cuerpo no es necesario. Por lo tanto, simplemente introduzca el texto necesario en la **Sección de pie de página**. He aquí un ejemplo.

    ```plaintext
    ^XZ
    ```

    La tercera etiqueta ya está lista para usarse.

    > [!NOTE]
    > Esta tercera etiqueta es una etiqueta de interrupción que se utilizará como divisor entre los rollos de etiquetas.

### <a name="create-two-wave-label-types"></a>Crear dos tipos de etiquetas de oleadas

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Tipos de etiquetas de oleadas**.
1. Cree un registro que tenga la siguiente configuración:

    - **Tipo de etiqueta:** *Caja*
    - **Descripción:** *Caja (SSCC)*

1. Cree un segundo registro que tenga la siguiente configuración:

    - **Tipo de etiqueta:** *Pallets*
    - **Descripción:** *Pallet*

### <a name="set-up-unit-sequence-groups"></a>Configurar grupos de secuencias de unidades

1. Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Grupos de secuencias de unidades**.
1. Seleccione o cree un grupo **Ea Box PL**.
1. En la línea **Caja** establezca el campo **Tipo de nivel de oleada** en *Caja*.
1. En la línea **Ea Box PL** establezca el campo **Tipo de nivel de oleada** en *Pallet*.

### <a name="create-wave-label-templates"></a>Crear plantillas de etiquetas de oleadas

1. Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.
1. Cree una plantilla de etiqueta con la siguiente configuración:

    - **Nombre de plantilla de etiqueta:** *Etiquetas de caja*
    - **Descripción:** *Etiquetas de caja*
    - **Código de paso de oleada:** *Caja*
    - **Almacén**: *62*

1. En la ficha desplegable **General**, en el campo **Tipo de etiqueta de oleada**, seleccione un valor como *Caja*.
1. En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas**, agregue una fila que tenga la siguiente configuración:

    - **Id. de diseño de etiqueta:** *Caja*
    - **Nombre de la impresora:** seleccione una impresora ZPL adecuada.
    - **Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).

1. En el panel Acciones, seleccione **Guardar**.
1. Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente. En la ficha desplegable **Detalles de plantilla de etiqueta de oleada**, seleccione **Editar consulta**. A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo**, en el cuadro de diálogo del editor de consultas.

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Número de cuenta*
    - **Criterios** introduzca el número de cuenta del cliente pertinente.

    Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación**, seleccione una fila que tenga la siguiente configuración.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *id. de línea de carga de referencia (id. de registro)*
    - **Dirección de búsqueda:** *Ascendente*

1. Agregue una segunda columna que tenga la siguiente configuración:

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Identificación del envío*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación. Seleccione **Sí** para continuar.
1. En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.
1. En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas**, en la fila donde el campo **Nombre del campo de referencia** se establece en *Id. del envío*, establezca los siguientes valores:

    - **Imprimir etiqueta de interrupción:** seleccione esta casilla.
    - **ID de diseño de etiquetas:** seleccione una etiqueta de interrupción. (Por ejemplo, seleccione el diseño de la etiqueta *Interrupción* que creó anteriormente en este escenario.)
    - **Nombre de la impresora:** seleccione la impresora para la etiqueta de interrupción. (Normalmente, para dividir los rollos de etiquetas, debe seleccionar la misma impresora que está seleccionada en la ficha desplegable **Detalles de plantilla de etiqueta de oleada**. Aún así, pueden darse otros escenarios).

1. Para la fila donde el campo **Nombre del campo de referencia** se establezca en *Identificador de la referencia de la línea de carga*, seleccione la casilla **Id. de compilación de etiqueta**.

    > [!NOTE]
    > Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo. Esta secuencia de etiquetas se puede imprimir en un diseño de etiqueta. Además, las etiquetas para diferentes envíos estarán separadas por la etiqueta de interrupción seleccionada.

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas**.
1. Cree una segunda plantilla de etiqueta con la siguiente configuración:

    - **Nombre de la plantilla de etiqueta:** *Etiquetas de pallet*
    - **Descripción:** *Etiquetas de pallet*
    - **Código de paso de oleada:** *Pallet*
    - **Almacén**: *62*

1. En la ficha desplegable **General**, en el campo **Tipo de etiqueta de oleada**, seleccione un valor como *Pallet*.
1. En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas**, agregue una fila que tenga la siguiente configuración:

    - **Id. de diseño de etiquetas:** *Pallet*
    - **Nombre de la impresora:** seleccione una impresora ZPL adecuada.
    - **Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).

1. En el panel Acciones, seleccione **Guardar**.
1. Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente. En la ficha desplegable **Detalles de plantilla de etiqueta de oleada**, seleccione **Editar consulta**. A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo**, en el cuadro de diálogo del editor de consultas.

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Número de cuenta*
    - **Criterios** introduzca el número de cuenta del cliente pertinente.

    Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas. 

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación**, seleccione una fila que tenga la siguiente configuración.

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *id. de línea de carga de referencia (id. de registro)*
    - **Dirección de búsqueda:** *Ascendente*

1. Agregue una segunda columna que tenga la siguiente configuración:

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Identificación del envío*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación. Seleccione **Sí** para continuar.
1. En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.
1. En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas**, en la fila donde el campo **Nombre del campo de referencia** se establece en *Id. del envío*, establezca los siguientes valores:

    - **Imprimir etiqueta de interrupción:** seleccione esta casilla.
    - **ID de diseño de etiquetas:** seleccione una etiqueta de interrupción. (Por ejemplo, seleccione el diseño de la etiqueta *Interrupción* que creó anteriormente en este escenario.)
    - **Nombre de la impresora:** seleccione la impresora para la etiqueta de interrupción. (Normalmente, para dividir los rollos de etiquetas, debe seleccionar la misma impresora que está seleccionada en la ficha desplegable **Detalles de plantilla de etiqueta de oleada**. Aún así, pueden darse otros escenarios).

1. Para la fila donde el campo **Nombre del campo de referencia** se establezca en *Identificador de la referencia de la línea de carga*, seleccione la casilla **Id. de compilación de etiqueta**.

    > [!NOTE]
    > Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo. Esta secuencia de etiquetas se puede imprimir en un diseño de etiqueta. Además, las etiquetas para diferentes envíos estarán separadas por la etiqueta de interrupción seleccionada.

### <a name="configure-number-sequence-extensions"></a>Configurar extensiones de secuencias numéricas

Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas. Esta configuración es opcional para el escenario actual. Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Crear un pedido de ventas y liberarlo en el almacén

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *62*

1. Agrega dos líneas de pedidos de ventas:

    - Línea de pedido de ventas 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *9024*
        - **Unidad:** *ea* (9024 ea = 376 Caja = 47 PL)

    - Línea de pedido de ventas 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *9016*
        - **Unidad:** *ea* (9016 ea = 322 Caja = 46 PL)

    > [!NOTE]
    > Los artículos y cantidades que se proporcionan aquí son solo ejemplos. Deben usar el grupo de secuencias de unidades que ha definido anteriormente, las conversiones de unidades adecuadas de *ea* a *Caja* a *PL* deben definirse para ellas, y deben tener existencias en el almacén *62*. Para más información, consulte [Directivas de unidad de medida y de existencias](unit-measure-stocking-policies.md).

1. Seleccione la línea de pedido de ventas 1. A continuación, en la sección **Línea de pedido de ventas**, en el menú **Inventario**, seleccione **Reservas**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** y después cierre la página.
1. Repita los pasos 4 y 5 para la línea de pedido de ventas 2.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Se producen los eventos siguientes: 

    - El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas. El diseño de la etiqueta se usará para definir el formato de la etiqueta y el resultado será una etiqueta impresa en la impresora que está seleccionada en la plantilla de la etiqueta.
    - Las etiquetas de oleadas se generan y se imprimen. El número de etiquetas será igual al número de cajas (en este ejemplo, 376 etiquetas de caja para la línea 1, 322 etiquetas de caja para la línea 2, 47 etiquetas de PL para la línea 1, 47 etiquetas de PL para la línea 2 y dos etiquetas de interrupción que tienen el Id. del envío).
    - Se genera un nuevo id. de conocimiento de embarque para los envíos. Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**. 

Puede ver y volver a imprimir etiquetas de oleadas desde las siguientes páginas:

- Todos los envíos \> Detalles del envío
- Todas las cargas \> Detalles de la carga
- Todas las oleadas
- Etiquetas de oleadas
- Historial de etiquetas de oleada

Para la mayoría de estas páginas, puede encontrar la función relevante seleccionando **Etiquetas de oleadas** en el grupo **Información relacionada** de la pestaña del panel de acciones **Envíos**.

## <a name="additional-resources"></a>Recursos adicionales

- [Volver a imprimir y anular etiquetas de lanzamiento](reprint-and-void-wave-labels.md)
- [Programar la impresión de etiquetas de oleada durante la oleada](configure-task-based-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
