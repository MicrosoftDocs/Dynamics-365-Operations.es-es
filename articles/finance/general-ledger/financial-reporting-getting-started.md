---
title: Visión general de informes financieros
description: Este tema describe cómo acceder a los informes financieros en Microsoft Dynamics 365 Finance y cómo usar las capacidades de informes financieros. Incluye una descripción de los informes financieros predeterminados proporcionados.
author: aprilolson
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cd77e22f9c6f90f6aa9934d70a121008e1274dd
ms.sourcegitcommit: 5419f2b8f51cd5de55be66d1389b5b9d7771fd52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "3262658"
---
# <a name="financial-reporting-overview"></a>Visión general de informes financieros

[!include [banner](../includes/banner.md)]

Este tema describe cómo acceder a los informes financieros y cómo usar las capacidades de informes financieros. También incluye una descripción de los informes financieros predeterminados proporcionados.

<a name="accessing-financial-reporting"></a>Acceso a informes financieros
-----------------------------

Encontrará el menú **Informes financieros** en los dos siguientes lugares:

-   **Contabilidad general** &gt; **Consultas e informes**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Gestión presupuestaria básica**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Gestión presupuestaria básica**
-   **Gestión presupuestaria** &gt; **Consultas e informes** &gt; **Control presupuestario**
-   Consolidaciones

Para crear y generar informes financieros para una entidad jurídica, debe configurar la siguiente información para esa entidad jurídica:

-   Calendario fiscal
-   Libro mayor
-   Plan contable
-   Divisa

Las funciones de informes financieros están disponibles para los usuarios que tienen los privilegios y los derechos adecuados asignados con sus roles de seguridad. Las secciones siguientes muestran estos privilegios y deberes, junto con los roles asociados.

### <a name="duties"></a>Deberes

| Etiqueta de arancel                            | Descripción                                                             | Nombre AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Mantener seguridad de informes financieros | Mantener la seguridad de los informes financieros y realizar tareas administrativas. | FinancialReportsSecurityMaintain |
| Mantener informes financieros            | Diseñar y mantener informes financieros.                                  | FinancialReportsMaintain         |
| Generar informes financieros            | Generar y actualizar informes financieros.                                 | FinancialReportsGenerate         |
| Revisar rendimiento financiero          | Revisar y analizar rendimiento financiero.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilegios

| Etiqueta del privilegio                       | Descripción                                                             | Nombre AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Mantener seguridad de informes financieros | Mantener la seguridad de los informes financieros y realizar tareas administrativas. | FinancialReportsSecuritySystemMaintain |
| Mantener informes financieros            | Diseñar y mantener informes financieros.                                  | FinancialReportsMaintainReports  |
| Generar informes financieros            | Generar y actualizar informes financieros.                                 | FinancialReportsGenerateReports  |
| Ver informes financieros                | Ver informes financieros.                                                 | FinancialReportsView             |

### <a name="roles"></a>Roles

| Etiqueta del privilegio                       | Derecho                                  | Roles                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Mantener seguridad de informes financieros | Mantener seguridad de informes financieros | Administrador de seguridad                                                          |
| Mantener informes financieros            | Mantener informes financieros            | Administrador contable, Supervisor de contabilidad, Controlador financiero, Administrador presupuestario |
| Generar informes financieros            | Generar informes financieros            | Director financiero, CFO, contable                                                            |
| Ver informes financieros                | Revisar rendimiento financiero          | Ninguno asignado                                                                   |

Tras la adición de un usuario o el cambio de un rol, el usuario debe poder tener acceso a informes financieros al cabo de unos minutos. **Nota:** el rol sysadmin se agrega a todos los roles en informes financieros.

## <a name="report-deletions-and-expirations"></a>Notificar eliminaciones y vencimientos
Los usuarios que generan un informe pueden eliminar sus propios informes. Los usuarios con el deber **Mantener seguridad de informes financieros** puede eliminar los informes de otros. 

En la versión 10.0.8, se introdujo el concepto de fechas de vencimiento. Se habilitará una nueva función requerida en la página **Todas** dentro del espacio de trabajo de gestión de características. La característica **Políticas de retención de informes financieros** contiene los siguientes cambios:
* Los informes recién generados se marcarán automáticamente con una fecha de vencimiento de 90 días a partir de la fecha en que se generaron
* Cualquier informe existente que sea anterior a la instalación de la característica tendrá un período de vencimiento de 90 días. La fecha puede mostrarse en blanco durante un corto período de tiempo hasta que se ejecute el servicio de informes financieros, se genere un informe y el servicio realice la actualización de los informes existentes con una fecha de vencimiento en blanco. 
* Los usuarios con **Mantener seguridad de informes financieros** tienen acceso a esta funcionalidad. Cualquier usuario con el deber **Mantener informes financieros** que tenga concedido el privilegio **Mantener el vencimiento del informe financiero** también tendrá la capacidad de modificar el período de vencimiento. Actualmente hay dos opciones de retención disponibles. 
  * Un vencimiento de 90 días.
  * La opción de establecer que el informe nunca venza.
  
Se considerarán opciones adicionales en la funcionalidad futura. El vencimiento de 90 días será el predeterminado y los usuarios con los permisos adecuados pueden anular la configuración predeterminada en la página de lista **Informes financieros**.    
  
Cuando se selecciona un vencimiento de 90 días, otorga 90 días a partir de hoy, que es un comportamiento que difiere de los 90 días a partir de la fecha de generación original establecida al generar el informe. 

## <a name="default-reports"></a>Informes predeterminados
Los informes financieros proporcionan 22 informes financieros predeterminados. Cada informe usa las categorías de cuenta principal predeterminada. Puede usar estos informes tal cual o como punto de partida para las necesidades de informes financieros. Además de los informes financieros tradicionales, como Informe financiero y Balance de situación, estos informes predeterminados incluyen informes que muestran los diferentes tipos de informes financieros que puede crear. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Informe predeterminado                                                                                         | Descripción                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Informe de ingresos de columna única móvil de 12 meses – predeterminado | Vea la rentabilidad de una organización durante los últimos 12 meses en una sola columna.                                                                                                                                                                                                                                      |
| Informe de ingresos de tendencias de 12 meses – predeterminado                 | Vea la rentabilidad de una organización para cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                             |
| Real frente a presupuesto - predeterminado                                | Vea información detallada de saldo para todas las cuentas para el presupuesto original y compare el presupuesto revisado con los valores reales que tienen una desviación.                                                                                                                                                                          |
| Detalles de auditoría - predeterminado                                  | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito en la divisa de notificación y la divisa local, junto con la información de transacciones adicional, como el id. de usuario, el usuario que modificó los datos por última vez, la fecha de la última modificación y el id. de diario. |
| Lista de saldos - predeterminado                                   | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de apertura y cierre, y los saldos de débito y crédito para el período actual y el año hasta la fecha, junto con la información de transacciones adicional, como el asiento.                                                                    |
| Balance de situación - predeterminado                                   | Vea la posición financiera de la organización para el año.                                                                                                                                                                                                                                                             |
| Balance de situación e informe de ingresos en paralelo - predeterminado | Ver la rentabilidad y posición financiera de la organización para el año de forma simultánea.                                                                                                                                                                                                                              |
| Flujo de efectivo - predeterminado                                       | Obtenga información del efectivo que entra y sale de la organización.                                                                                                                                                                                                                                   |
| Revisión de JE y TB detallada – predeterminado                      | Vea el saldo de apertura y la información de la actividad para todas las cuentas.                                                                                                                                                                                                                                                      |
| Saldo de comprobación detallado - predeterminado                         | Vea información de saldo para todas las cuentas que tengan saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                                                                                                                                  |
| Tendencia trimestral de tres años de gastos – predeterminado             | Obtenga información de los gastos de los últimos 12 trimestres durante los tres años anteriores.                                                                                                                                                                                                                                   |
| Revisión de JE y TB de títulos financieros – predeterminado            | Muestra una visión general de los saldos y de la actividad de los títulos financieros del activo, el pasivo, los recursos propios del propietario, los ingresos, los gastos, el incremento o las pérdidas o ganancias.                                                                                                                                                                           |
| Informe de ingresos – predeterminado                                | Vea la rentabilidad de la organización para el período actual y para el ejercicio hasta la fecha.                                                                                                                                                                                                                                   |
| Lista de transacciones contables – predeterminado                        | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito, junto con la información de transacciones adicional, como la fecha de transacción, el número de diario, el asiento, el tipo de registro y el número de seguimiento.                                                                            |
| Coeficientes – predeterminado                                          | Vea los coeficientes de solvencia, rentabilidad y eficiencia para la organización durante el año.                                                                                                                                                                                                                           |
| Gastos de 12 meses continuos – predeterminado                       | Obtenga información de los gastos de cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                                       |
| Informe de ingresos de trimestres continuos – predeterminado               | Vea la rentabilidad de la organización cada trimestre durante el último año y también del año hasta la fecha.                                                                                                                                                                                                                   |
| Balance de situación en paralelo – predeterminado                      | Vea la posición financiera de la organización para el año. Este informe muestras activos y pasivo y los recursos propios de los accionistas en paralelo.                                                                                                                                                                                |
| Resumen de saldo de comprobación – predeterminado                          | Vea la información de saldo para todas las cuentas que tienen saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                                                                                                                                                  |
| Resumen de saldo de comprobación año por año – predeterminado           | Vea la información de saldo para todas las cuentas que tienen saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior.                                                                                                                           |
| Ventas y descuentos semanales - predeterminado                     | Obtenga información de las ventas y los descuentos para cada semana de un mes. Este informe incluye un total de cuatro semanas.                                                                                                                                                                                                              |
| Depositar fondos presupuestarios disponibles - Valor predeterminado                         | Vea una comparación detallada de presupuesto revisado, gastos reales, reservas de presupuesto y fondos de presupuestos disponibles para todas las cuentas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura de informes financieros
Al hacer clic en el menú **Informes financieros**, se muestra la lista de informes financieros predeterminado para la empresa. A continuación, puede abrir o modificar un informe. Para abrir uno de los informes predeterminados, seleccione el nombre del informe. La primera vez que se abre un informe, se genera automáticamente para el mes anterior. Por ejemplo, si abre un informe por primera vez en agosto de 2016, el informe se genera para el 31 de julio de 2016. Tras abrir un informe, puede empezar a explorarlo profundizando en fragmentos específicos de datos y cambiando las opciones de informe.

## <a name="creating-and-modifying-financial-reports"></a>Creación y modificación de informes financieros
A partir de la lista de informes financieros, puede crear un nuevo informe o modificar un informe existente. Si dispone de los permisos adecuados, puede crear un nuevo informe financiero haciendo clic en **Nuevo** del panel de acciones. Se descarga un programa del diseñador de informes en el dispositivo. Una vez iniciado el diseñador de informes, puede crear el nuevo informe. Tras guardar el nuevo informe, aparece en la lista de informes financieros. En la lista se muestran solo los informes que se crearon para la empresa que está usando en Finance. 

> [!NOTE] 
> El equipo en el que está descargando el cliente del diseñador de informes debe tener instalada la versión 4.6.2 del Microsoft .NET Framework. Esta versión de Microsoft .NET Framework puede descargarse e instalarse desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53345). Si está usando Chrome, debe instalar una extensión ClickOnce para descargar el cliente del diseñador de informes. Si está ejecutando en modo ingógnito, asegúrese de que la extensión ClickOnce está activada para el modo incógnito. También puede modificar un informe que aparece en la lista de informes financieros. Cuando se seleccione el área alrededor del nombre del informe, haga clic en **Editar** en el Panel de acciones. Se inicia el programa del diseñador de informes.

## <a name="additional-resources"></a>Recursos adicionales
- [Ver informes financieros](view-financial-reports.md)



