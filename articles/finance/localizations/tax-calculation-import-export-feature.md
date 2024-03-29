---
title: Cálculos de impuestos de importación y exportación
description: Este artículo proporciona información sobre la funcionalidad de importación y exportación del servicio de cálculo de impuestos.
author: Kai-Cloud
ms.date: 10/17/2022
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
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690243"
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

## <a name="import-feature-demo-data"></a>Importar datos de demostración de funciones

Siga estos pasos para importar datos de demostración de funciones.

1. Inicie sesión en [RCS](https://marketing.configure.global.dynamics.com/).
2. En el espacio de trabajo **Características de globalización**, seleccione **Características** y, a continuación, seleccione el icono **Cálculo de impuestos**.
3. Seleccione **Importar**, y luego, en la página **Importar función desde el repositorio global**, seleccione **Sincronizar**. 
4. En la tabla, seleccione la función **tax-calculation-feature-demo-data** y, a continuación, seleccione **Importar**.
5. Seleccione **Vista** para revisar los códigos de impuestos, los grupos y las reglas de aplicabilidad que se definen en la función importada.
6. En Finanzas, cambie a la entidad legal **DEMF** y luego vaya a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Parámetros de cálculo de impuestos**.
7. En la pestaña **General**, seleccione **Habilitar servicio de cálculo de impuestos**.
8. En el campo **Nombre de configuración de funciones**, seleccione **tax-calculation-feature-demo-data**.
9. Seleccione un **Periodo de asentamiento** y un **Grupo de registro contable** para los nuevos códigos de impuestos de demostración y, a continuación, seleccione **Confirmar**.
10. Seleccione **Guardar**.

> [!NOTE]
> La función de demostración **tax-calculation-feature-demo-data** se basa en la versión de la función **40.54.234** y se ha diseñado para la entidad legal de demostración **DEMF**. Asegúrese de que Finance y RCS estén actualizados a la versión 10.0.26 o posterior.
