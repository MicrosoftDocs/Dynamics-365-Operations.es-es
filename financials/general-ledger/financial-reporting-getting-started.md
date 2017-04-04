---
title: Informes financieros
description: "Este tema describe en tener acceso a informes financieros en Microsoft Dynamics 365 para las operaciones y cómo usar las capacidades del informe financiero. Incluye una descripción de los informes financieros predeterminados que se le ofrecen."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d13747f17b5f382b3a530b1f166681eeec0b9d73
ms.lasthandoff: 03/31/2017


---

# <a name="financial-reporting"></a>Informes financieros

Este tema describe en tener acceso a informes financieros en Microsoft Dynamics 365 para las operaciones y cómo usar las capacidades del informe financiero. Incluye una descripción de los informes financieros predeterminados que se le ofrecen.

<a name="accessing-financial-reporting"></a>Acceso a informes financieros
-----------------------------

Puede encontrar ** informe financiero ** el menú en las ubicaciones siguientes de Dynamics 365 para las operaciones:

-   ** Contabilidad general ** &gt; ** consultas e informes **
-   ** Presupuestando ** &gt; ** investiga y informa ** &gt; ** la gestión presupuestaria básica **
-   ** ** ** &gt; Las consultas e informes de presupuesto ** &gt; ** el presupuesto se ha planificado **
-   ** ** ** &gt; Consultas e informes de presupuesto ** &gt; ** control presupuestario **
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
| Mantener informes financieros            | Mantener informes financieros            | Administrador contable, supervisor de estadísticas, auditora, director de presupuestos |
| Generar informes financieros            | Generar informes financieros            | Director financiero, CFO, contable                                                            |
| Ver informes financieros                | Revisar rendimiento financiero          | Ninguno asignado                                                                   |

Tras la adición de un usuario o el cambio de un rol, el usuario debe poder tener acceso a informes financieros al cabo de unos minutos. ** Nota: ** La función de control del sistema se agrega a todos los roles en informes financieros.

## <a name="default-reports"></a>Informes predeterminados
Los informes financieros proporcionan 22 informes financieros predeterminados. Cada informe usa las categorías de cuenta principal predeterminadas de Dynamics 365 para las operaciones. Puede usar estos informes tal cual o como punto de partida para las necesidades de informes financieros. Además de los informes financieros tradicionales, como Informe financiero y Balance de situación, estos informes predeterminados incluyen informes que muestran los diferentes tipos de informes financieros que puede crear. Cada informe en los vínculos siguientes de la tabla a una presentación de la combinación de la oficina por el informe.

| Informe predeterminado                                                                                         | Descripción                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12 Month Rolling Single Column Income Statement – Default](https://mix.office.com/watch/76kc7bm3wnt1) | Vea la rentabilidad de una organización durante los últimos 12 meses en una sola columna.                                                                                                                                                                                                                                      |
| [12 Month Trend Income Statement – Default](https://mix.office.com/watch/12brmfge5p8r)                 | Vea la rentabilidad de una organización para cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                             |
| [Actual vs Budget – Default](https://mix.office.com/watch/fi439lkwr0no)                                | Vea información detallada de saldo para todas las cuentas para el presupuesto original y compare el presupuesto revisado con los valores reales que tienen una desviación.                                                                                                                                                                          |
| [Audit Details – Default](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito en la divisa de notificación y la divisa local, junto con la información de transacciones adicional, como el id. de usuario, el usuario que modificó los datos por última vez, la fecha de la última modificación y el id. de diario. |
| [Balance List – Default](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de apertura y cierre, y los saldos de débito y crédito para el período actual y el año hasta la fecha, junto con la información de transacciones adicional, como el asiento.                                                                    |
| [Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                                   | Vea la posición financiera de la organización para el año.                                                                                                                                                                                                                                                             |
| [Balance Sheet and Income Statement Side by Side - Default](https://mix.office.com/watch/zkgq0u7visw9) | Ver la rentabilidad y posición financiera de la organización para el año de forma simultánea.                                                                                                                                                                                                                              |
| [Cash Flow – Default](https://mix.office.com/watch/jd3go9pz6390)                                       | Obtenga información del efectivo que entra y sale de la organización.                                                                                                                                                                                                                                   |
| [Detailed JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Vea el saldo de apertura y la información de la actividad para todas las cuentas.                                                                                                                                                                                                                                                      |
| [Detailed Trial Balance - Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Vea información de saldo para todas las cuentas que tengan saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                                                                                                                                  |
| [Expenses Three Year Quarterly Trend – Default](https://mix.office.com/watch/gwm4zu7tmtj8)             | Obtenga información de los gastos de los últimos 12 trimestres durante los tres años anteriores.                                                                                                                                                                                                                                   |
| [Financial Captions JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Muestra una visión general de los saldos y de la actividad de los títulos financieros del activo, el pasivo, los recursos propios del propietario, los ingresos, los gastos, el incremento o las pérdidas o ganancias.                                                                                                                                                                           |
| [Income Statement – Default](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Vea la rentabilidad de la organización para el período actual y para el ejercicio hasta la fecha.                                                                                                                                                                                                                                   |
| [Ledger Transaction List – Default](https://mix.office.com/watch/19h9v2rmh48vy)                        | Vea información detallada de saldo para todas las cuentas. Este informe muestra los saldos de débito y crédito, junto con la información de transacciones adicional, como la fecha de transacción, el número de diario, el asiento, el tipo de registro y el número de seguimiento.                                                                            |
| [Ratios – Default](https://mix.office.com/watch/b08hfc5h92me)                                          | Vea los coeficientes de solvencia, rentabilidad y eficiencia para la organización durante el año.                                                                                                                                                                                                                           |
| [Rolling 12 Month Expenses – Default](https://mix.office.com/watch/iywod5qmqhz7)                       | Obtenga información de los gastos de cada uno de los últimos 12 meses. Estos 12 meses pueden abarcar más de un ejercicio.                                                                                                                                                                                                       |
| [Rolling Quarter Income Statement – Default](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Ver la rentabilidad de la organización trimestralmente por el último año y el Año hasta la fecha.                                                                                                                                                                                                                   |
| [Side by Side Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                      | Vea la posición financiera de la organización para el año. Este informe muestras activos y pasivo y los recursos propios de los accionistas en paralelo.                                                                                                                                                                                |
| [Summary Trial Balance – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Vea la información de saldo para todas las cuentas que tienen saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                                                                                                                                                  |
| [Summary Trial Balance Year Over Year – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Ver información sobre el saldo para todas las cuentas con apertura y saldo de cierre, y el débito y los saldos de crédito junto con su diferencia neto por el año actual y el último año.                                                                                                                           |
| [Weekly Sales and Discounts - Default](https://mix.office.com/watch/112ng0hy5de0j)                     | Obtenga información de las ventas y los descuentos para cada semana de un mes. Este informe incluye un total de cuatro semanas.                                                                                                                                                                                                              |
| [Depositar fondos presupuestarios disponibles - Valor predeterminado (https://mix.office.com/watch/15hcpezcbx7tv)]                         | Ver una comparación detallada del presupuesto, de gastos reales, reservas de presupuesto, y de fondos de presupuesto revisados disponible para todas las cuentas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura de informes financieros
Al hacer clic en el menú **Informes financieros**, se muestra la lista de informes financieros predeterminado para la empresa. A continuación, puede abrir o modificar un informe. Para abrir uno de los informes predeterminados, seleccione el nombre del informe. La primera vez que se abre un informe, se genera automáticamente para el mes anterior. Por ejemplo, si abre un informe por primera vez en agosto de 2016, el informe se genera para el 31 de julio de 2016. Tras abrir un informe, puede empezar a explorarlo profundizando en fragmentos específicos de datos y cambiando las opciones de informe.

## <a name="creating-and-modifying-financial-reports"></a>Creación y modificación de informes financieros
A partir de la lista de informes financieros, puede crear un nuevo informe o modificar un informe existente. Si tiene los permisos adecuados, puede crear un nuevo informe financiero haciendo clic en ** nuevo ** en el panel de acciones. Programa del diseñador de informes se descarga al dispositivo. Una vez que el inicio del diseñador de informes pueda crear el nuevo informe. Tras guardar el nuevo informe, aparece en la lista de informes financieros. La lista muestra sólo los informes creados para la empresa que utiliza en Dynamics 365 para las operaciones. Para obtener más información acerca del proceso de creación y de modificar los informes financieros de Dynamics 365 para las operaciones, consulte a estos [los artículos para registrar] de blog (https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) de blog de los informes financieros de Dynamics. ** Nota: ** El equipo que se está descargando al cliente del diseñador de informes acerca de versión debe tener 4.6.2 del marco de Microsoft .NET instalado en él. Esta versión del marco de Microsoft .NET puede ser descargó y de instalar aquí [] (https://www.microsoft.com/en-us/download/details.aspx?id=53345). Si utiliza Cromada, debe instalar una extensión de ClickOnce para descargar el cliente del diseñador de informes. Si ejecuta en modo incógnito, asegúrese de que la extensión de ClickOnce esté habilitada para el modo incógnito. También puede modificar un informe que aparece en la lista de informes financieros. Cuando se seleccione el área alrededor del nombre del informe, haga clic en **Editar** en el Panel de acciones. Se inicia el programa del diseñador de informes.

<a name="see-also"></a>Consulte también
--------

[View financial reports](view-financial-reports.md)

[Blog de informes financieros de Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)


