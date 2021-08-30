---
title: Actualizar la estructura de una plantilla de documento empresarial
description: Este tema explica cómo actualizar la estructura de una plantilla de documento empresarial mediante la función de administración de documentos empresariales.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 2f57e3f3a84a6e767755c69074bc194e90793e6edd79d0e07ae7449d45ec7539
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775295"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Actualizar la estructura de una plantilla de documento empresarial 

[!include[banner](../includes/banner.md)]

En el panel **Estructura de la plantilla** del editor de plantillas [Gestión de documentos empresariales](er-business-document-management.md), puede modificar una plantilla de documento empresarial [agregando nuevos campos](er-bdm-add-field-to-excel-template.md) a una plantilla en Microsoft Excel. La estructura de la plantilla se actualiza automáticamente en Dynamics 365 Finance, de modo que refleje los cambios que realizó en el panel **Estructura de la plantilla**.

También puede modificar una plantilla utilizando la funcionalidad en línea de Office 365. Por ejemplo, puede agregar un nuevo elemento con nombre, como una imagen o una forma, a la hoja de trabajo editable. En este caso, la estructura de la plantilla no se actualiza automáticamente en Finance y el elemento que agregó no aparece en el panel **Estructura de la plantilla**. Actualice manualmente la estructura de la plantilla en Finance seleccionando **Estructura de actualización** en la página del editor de plantillas.

Para obtener más información acerca de esta característica, complete el siguiente ejemplo.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Ejemplo: Actualizar la estructura de una plantilla de documento empresarial

Este ejemplo muestra cómo un administrador del sistema puede actualizar la estructura de una plantilla de documento empresarial en Finance después de modificar la plantilla en Office Online. Las siguientes secciones explican los pasos involucrados.

### <a name="prepare-a-business-document-template-for-editing"></a>Prepare una plantilla de documento empresarial para editar

Complete los siguientes procedimientos en [Descripción general de la gestión de documentos empresariales](er-business-document-management.md).

1. [Configurar los parámetros de ER](er-business-document-management.md#configure-er-parameters)
2. [Importar soluciones de ER](er-business-document-management.md#import-er-solutions)
3. [Habilitar la gestión de documentos empresariales](er-business-document-management.md#enable-business-document-management)
4. [Configurar parámetros](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Editar una plantilla de documento empresarial

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.
2. En la página **Crear una nueva plantilla**, seleccione el modelo **Factura de servicios gratuitos (muestra de ER) (Excel)**.
3. Seleccione **Crear documento**.
4. En el campo **Título**, introduzca **Muestra FTI Litware**.
5. Seleccione **Aceptar** para crear una plantilla nueva.

    > [!NOTE]
    > Si aún no ha iniciado sesión en Office Online se le [dirigirá a la página de inicio de sesión de Office 365](er-business-document-management.md#frequently-asked-questions). Para volver a su entorno de Finance, seleccione el botón **Atrás** en su navegador.

    La nueva plantilla se abre para su edición en el control incrustado de Excel Online en la página del editor de plantillas.

[![Uso del espacio de trabajo de administración de documentos empresariales para comenzar a editar una plantilla de documento empresarial.](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Revise la estructura actual de la plantilla editable

1. En Excel Online, en la cinta, en la pestaña **Ver**, en el grupo **Mostrar**, seleccione **Líneas de cuadrícula**.
2. En la plantilla editable, seleccione el rectángulo sobre el título de la plantilla. Este rectángulo es una imagen que se llama **rptHeaderCompLogo**.
3. Si el panel **Estructura de la plantilla** está oculto, seleccione **Mostrar estructura**.
4. En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.
5. Observe que, en la estructura de la plantilla en Finance, el elemento **rptHeaderCompLogo** se presenta como un elemento secundario de **Informe \> Factura \> rptHeader \> rptHeaderPart1**.

[![Usar el espacio de trabajo de administración de documentos empresariales para revisar la estructura actual de una plantilla editable.](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Actualizar la estructura de una plantilla de documento empresarial eliminando una imagen

1. En Excel Online, en la plantilla editable, seleccione la imagen **rptHeaderCompLogo**.
2. Siga uno de estos pasos para eliminar la imagen seleccionada de la plantilla editable:

    - Seleccione la tecla **Suprimir** en su teclado.
    - Seleccione y mantenga presionada (o haga clic con el botón derecho) en la imagen y luego seleccione **Cortar**.

    > [!NOTE]
    > El elemento **rptHeaderCompLogo** todavía está presente en la estructura de la plantilla en Finance, aunque la imagen ya no se incluye en la plantilla de Excel.

3. Seleccione **Estructura de actualización** para sincronizar la estructura de la plantilla editable en Excel y Finance.
4. En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.
5. Fíjese en que el elemento **rptHeaderCompLogo** ya no se incluye en la estructura de la plantilla en Finance.

[![Uso del espacio de trabajo de administración de documentos empresariales para eliminar una imagen de una plantilla de documento empresarial.](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Actualizar la estructura de una plantilla de documento empresarial añadiendo una imagen

1. En Excel Online, en la cinta, en la pestaña **Insertar**, en el grupo **Ilustraciones**, seleccione **Imagen**.
2. Seleccione **Elegir archivo**, busque la imagen que desea agregar, selecciónela y luego seleccione **Aceptar**.
3. Seleccione **Insertar**.
4. Mueva la nueva imagen hasta que esté en el lugar correcto. De forma predeterminada, Excel nombra la imagen. Por ejemplo, podría nombrar la imagen **Imagen 2**.
5. Seleccione **Estructura de actualización** para sincronizar la estructura de la plantilla editable en Excel y Finance.
6. En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.
7. Fíjese en que la nueva imagen ya se incluye como un elemento en la estructura de la plantilla en Finance.

[![Uso del espacio de trabajo de administración de documentos empresariales para agregar una imagen a una plantilla de documento empresarial.](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Vínculos relacionados

[Información general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Información general de la gestión de documentos empresariales](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]