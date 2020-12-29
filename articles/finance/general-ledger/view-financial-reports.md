---
title: Ver informes financieros
description: En este tema se describe cómo ver y explorar informes financieros en Microsoft Dynamics 365 Finance. Incluye información sobre las distintas opciones que se pueden aplicar a los informes financieros para cambiar su aspecto y los datos que incluyen.
author: kweekley
manager: AnnBe
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c368259af9454af94da217585b2a1d01ea75d834
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447606"
---
# <a name="view-financial-reports"></a>Ver informes financieros

[!include [banner](../includes/banner.md)]

En este tema se describe cómo ver y explorar informes financieros. Incluye información sobre las distintas opciones que se pueden aplicar a los informes financieros para cambiar su aspecto y los datos que incluyen.

<a name="financial-reporting-overview"></a>Visión general de informes financieros
----------------------------

## <a name="open-a-financial-report"></a>Abrir un informe financiero
Para abrir un informe, seleccione el nombre del informe. La primera vez que se abre un informe, se genera automáticamente para el mes anterior. Por ejemplo, si abre un informe por primera vez en agosto de 2015, el informe se genera para el 31 de julio de 2015. Tras abrir un informe, puede empezar a explorarlo profundizando en fragmentos específicos de datos y cambiando las opciones de informe.

## <a name="drill-down-on-a-financial-report"></a>Exploración en profundidad de informes financieros
Los informes financieros pueden incluir múltiples niveles de detalle. El nivel financiero es el primer nivel que ve al abrir un informe financiero. Para ir al nivel de cuenta, seleccione los datos que desea explorar en profundidad. Por ejemplo, para ver los detalles de la cuenta para ventas, seleccione los datos de ventas que desea explorar. Desde el nivel de cuenta, puede explorar en profundidad para ver las transacciones que componen el saldo de la cuenta. Hay dos formas de ver transacciones: transacciones de informes y transacciones de asientos.

-   **Transacciones de informes**: las transacciones aparecen en una vista con formato que se incluye en el informe financiero. Para ver transacciones en la vista con formato, seleccione los datos que desea explorar en profundidad y, a continuación, haga clic en **Obtener detalles de nivel de transacción de informe**.
-   **Transacciones de asiento**: se abre una consulta de transacción de asiento, en la que puede ver transacciones. Para ver transacciones en la consulta de transacción de asiento, seleccione los datos que desea explorar en profundidad y, a continuación, haga clic en **Transacciones abiertas de la cuenta**.

Si los datos son datos de presupuesto, puede elegir abrir asientos contables presupuestarios. Para cerrar cualquier nivel del informe y regresar la lugar donde comenzó, puede presionar la tecla Esc o hacer clic en el botón **Cerrar** (**X**) en la parte superior derecha.

## <a name="change-report-options"></a>Cambiar opciones de informe
Puede aplicar filtros de atributos y dimensiones, o cambiar el escenario de presupuesto en un informe **Real frente a presupuesto**. En el Panel de acciones, haga clic en **Opciones del informe** y, a continuación, siga uno o más de estos pasos:

-   Para aplicar filtros de atributos a un informe, seleccione **Agregar atributo de filtro**. Seleccione el atributo, escriba el valor del atributo y, a continuación, haga clic en **Aceptar**. Por ejemplo, si selecciona el atributo **Categoría de cuenta**, especifique **VENTAS** como el valor del atributo. Para quitar un filtro de atributo, haga clic en **Borrar**.
-   Para aplicar filtros de dimensión a un informe, seleccione **Agregar una dimensión de filtro**. Seleccione la dimensión y, a continuación, escriba el id. de la dimensión o seleccione la dimensión en la lista. Para quitar un filtro de dimensión, haga clic en **Borrar**.
-   Para cambiar el escenario en un informe **Real frente a presupuesto**, seleccione un nuevo escenario y haga clic en **Aceptar**. Si el escenario seleccionado es por otro año fiscal, no se devolverá resultado alguno. Por ejemplo, si un informe se genera para FY2015 y la situación actual es para FY2015 y la nueva escenario seleccionado es para FY2016, no se mostrará ningún resultado. Si es necesario un nuevo escenario para otro año fiscal, genere una nueva versión del informe del ejercicio relacionado con la situación.

Al hacer clic en **Aceptar**, se aplican al informe todas las opciones que haya seleccionado. Si decide que no desea aplicar las opciones seleccionadas, haga clic en **Cancelar**.

## <a name="update-a-financial-report"></a>Actualizar un informe financiero
Puede actualizar un informe financiero de modo que muestre los datos más recientes para el período y el año para el que se generó el informe. Por ejemplo, si actualiza un informe financiero que se generó para octubre de 2015, el informe refleja las nuevas transacciones que se han registrado para octubre de 2015. Para actualizar un informe financiero, en el Panel de acciones, haga clic en **Actualizar**. Un informe actualizado solo está disponible para la persona que lo actualizó. Para que las demás personas vean los mismos datos, se debe publicar el informe.

## <a name="publish-a-financial-report"></a>Publicar un informe financiero
Tras actualizar un informe financiero, puede publicarlo. Otras personas de la organización podrán verlo entonces. Para publicar un informe, en el Panel de acciones, haga clic en **Publicar**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Mostrar un informe financiero en una divisa distinta
Se puede mostrar un informe financiero en cualquier divisa en cualquier momento. Para mostrar un informe en una divisa distinta, en el Panel de acciones, haga clic en **Divisa** y seleccione una divisa. El informe se traduce en esa divisa y se muestran los resultados. Los símbolos o los códigos de divisa que se incluyen como parte del diseño del informe se actualizan para reflejar la nueva divisa. Las divisas que aparecen en la lista son las divisas de notificación que se configuran en Finance.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Mostrar una vista resumida del informe financiero
Un informe financiero puede contener líneas de detalle y líneas de resumen. Las líneas de detalle son las líneas que contienen cuentas principales o dimensiones. Las líneas de resumen son descripción, total y líneas de cálculo. Para mostrar solo las líneas de resumen de un informe, haga clic en **Mostrar** y luego en **Solo líneas de resumen**. El informe se contrae y solo muestra las líneas de resumen. Para ver las líneas de detalle junto con las líneas de resumen, haga clic en **Mostrar** y luego haga clic en **Solo líneas de resumen** de nuevo.

## <a name="print-a-financial-report"></a>Imprimir un informe financiero
Imprimir un informe financiero creará un archivo PDF que puede a continuación imprimirse manualmente. Para crear un informe financiero que pueda imprimirse, en el Panel de acciones, haga clic en **Imprimir** y, a continuación, siga uno o más de estos pasos para establecer las opciones de impresión:

-   Para incluir los diversos niveles de detalles en el informe impreso, establezca el control deslizante en **Sí** o **No**. Si un informe usa un organigrama, puede elegir incluir todas las unidades de notificación o solo la unidad de notificación actual.
-   Para establecer el tamaño de página, seleccione un tamaño de página en la lista.
-   Para establecer el diseño de la página, seleccione un diseño en la lista. Si desea que el contenido del informe ajuste el ancho que ha seleccionado, establezca el control deslizante en **Sí**.
-   Para establecer los márgenes de página, escriba el tamaño de los márgenes superior, inferior, izquierdo y derecho en pulgadas.

Una vez que haya terminado de establecer las opciones de impresión, haga clic en **Imprimir** para continuar y que se le pida si desea descargar el archivo, o guardar el archivo en OneDrive o en SharePoint. Si decide que no desea continuar, haga clic en **Cancelar** en su lugar. Una vez que continúe, el informe comenzará a representarse en el servidor y se le solicitará que descargue el informe en formato PDF. Ahora puede ver el informe en el visor de PDF y desde ahí puede seleccionar la impresora a la que enviará el informe e introducir ajustes adicionales en las opciones de impresión.

## <a name="export-a-financial-report"></a>Exportar un informe financiero
Para exportar un informe financiero, en el Panel de acciones, haga clic en **Exportar**. El informe se exporta a Microsoft Excel y el explorador le pregunta si desea abrir o guardar el archivo exportado. La configuración de exportación que se define en el diseño del informe se aplica al informe exportado.    

<a name="additional-resources"></a>Recursos adicionales
--------

[Informes financieros](../../dev-itpro/analytics/financial-reporting-intro.md)




