---
title: Informes financieros
description: "Este tema describe cómo acceder a los informes financieros en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y cómo usar las capacidades de informes financieros. Incluye una descripción de los informes financieros predeterminados proporcionados."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ed207bdc04041ec2f21cb1038451fc75b8d061a1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="financial-reporting"></a>Informes financieros

[!include[banner](../includes/banner.md)]


Este tema describe cómo acceder a los informes financieros en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y cómo usar las capacidades de informes financieros. Incluye una descripción de los informes financieros predeterminados proporcionados.

<a name="accessing-financial-reporting"></a>Acceso a informes financieros
-----------------------------

Encontrará el menú **Informes financieros** en los dos siguientes lugares de Finance and Operations:

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
| Mantener seguridad de informes financieros | Mantener la seguridad de los informes financieros y realizar tareas administrativas. | FinancialReportsSecurityMaintain |
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

## <a name="default-reports"></a>Informes predeterminados
Los informes financieros proporcionan 22 informes financieros predeterminados. Cada informe usa las categorías de cuenta principal predeterminadas en Finance and Operations. Puede usar estos informes tal cual o como punto de partida para las necesidades de informes financieros. Además de los informes financieros tradicionales, como Informe financiero y Balance de situación, estos informes predeterminados incluyen informes que muestran los diferentes tipos de informes financieros que puede crear. Cada informe de la tabla siguiente se vincula con una presentación combinada de Office sobre el informe.

| Informe predeterminado                                                                                         | Descripción                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Informe de ingresos de columna única móvil de 12 meses – predeterminado](https://mix.office.com/watch/76kc7bm3wnt1) | Vea la rentabilidad de una organización durante los últimos 12 meses en una sola columna.                                                                                                                                                                                                                                      |
| [Informe de ingresos de tendencias de 12 meses – predeterminado](https://mix.office.com/watch/12brmfge5p8r)                 | Vea la rentabilidad de una organización para cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                             |
| [Real frente a presupuesto - predeterminado](https://mix.office.com/watch/fi439lkwr0no)                                | Vea información detallada de saldo para todas las cuentas para el presupuesto original y compare el presupuesto revisado con los valores reales que tienen una desviación.                                                                                                                                                                          |
| [Detalles de auditoría - predeterminado](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito en la divisa de notificación y la divisa local, junto con la información de transacciones adicional, como el id. de usuario, el usuario que modificó los datos por última vez, la fecha de la última modificación y el id. de diario. |
| [Lista de saldos - predeterminado](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de apertura y cierre, y los saldos de débito y crédito para el período actual y el año hasta la fecha, junto con la información de transacciones adicional, como el asiento.                                                                    |
| [Balance de situación - predeterminado](https://mix.office.com/watch/zkgq0u7visw9)                                   | Vea la posición financiera de la organización para el año.                                                                                                                                                                                                                                                             |
| [Balance de situación e informe de ingresos en paralelo - predeterminado](https://mix.office.com/watch/zkgq0u7visw9) | Ver la rentabilidad y posición financiera de la organización para el año de forma simultánea.                                                                                                                                                                                                                              |
| [Flujo de efectivo - predeterminado](https://mix.office.com/watch/jd3go9pz6390)                                       | Obtenga información del efectivo que entra y sale de la organización.                                                                                                                                                                                                                                   |
| [Revisión de JE y TB detallada – predeterminado](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Vea el saldo de apertura y la información de la actividad para todas las cuentas.                                                                                                                                                                                                                                                      |
| [Saldo de comprobación detallado - predeterminado](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Vea información de saldo para todas las cuentas que tengan saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                                                                                                                                  |
| [Tendencia trimestral de tres años de gastos – predeterminado](https://mix.office.com/watch/gwm4zu7tmtj8)             | Obtenga información de los gastos de los últimos 12 trimestres durante los tres años anteriores.                                                                                                                                                                                                                                   |
| [Revisión de JE y TB de títulos financieros – predeterminado](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Muestra una visión general de los saldos y de la actividad de los títulos financieros del activo, el pasivo, los recursos propios del propietario, los ingresos, los gastos, el incremento o las pérdidas o ganancias.                                                                                                                                                                           |
| [Informe de ingresos – predeterminado](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Vea la rentabilidad de la organización para el período actual y para el ejercicio hasta la fecha.                                                                                                                                                                                                                                   |
| [Lista de transacciones contables – predeterminado](https://mix.office.com/watch/19h9v2rmh48vy)                        | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito, junto con la información de transacciones adicional, como la fecha de transacción, el número de diario, el asiento, el tipo de registro y el número de seguimiento.                                                                            |
| [Coeficientes – predeterminado](https://mix.office.com/watch/b08hfc5h92me)                                          | Vea los coeficientes de solvencia, rentabilidad y eficiencia para la organización durante el año.                                                                                                                                                                                                                           |
| [Gastos de 12 meses continuos – predeterminado](https://mix.office.com/watch/iywod5qmqhz7)                       | Obtenga información de los gastos de cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                                       |
| [Informe de ingresos de trimestres continuos – predeterminado](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Vea la rentabilidad de la organización cada trimestre durante el último año y también del año hasta la fecha.                                                                                                                                                                                                                   |
| [Balance de situación en paralelo – predeterminado](https://mix.office.com/watch/zkgq0u7visw9)                      | Vea la posición financiera de la organización para el año. Este informe muestras activos y pasivo y los recursos propios de los accionistas en paralelo.                                                                                                                                                                                |
| [Resumen de saldo de comprobación – predeterminado](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Vea la información de saldo para todas las cuentas que tienen saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                                                                                                                                                  |
| [Resumen de saldo de comprobación año por año – predeterminado](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Vea la información de saldo para todas las cuentas que tienen saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior.                                                                                                                           |
| [Ventas y descuentos semanales - predeterminado](https://mix.office.com/watch/112ng0hy5de0j)                     | Obtenga información de las ventas y los descuentos para cada semana de un mes. Este informe incluye un total de cuatro semanas.                                                                                                                                                                                                              |
| [Depositar fondos presupuestarios disponibles - Valor predeterminado](https://mix.office.com/watch/15hcpezcbx7tv)                         | Vea una comparación detallada de presupuesto revisado, gastos reales, reservas de presupuesto y fondos de presupuestos disponibles para todas las cuentas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura de informes financieros
Al hacer clic en el menú **Informes financieros**, se muestra la lista de informes financieros predeterminado para la empresa. A continuación, puede abrir o modificar un informe. Para abrir uno de los informes predeterminados, seleccione el nombre del informe. La primera vez que se abre un informe, se genera automáticamente para el mes anterior. Por ejemplo, si abre un informe por primera vez en agosto de 2016, el informe se genera para el 31 de julio de 2016. Tras abrir un informe, puede empezar a explorarlo profundizando en fragmentos específicos de datos y cambiando las opciones de informe.

## <a name="creating-and-modifying-financial-reports"></a>Creación y modificación de informes financieros
A partir de la lista de informes financieros, puede crear un nuevo informe o modificar un informe existente. Si dispone de los permisos adecuados, puede crear un nuevo informe financiero haciendo clic en **Nuevo** del panel de acciones. Se descarga un programa del diseñador de informes en el dispositivo. Una vez iniciado el diseñador de informes, puede crear el nuevo informe. Tras guardar el nuevo informe, aparece en la lista de informes financieros. En la lista se muestran solo los informes que se crearon para la empresa que está usando en Finance and Operations. Para obtener más información sobre el proceso de creación y modificación de informes financieros en Finance and Operations, consulte estos [artículos de blog](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) en el blog de informes financieros de Dynamics. **Nota:** El equipo en el que está descargando el cliente del diseñador de informes debe tener instalada la versión 4.6.2 del Microsoft .NET Framework. Esta versión de Microsoft .NET Framework puede descargarse e instalarse desde [aquí](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Si está usando Chrome, debe instalar una extensión ClickOnce para descargar el cliente del diseñador de informes. Si está ejecutando en modo ingógnito, asegúrese de que la extensión ClickOnce está activada para el modo incógnito. También puede modificar un informe que aparece en la lista de informes financieros. Cuando se seleccione el área alrededor del nombre del informe, haga clic en **Editar** en el Panel de acciones. Se inicia el programa del diseñador de informes.

<a name="see-also"></a>Consulte también
--------

[Ver informes financieros](view-financial-reports.md)

[Blog de informes financieros de Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




