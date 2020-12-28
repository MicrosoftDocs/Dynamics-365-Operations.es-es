---
title: Registro de la recepción de artículos devueltos
description: Puede registrar la recepción de artículos devueltos mediante el formulario Visión general de llegadas o el formulario Registro.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42ca1d4d2d9b45d79cf479833f83e498e3b73540
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436596"
---
# <a name="register-the-receipt-of-returned-items"></a>Registro de la recepción de artículos devueltos 

[!include [banner](../includes/banner.md)]


Hay dos métodos para registrar la recepción de artículos devueltos. El primer método es el proceso de recepción en un almacén que usa el formulario **Visión general de llegadas**. El segundo usa el formulario **Registro**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Registre el recibo de artículos devueltos en el formulario Visión general de llegadas

Puede utilizar el formulario **Visión general de llegadas** para identificar un envío de devolución por su número de autorización de devolución de materiales (RMA). Si está definido un nombre de diario en la ficha **Configuración** y existen líneas de diario que se correspondan con las líneas seleccionadas en el formulario **Visión general de llegadas**, se creará automáticamente un nuevo encabezado de diario al hacer clic en **Iniciar llegada**.

1.  Haga clic en **Gestión del inventario** \> **Periódico** \> **Visión general de llegadas**.

2.  En el campo **Configurar nombre**, seleccione **Pedido de devolución** y, a continuación haga clic en **Actualizar**.
    

    > [!TIP]
    > <P>Puede utilizar los campos <STRONG>Intervalo</STRONG> para filtrar los resultados de la búsqueda. Puede escribir o seleccionar el número de RMA en el campo <STRONG>Número RMA</STRONG> para obtener un resultado exacto. Para definir y guardar un conjunto de filtros que restrinjan las entradas que se muestran, haga clic en la ficha <STRONG>Configuración</STRONG>. Los filtros disponibles incluyen tipos, almacenes y muelles.</P>

    

    > [!WARNING]
    > <P>Los pedidos de devolución no se pueden mezclar con otros tipos de llegada en el formulario <STRONG>Visión general de llegadas</STRONG>. Por lo tanto, la referencia siempre será pedido de ventas, pero no se especificará ningún Id. de pedido de ventas en el encabezado del diario.</P>



3.  En la cuadrícula **Recibos**, localice la línea que corresponda al artículo que se está devolviendo y active la casilla de la columna **Seleccionar para llegada**.

4.  Si desea excluir determinadas líneas de la recepción de devolución, como artículos del pedido original que no se incluyeron en el envío de devolución, desactive las casillas **Seleccionar para llegada** asociadas en la tabla **Líneas** de la parte inferior del formulario.

5.  Haga clic en el botón **Iniciar llegada** para crear un diario de recepción.
    

    > [!NOTE]
    > <P>Puede seleccionar varios pedidos de devolución e incluirlos a todos en un único proceso de llegada. Cada línea del pedido de devolución se copiará en la línea correspondiente del diario de recepción de artículos.</P>

    

    > [!NOTE]
    > <P>También puede crear manualmente un diario de recepción mediante el formulario <STRONG>Recepción de artículos</STRONG>. 



6.  Haga clic en **Gestión del inventario** \> **Diarios** \> **Recepción de artículos** \> **Recepción de artículos**.

7.  Seleccione el diario de recepción que acaba de crear y, a continuación, haga clic en **Líneas** para abrir el formulario **Líneas de diario, ubicaciones**.

8.  En la ficha **General**, ajuste el número en el campo **Cantidad**, si fuera necesario, y asígnele un código de disposición en el campo **Código de disposición**.
    
    Como alternativa, puede marcar la casilla **Gestión de cuarentena** para someter los artículos devueltos a un proceso de inspección dentro de un pedido de cuarentena.
    

    > [!NOTE]
    > <P>Si envía los artículos devueltos a la cuarentena, no puede especificar un código de disposición.</P>



9.  Haga clic en el botón **Validar**.

10. Si no hay errores en el proceso de validación, haga clic en **Registrar**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Registre el recibo de artículos devueltos en el formulario de Registro

En vez de utilizar el formulario **Visión general de llegadas**, puede utilizar el formulario **Registro** para registrar la recepción de artículos devueltos.

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**. Cree un nuevo pedido de devolución o abra el pedido de devolución de la lista. En la ficha desplegable **Líneas**, seleccione la línea de pedido de devolución. Haga clic en **Actualizar línea** y luego en **Registro**.

2.  Asigne un código de disposición en el campo **Código de disposición** y, a continuación, haga clic en **Aceptar**.
    

    > [!NOTE]
    > <P>No se podrá enviar el artículo para inspección como pedido de cuarentena mediante el formulario <STRONG>Registro</STRONG>.</P>



3.  En la cuadrícula **Transacciones**, seleccione la transacción que vaya a registrar.

4.  En la cuadrícula **Registrar ahora** , haga click en **Agregar**. Repita los dos pasos anteriores hasta que todos los artículos devueltos aparezcan en la cuadrícula **Registrar ahora**.

5.  Haga clic en **Registrar todo**.

## <a name="see-also"></a>Consulte también

[Visión general de llegadas (formulario)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  


