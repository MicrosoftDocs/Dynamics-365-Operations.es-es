---
title: Cálculos de impuestos de importación y exportación
description: Este artículo proporciona información sobre la funcionalidad de importación y exportación del servicio de cálculo de impuestos.
author: Kai-Cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 9daee683763d7cb0eb9573497eb4e20cba9b1863
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855184"
---
# <a name="import-and-export-tax-calculations"></a>Cálculos de impuestos de importación y exportación

Este artículo proporciona información sobre la funcionalidad de importación y exportación del servicio de cálculo de impuestos. Esta funcionalidad ayuda a garantizar una experiencia de configuración flexible y eficiente.

## <a name="import-and-export-tax-codes"></a>Códigos de impuestos de importación y exportación

### <a name="export-templates"></a>Plantillas de exportación

1. Inicie sesión en [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. En el espacio de trabajo **Características de globalización**, seleccione **Características** y, a continuación, seleccione el icono **Cálculo de impuestos**.
3. Seleccione una características existente o [cree una nueva](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. En la cuadrícula **Versiones**, seleccione **Editar**.
5. En la página de características **Cálculo de impuestos**, establezca la [versión de configuración](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. En la pestaña **Códigos de impuestos**, seleccione **Importar**.
7. Seleccione **Exportar una plantilla de código de impuestos** para descargar el archivo **TaxCodesTemplate.zip**.
8. Descomprima **TaxCodesTemplate.zip**. Las plantillas de códigos de impuestos se comprimen por separado según el valor de **Origen de cálculo**.
9. Descomprima **By Net Amount.zip** para obtener los siguientes archivos de valores separados por comas (CSV):

    - **TaxCode.csv**: escriba los códigos de impuestos.
    - **TaxLimit.csv**: escriba los límites de impuestos para cada código de impuestos.
    - **TaxRate.csv**: escriba los tipos impositivos para cada código de impuestos.

> [!NOTE]
> De forma predeterminada, las entradas para el código de impuestos **Muestra** están disponibles en las plantillas. Si no se quita el código de impuestos **Muestra** de los archivos CSV, se importará a la característica.

### <a name="import-tax-codes"></a>Importar códigos de impuestos

Siga estos pasos para importar el código de impuestos **Muestra** de la plantilla a la característica de cálculo de impuestos.

1. En RCS, en la página de características **Cálculo de impuestos**, en la pestaña **Códigos de impuestos**, seleccione **Importar**.
2. Seleccione **Examinar**, busque y seleccione el archivo **TaxCode.csv** y, a continuación, en el campo **Tabla de destino**, seleccione **Código de impuestos**.
3. Seleccione **Aceptar** para importar el código de impuestos.
4. Busque y seleccione el archivo **TaxRate.csv** y, a continuación, en el campo **Tabla de destino**, seleccione **Índice de impuestos**.
5. Seleccione **Aceptar** para importar el índice de impuestos.
6. Busque y seleccione el archivo **TaxLimit.csv** y, a continuación, en el campo **Tabla de destino**, seleccione **Límite de impuestos**.
7. Seleccione **Aceptar** para importar el límite de impuestos.

También puede importar directamente el archivo zip que incluye los tres archivos CSV. De esta manera, puede completar la importación rápida y fácilmente.

1. En RCS, en la página de características **Cálculo de impuestos**, en la pestaña **Códigos de impuestos**, seleccione **Importar**.
2. Seleccione **Examinar**, busque y seleccione el archivo **By Net Amount.zip** y, a continuación, seleccione **Aceptar**.

### <a name="export-tax-codes"></a>Exportar códigos de impuestos

1. En RCS, en la página de características **Cálculo de impuestos**, en la pestaña **Códigos de impuestos**, seleccione **Exportar**.

    El botón **Exportar** está disponible cuando hay como mínimo un código de impuestos en la cuadrícula **Códigos de impuestos**.

2. Seleccione **Aceptar** para exportar todos los códigos de impuestos de la función en un archivo zip.

> [!NOTE]
> Utilice el archivo exportado como plantilla para importar códigos de impuestos a la característica correspondiente.

## <a name="import-and-export-applicability-rules"></a>Reglas de aplicabilidad de importación y exportación

### <a name="export-applicability-rules"></a>Reglas de aplicabilidad de exportación

1. Inicie sesión en [RCS](https://marketing.configure.global.dynamics.com/).
2. En el espacio de trabajo **Características de globalización**, seleccione **Características** y, a continuación, seleccione el icono **Cálculo de impuestos**.
3. Seleccione una características existente o [cree una nueva](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. En la cuadrícula **Versiones**, seleccione **Editar**.
5. En la página de características **Cálculo de impuestos**, establezca la [versión de configuración](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. En la pestaña **Aplicabilidad del grupo de impuestos**, seleccione las filas de la cuadrícula **Configurar aplicabilidad del grupo de impuestos**.
7. Seleccione el botón **Abrir en Microsoft Office** y, a continuación, seleccione **Matriz de aplicabilidad dinámica del servicio de impuestos**.

    [![Reglas de aplicabilidad de exportación a Microsoft Excel en la página de características de Cálculo de impuestos.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Seleccione **Descargar** para exportar las filas seleccionadas a una hoja de cálculo de Microsoft Excel.

### <a name="import-applicability-rules"></a>Reglas de aplicabilidad de importación

La hoja de cálculo de Excel que descargó contiene la estructura de la cuadrícula **Configurar aplicabilidad del grupo de impuestos**. Puede agregar nuevas reglas directamente en la hoja de trabajo. Cuando haya terminado, siga estos pasos para importar las nuevas reglas de nuevo a la cuadrícula **Configurar aplicabilidad del grupo de impuestos**.

1. En la hoja de cálculo de Excel, seleccione y copie las filas para importar.
2. En RCS, en la página de características de **Cálculo de impuestos**, en la pestaña **Aplicabilidad del grupo de impuestos**, seleccione **Agregar** para insertar un registro vacío en la parte inferior de la cuadrícula **Configurar aplicabilidad del grupo de impuestos**.
3. Seleccione **Ctrl + V** para pegar las filas copiadas en la cuadrícula.
4. Seleccione **Guardar**.
