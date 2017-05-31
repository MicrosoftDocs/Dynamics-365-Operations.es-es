---
title: Contenido de Power BI sobre rendimiento financiero
description: "Este artículo describe el paquete de contenido de rendimiento financiero de Microsoft Dynamics 365 for Operations para Microsoft Power BI. Describe el panel de información y los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9cd1d7e5b7b1fd892034dcca0a0c141363104a45
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="financial-performance-power-bi-content"></a>Contenido de Power BI sobre rendimiento financiero

[!include[banner](../includes/banner.md)]


Este artículo describe el paquete de contenido de rendimiento financiero de Microsoft Dynamics 365 for Operations para Microsoft Power BI. Describe el panel de información y los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

Hay dos versiones del paquete de contenido sobre rendimiento financiero. Hay una versión disponible en Microsoft Dynamics Lifecycle Services (LCS) y la otra en PowerBI.com.

-   **Versión disponible en LCS:** el paquete de contenido de rendimiento financiero que está disponible en LCS admite Microsoft Dynamics 365 for Operations versión 1611. El paquete de contenido se encuentra en la biblioteca de activos compartidos de LCS. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Microsoft Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).
-   **Versión disponible en PowerBI.com:** el paquete de contenido de rendimiento financiero que está disponible en PowerBI.com admite Microsoft Dynamics AX versión 7.0 y 7.0.1. Para obtener más información sobre cómo conectar y cargar los datos de Dynamics 365 for Operations, consulte [Acceso al contenido de Power BI en PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Configuración de la cuenta principal
Debido a que las organizaciones quieren que los ingresos aparezcan como cantidades positivas en los informes, la configuración de las cuentas principales en Dynamics 365 for Operations es importante. Para que esas cuentas principales aparezcan como importes positivos, el tipo de cuenta principal debe definirse como **Pasivo** o **Ingreso**. Al utilizar estos tipos de cuentas, los informes de Microsoft Power BI invertirán los signos y mostrarán los importes como positivos.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Panel de información e informes incluidos en el paquete de contenido
Tras la conexión del paquete de contenido con sus datos de Dynamics 365 for Operations, el panel de información y los informes muestran sus datos financieros. Si nunca ha utilizado Microsoft Power BI antes, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. El panel contiene los iconos resumidos de los datos que se basan en los informes subyacentes. Cada icono contiene la información resumida del año actual en todas las empresas de una organización. Estos son algunos de estos iconos:

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

Cada icono viene respaldado por un informe auxiliar. Estos informes contienen tanto gráficos como tablas que proporcionan más información. En la siguiente tabla se describen los informes.

| Informe                      | Información que el informe contiene                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Análisis de efectivo               | Efectivo por entidad jurídica, efectivo por trimestre, efectivo total y efectivo por cuenta **Nota:** el informe **Efectivo por trimestre** no incluye los saldos iniciales en el total del primer trimestre. Muestra el total de nuevas transacciones contabilizadas en cada trimestre.                                                                                |
| Análisis de índice actual      | Índice actual por entidad jurídica, índice actual por trimestre y saldos para activos actuales y pasivos actuales                                                                                                                                                                                                                              |
| Análisis de índice rápido        | Índice rápido por entidad jurídica, índice rápido por trimestre y saldos para efectivo, clientes y pasivos actuales                                                                                                                                                                                                                      |
| Análisis de coste de bienes vendidos | Coste de bienes vendidos (COGS) por entidad jurídica, COGS este año y el último año por trimestre, COGS para ventas por entidad jurídica, COGS total y COGS para porcentaje de ventas                                                                                                                                                                                   |
| Análisis de capital circulante    | Capital circulante por entidad jurídica, capital circulante por trimestre, activos actuales, pasivos actuales y capital circulante total                                                                                                                                                                                                                   |
| Análisis de deudas y activos     | Rentabilidad de activos totales y deuda de activos totales por entidad jurídica, deuda de activos totales y rentabilidad de activos totales de trimestre hasta la fecha, activos y pasivos                                                                                                                                                                                     |
| Análisis de margen de beneficio      | Margen de beneficio real y de presupueste por entidad jurídica, marcado de beneficio por trimestre, porcentaje de margen de beneficio y margen de beneficio                                                                                                                                                                                                                       |
| Análisis de ingresos netos         | Ingresos netos reales y de presupuesto por entidad jurídica, ingresos netos este año y el año pasado, y porcentaje de gastos para ingresos netos                                                                                                                                                                                                                       |
| Análisis de ganancias           | Ganancias reales y de presupuesto antes de intereses e impuestos (IAII) por entidad jurídica, IAII este año y el año pasado, porcentaje de gastos para ingresos, y gastos reales y de presupuesto para ingresos                                                                                                                                                          |
| Análisis de ingresos            | Ingresos totales, ingresos totales reales y de presupuesto por entidad jurídica, ingresos totales este año y el año pasado, varianza del presupuesto de ingresos por entidad jurídica e ingresos totales este y el último período                                                                                                                                                 |
| Análisis de gastos            | Total de gastos, total de gastos reales frente a los de presupuesto por entidad jurídica, total de gastos reales y de presupuesto por trimestre, total de gastos por categoría de cuenta y coeficiente de gastos de explotación                                                                                                                                                                 |
| Análisis de ingresos facturados     | Total de clientes, total de clientes por entidad jurídica, total de clientes por trimestre y saldos de cuentas de clientes **Nota:** los informes no incluyen los saldos iniciales de las cuentas contables de clientes. Muestran el total de las transacciones nuevas registradas en Clientes. |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos que rellenan el panel de información y los informes del paquete de contenido de rendimiento financiero son datos de Dynamics 365 for Operations. Las siguientes entidades se usaban como la base del paquete de contenido: **Entidades de datos agregados**

-   **GeneralLedgerActivities**: esta entidad agrega saldos de contabilidad general por categoría de cuenta.
-   **BudgetActivities**: esta entidad agrega saldos presupuestarios por categoría de cuenta.

**Entidades de datos**

-   Calendarios fiscales
-   Cuentas principales
-   Entidades jurídicas
-   Libros mayores
-   Planes contables:

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. La medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el paquete del contenido. De forma predeterminada, el paquete de contenido incluye datos de los tres últimos años y un año futuro. Para incluir cálculos adicionales sobre sus informes y panel de información, puede modificar el [libro de Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Este libro es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya terminado de realizar las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)





