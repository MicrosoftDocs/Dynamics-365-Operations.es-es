---
title: Contenido de Power BI de rendimiento financiero
description: "Este tema describe el Microsoft Dynamics 365 para el paquete del contenido del rendimiento financiero de operaciones para el BI de la potencia de Microsoft. Describe el panel y los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Contenido de Power BI de rendimiento financiero

Este tema describe el Microsoft Dynamics 365 para el paquete del contenido del rendimiento financiero de operaciones para el BI de la potencia de Microsoft. Describe el panel y los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

Dos versiones de embalaje del contenido del rendimiento financiero están disponibles. Una versión es disponible de los servicios (LCS) del ciclo de vida de Microsoft Dynamics, y otra está disponible en PowerBI.com.

-   ** Versión que está disponible en el CD: ** El paquete del contenido del rendimiento financiero que está disponible en el CD admite el Microsoft Dynamics 365 para la versión 1611 de las operaciones. Puede encontrar el paquete de contenido en la biblioteca compartida de activos en el CD. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a su Microsoft Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] ().
-   ** Versión disponible en PowerBI.com: ** El paquete del contenido del rendimiento financiero disponible en PowerBI.com admite las versiones 7.0 y 7.0.1 de Microsoft Dynamics AX. Para obtener más información sobre cómo conectar y cargar su Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI de acceso de PowerBI.com] () power-bi-home-page.md.

## <a name="main-account-setup"></a>Configuración de la cuenta principal
Dado que las organizaciones desean pasivos y importes de ingresos que desea que aparezcan como importes positivos en los informes, la configuración de las cuentas principales de Dynamics 365 para las operaciones es importante. Para que estas cuentas principales aparecen como importes positivos, el tipo de cuenta principal se debe establecer ** pasivo ** o ** ** ingresos. Cuando se utiliza a estos tipos de cuenta, notificando a través de Power BI de Microsoft invertirá los signos y los importes mostrará como positivo.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Panel e informes incluidos en el paquete de contenido
Tras la conexión del paquete de contenido con sus datos de Dynamics 365 for Operations, el panel de información y los informes muestran sus datos financieros. Si nunca se ha utilizado el BI de la potencia antes, puede obtener más información acerca de ella en [dirigido aprendiendo la página para el BI] de la potencia (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). El panel contiene los iconos resumidos de los datos que se basan en los informes subyacentes. Cada icono contiene la información resumida del año actual en todas las empresas de una organización. A continuación se muestran algunos de los mosaicos:

-   Efectivo
-   Ingresos totales este año
-   Total de gastos este año
-   Ingresos netos este año
-   Índice rápido
-   Total de gastos este año por categoría de cuenta
-   Índice actual
-   Deuda para activos totales
-   Ingresos reales frente a previstos
-   Ingresos facturados este año
-   Coeficiente de gastos de explotación este año
-   Margen de beneficio este año
-   Gastos reales frente a gastos de presupuesto – Todas las empresas

Cada mosaico es apoyado por un informe que admite. Estos informes contienen tanto gráficos como tablas que proporcionan más información. En la siguiente tabla se describen los informes.

| Informe                      | Información que el informe contiene                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Análisis de efectivo               | Efectivo de la entidad jurídica, efectivo por trimestre, efectivo total, y efectivo por la cuenta ** nota: ** ** Efectivo por trimestre ** el informe no incluye los saldos iniciales en el total del primer trimestre. Muestra el total de nuevas transacciones que se registren de cada trimestre.                                                                                |
| Análisis de índice actual      | Índice actual por entidad jurídica, índice actual por trimestre y saldos para activos actuales y pasivos actuales                                                                                                                                                                                                                              |
| Análisis de índice rápido        | Relación de transformación rápida de la entidad jurídica, proporción rápida por trimestre, y saldos del efectivo, los clientes, y los pasivos actuales                                                                                                                                                                                                                      |
| Análisis de coste de bienes vendidos | Coste de bienes vendidos (COGS) por entidad jurídica, COGS este año y el último año por trimestre, COGS para ventas por entidad jurídica, COGS total y COGS para porcentaje de ventas                                                                                                                                                                                   |
| Análisis de capital circulante    | Capital circulante por entidad jurídica, capital circulante por trimestre, activos actuales, pasivos actuales y capital circulante total                                                                                                                                                                                                                   |
| Análisis de deudas y activos     | Rentabilidad de activos totales y deuda de activos totales por entidad jurídica, deuda de activos totales y rentabilidad de activos totales de trimestre hasta la fecha, activos y pasivos                                                                                                                                                                                     |
| Análisis de margen de beneficio      | Margen de beneficio real y de presupueste por entidad jurídica, marcado de beneficio por trimestre, porcentaje de margen de beneficio y margen de beneficio                                                                                                                                                                                                                       |
| Análisis de ingresos netos         | Ingresos netos reales y de presupuesto por entidad jurídica, ingresos netos este año y el año pasado, y porcentaje de gastos para ingresos netos                                                                                                                                                                                                                       |
| Análisis de ganancias           | Ganancias reales y de presupuesto antes de intereses e impuestos (IAII) por entidad jurídica, IAII este año y el año pasado, porcentaje de gastos para ingresos, y gastos reales y de presupuesto para ingresos                                                                                                                                                          |
| Análisis de ingresos            | Ingresos totales, ingresos totales reales y de presupuesto por entidad jurídica, ingresos totales este año y el año pasado, varianza del presupuesto de ingresos por entidad jurídica e ingresos totales este y el último período                                                                                                                                                 |
| Análisis de gastos            | Total de gastos, total de gastos reales frente a los de presupuesto por entidad jurídica, total de gastos reales y de presupuesto por trimestre, total de gastos por categoría de cuenta y coeficiente de gastos de explotación                                                                                                                                                                 |
| Análisis de ingresos facturados     | Clientes totales, totales clientes de la entidad jurídica, clientes totales por trimestre, y saldos de las cuentas de clientes ** nota: ** Los informes no incluyen los saldos iniciales para las cuentas contables de los clientes. Se muestran el total de nuevas transacciones enviadas a los clientes. |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos que rellenen el panel y los informes del contenido del rendimiento financiero empaquetan son las Dynamics 365 para los datos de las operaciones. Usaban a las entidades siguientes como base del paquete de contenido: ** Entidades globales de los datos **

-   ** GeneralLedgerActivities ** – esta entidad agrega los saldos de contabilidad por categoría de cuenta.
-   ** BudgetActivities ** – esta entidad agrega los saldos presupuestarios por categoría de cuenta.

**Data entities**

-   Calendarios fiscales
-   Cuentas principales
-   Entidades jurídicas
-   Libros mayores
-   Planes contables:

Usaban a estas entidades para crear medidas calculadas en el modelo de datos. Se utilizan las medidas calculadas para calcular los indicadores clave de rendimiento (KPIs) y los informes que se utilizan en el paquete del contenido. De forma predeterminada, el paquete de contenido incluye datos de los tres últimos años y un año futuro. Para incluir cálculos adicionales sobre sus informes y panel de información, puede modificar el [libro de Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Este libro es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya terminado de realizar las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



