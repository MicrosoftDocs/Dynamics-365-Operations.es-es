---
title: Solución PowerBI.com sobre rendimiento financiero
description: Este artículo describe la solución PowerBI.com sobre rendimiento financiero.
author: kweekley
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcbe41d113ee41734020546388851afb7fc27bbf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910426"
---
# <a name="financial-performance-powerbicom-solution"></a>Solución PowerBI.com sobre rendimiento financiero

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Esta solución de PowerBI.com se ha dejado de utilizar como se documenta en [Características eliminadas u obsoletas de Finance and Operations](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Este artículo describe la solución PowerBI.com sobre **rendimiento financiero**. Describe el panel de información y los informes incluidos y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar la solución.

## <a name="main-account-setup"></a>Configuración de la cuenta principal
Debido a que las organizaciones quieren que los ingresos aparezcan como cantidades positivas en los informes, la configuración de las cuentas principales es importante. Para que esas cuentas principales aparezcan como importes positivos, el tipo de cuenta principal debe definirse como **Pasivo** o **Ingreso**. Al utilizar estos tipos de cuentas, los informes de Power BI invertirán los signos y mostrarán los importes como positivos.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>Panel de información e informes incluidos en la solución PowerBI.com
El panel contiene los iconos resumidos de los datos que se basan en los informes subyacentes. Cada icono contiene la información resumida del año actual en todas las empresas de una organización. Estos son algunos de estos iconos:

- Efectivo
- Ingresos totales este año
- Total de gastos este año
- Ingresos netos este año
- Índice rápido
- Total de gastos este año por categoría de cuenta
- Índice actual
- Deuda para activos totales
- Ingresos reales frente a previstos
- Ingresos facturados este año
- Coeficiente de gastos de explotación este año
- Margen de beneficio este año
- Gastos reales frente a gastos de presupuesto – Todas las empresas

Cada icono viene respaldado por un informe auxiliar. Estos informes contienen tanto gráficos como tablas que proporcionan más información. En la siguiente tabla se describen los informes.

| Informe                      | Información que el informe contiene |
|-----------------------------|--------------------------------------|
| Análisis de efectivo               | Efectivo por entidad jurídica, efectivo por trimestre, efectivo total y efectivo por cuenta<blockquote>[!NOTE] El efectivo por la información del trimestre no incluye los saldos iniciales en el total del primer trimestre. Muestra el total de nuevas transacciones contabilizadas en cada trimestre.</blockquote> |
| Análisis de índice actual      | Índice actual por entidad jurídica, índice actual por trimestre y saldos para activos actuales y pasivos actuales |
| Análisis de índice rápido        | Índice rápido por entidad jurídica, índice rápido por trimestre y saldos para efectivo, clientes y pasivos actuales |
| Análisis de coste de bienes vendidos | Coste de bienes vendidos (COGS) por entidad jurídica, COGS este año y el último año por trimestre, COGS para ventas por entidad jurídica, COGS total y COGS para porcentaje de ventas |
| Análisis de capital circulante    | Capital circulante por entidad jurídica, capital circulante por trimestre, activos actuales, pasivos actuales y capital circulante total |
| Análisis de deudas y activos     | Rentabilidad de activos totales y deuda de activos totales por entidad jurídica, deuda de activos totales y rentabilidad de activos totales de trimestre hasta la fecha, activos y pasivos |
| Análisis de margen de beneficio      | Margen de beneficio real y de presupueste por entidad jurídica, marcado de beneficio por trimestre, porcentaje de margen de beneficio y margen de beneficio |
| Análisis de ingresos netos         | Ingresos netos reales y de presupuesto por entidad jurídica, ingresos netos este año y el año pasado, y porcentaje de gastos para ingresos netos |
| Análisis de ganancias           | Ganancias reales y de presupuesto antes de intereses e impuestos (IAII) por entidad jurídica, IAII este año y el año pasado, porcentaje de gastos para ingresos, y gastos reales y de presupuesto para ingresos |
| Análisis de ingresos            | Ingresos totales, ingresos totales reales y de presupuesto por entidad jurídica, ingresos totales este año y el año pasado, varianza del presupuesto de ingresos por entidad jurídica e ingresos totales este y el último período |
| Análisis de gastos            | Total de gastos, total de gastos reales frente a los de presupuesto por entidad jurídica, total de gastos reales y de presupuesto por trimestre, total de gastos por categoría de cuenta y coeficiente de gastos de explotación |
| Análisis de ingresos facturados     | El total de clientes, total de clientes por entidad jurídica, total de clientes por trimestre y saldos de cuentas de clientes<blockquote>[!NOTE] La información no incluye los saldos iniciales para las cuentas contables de los clientes. Muestra el total de las transacciones nuevas registradas en Clientes.</blockquote> |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Las siguientes entidades se usaban como la base de la solución PowerBI.com de **Rendimiento financiero**:

**Entidades de datos agregados**

- **GeneralLedgerActivities**: esta entidad agrega saldos de contabilidad general por categoría de cuenta.
- **BudgetActivities**: esta entidad agrega saldos presupuestarios por categoría de cuenta.

**Entidades de datos**

- Calendarios fiscales
- Cuentas principales
- Entidades jurídicas
- Libros mayores
- Planes contables:

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. La medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el contenido. De forma predeterminada, el contenido incluye datos de los tres últimos años y un año futuro. Para incluir cálculos adicionales sobre sus informes y panel de información, puede modificar el [libro de Microsoft Excel](/dynamics/s-e/). Este libro es el modelo de datos predeterminado usado para crear el contenido.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]