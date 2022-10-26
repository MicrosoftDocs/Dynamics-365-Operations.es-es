---
title: Reglas de asignación de la solución Invoice Capture
description: Este artículo proporciona información sobre la configuración de reglas de asignación en la solución Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691239"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Reglas de asignación de la solución Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Las reglas de mapeo traen datos maestros básicos de Microsoft Dynamics 365 Finance o el sistema de planificación de recursos empresariales (ERP). Después de configurar las reglas de asignación, se obtiene la información necesaria para crear facturas de proveedores en Finance. Cuando se utilizan reglas de asignación, el empleado de Cuentas por pagar (AP) verificará el estado en lugar de completar manualmente todos los valores de campo que faltan.

Hay cuatro tipos de reglas de asignación:

- Entidad jurídica
- Cuenta del proveedor
- Elemento
- Tipo de gasto

## <a name="manage-mapping-rules-by-using-the-app"></a>Administrar reglas de mapeo usando la aplicación

Para administrar las reglas de mapeo usando la aplicación, seleccione **Configuración**. La pestaña **Configuración de reglas de mapeo** ofrece cuatro opciones:

- Entidad jurídica 
- Cuenta del proveedor 
- Asignación de elementos 
- Tipo de gasto

Por ejemplo, selecciona la opción **Reglas de mapeo de entidades legales**. El código de entidad legal se identificará utilizando el nombre de la empresa, la dirección y el número de registro fiscal. Para una regla que se llame **LE-USPM**, si el nombre de la empresa contiene el texto "Contoso Robotics USA", el código de entidad legal será **USPM**.

La página muestra todas las reglas de mapeo activas. Si desea ver las reglas de asignación inactivas, seleccione **Reglas de entidades jurídicas de asignación activa** y luego seleccione **Reglas de entidad jurídica de asignación inactiva**.

Las siguientes acciones están disponibles para las reglas de asignación.

### <a name="create-a-mapping-rule"></a>Crear una regla de asignación

Puede utilizar dos métodos para crear una regla de asignación:

- Seleccione **Nuevo** para crear una nueva regla de asignación. A continuación, especifique información para la regla de asignación. El valor **Nombre de la regla** debe ser único para cada tipo de regla de asignación.
- Si selecciona una regla de mapeo existente, el botón **Copiar** pasa a estar disponible. Selecciónelo y luego seleccione, en el cuadro de diálogo que aparece, **Aceptar**. Una regla de mapeo se crea duplicando la regla seleccionada.

### <a name="edit-a-mapping-rule"></a>Editar una regla de asignación

Para editar una regla de asignación, seleccione un campo y cambie el valor.

### <a name="activatedeactivate-mapping-rules"></a>Activar/desactivar reglas de mapeo

Para desactivar una o más reglas de mapeo, selecciónelas en la página **Reglas de mapeo activas** y, a continuación, seleccione **Desactivar**. Las reglas se mueven de la página **Reglas de mapeo activas** a la página **Reglas de mapeo inactivas**.

De igual forma, para activar reglas de mapeo, selecciónelas en la página **Reglas de mapeo inactivas** y, a continuación, seleccione **Activar**.

### <a name="remove-mapping-rules"></a>Quitar reglas de asignación

Para quitar reglas de mapeo, selecciónelas y luego seleccione **Borrar**.

### <a name="check-for-conflicts"></a>Buscar conflictos

Si dos reglas de mapeo tienen la misma **Entidad legal** y **Cuenta de vendedor**, pero diferentes valores de **Nombre de artículo**, se detectará un conflicto y la regla de asignación no se creará ni actualizará.

## <a name="importexport-mapping-rules-from-excel"></a>Importar/exportar reglas de mapeo desde Excel

Se puede usar un complemento de Excel para administrar reglas en un lote. Las siguientes opciones están disponibles:

- Descargar una plantilla de Excel.
- Exportar a Excel.
- Importar desde Excel.

### <a name="download-an-excel-template"></a>Descargar una plantilla de Excel

Para descargar una plantilla de Excel, seleccione **Descargar plantilla**. Luego seleccione los campos que se van a incluir en la plantilla.

### <a name="export-to-excel"></a>Exportar a Excel

Puede exportar de dos maneras:

- Seleccione **Abrir en Excel en línea** para abrir el archivo en Excel. Entonces podrá editar el archivo en línea. Cuando haya terminado, haga clic en **Guardar**. Todos sus cambios se guardarán en la página **Regla de mapeo**.
- Seleccione **Descargar hoja de trabajo** para descargar un archivo de Excel que contiene reglas de mapeo. Entonces podrá editar el archivo. Cuando haya terminado, seleccione **Importar desde Excel** para cargar la hoja de cálculo actualizada.

### <a name="import-from-excel"></a>Importar desde Excel

1. Seleccione **Importar desde Excel** para importar datos de un archivo XLSX. También puede importar desde valores separados por comas (CSV) o archivos XML. Antes de importar, debe decidir si se permiten duplicados.
2. Seleccione **Revisión de mapeo** para revisar la asignación de atributos y determinar si es correcta. No se puede modificar la relación de asignación.
3. Cuando haya terminado, seleccione **Finalizar importación** para iniciar la importación.
4. Puede elegir **Seguimiento del proceso** para seguir el progreso del proceso de importación.

    El estado de la importación se actualiza de **Finalizar** a **Análisis**, luego a **Transformando** y finalmente a **Completado**.

Cuando se completa el proceso de importación, se muestran las estadísticas de éxitos, fallas parciales, errores y procesamiento total.
