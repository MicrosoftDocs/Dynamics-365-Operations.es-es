---
title: Contenido de administración de créditos y cobros de Power BI
description: Este artículo describe lo que se incluye en el contenido en Power BI de Administración de créditos y cobros. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.
author: ShivamPandey-msft
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 350c7ff2f0fa93d4ff99e2a11b9418413854a076
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889943"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Contenido de administración de créditos y cobros de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe lo que se incluye en el contenido de **Administración de créditos y cobros** en Microsoft Power BI. Explica cómo obtener acceso a los informes Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido en Power BI de **Administración de créditos y cobros** se creó para los administradores de créditos y cobros y los empleados de cobros. Proporciona métricas clave de créditos y cobros, como las ventas de los días pendientes, saldos vencidos, exposición crediticia y los clientes que sobrepasan su límite de crédito. Usa datos transaccionales y ofrece las vistas globales de créditos y cobros en todas las empresas. También proporciona un desglose por empresa, grupo de clientes y cliente.

Este contenido en Power BI consta de 10 páginas de informe:

- Dos páginas de visión general (una página para la visión general de créditos y una página para la visión general de cobros)
- Ocho páginas de detalles que proporcionan detalles de las métricas de crédito y de cobros que vienen desglosadas y articuladas en distintas dimensiones

Todos los importes se muestran en la divisa del sistema. Puede establecer la divisa del sistema en la página **Parámetros del sistema** .

De forma predeterminada, se muestran los datos sobre créditos y cobros para la empresa actual. Para ver los datos en todas las empresas, asigne el deber **CustCollectionsBICrossCompany** al rol.

## <a name="setup-needed-to-view-power-bi-content"></a>Configuración necesaria para ver el contenido de Power BI

Es necesario completar la siguiente configuración para que los datos se muestren en los elementos visuales de Power BI **Crédito y cobros de clientes**.

1. Vaya a **Administración del sistema > Configuración > Parámetros del sistema** para establecer **Divisa del sistema** y **Tipo de cambio del sistema**.
2. Para validar las fechas del calendario fiscal asignadas al período de tiempo activo, vaya a **Contabilidad general > Calendarios > Calendarios fiscales**.
3. Vaya a **Contabilidad general > Configuración > Libro mayor** y establezca **Divisa de contabilidad** y **Tipo de cambio**.
4. Defina los tipos de cambio entre las divisas de transacción y la divisa de contabilidad, la divisa de contabilidad, y la divisa del sistema. Para ello, vaya a **Contabilidad general > Divisas > Tipos de cambio de divisas**.
5. Vaya a **Administración del sistema > Configuración > Almacén de entidades** para actualizar la medida agregada **CustCollectionsBIMeasurementsV2**.

>[!NOTE] 
> Las definiciones del período de vencimiento deben configurarse en **Parámetros de clientes > Cobros> Valores predeterminados de cobros** para habilitar datos de vencimiento en el contenido de Power BI.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

El contenido de Power BI **Administración de créditos y cobros** se muestra en el área de trabajo **Crédito y cobros de clientes**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

El contenido en Power BI de **CustCollectionsBICrossCompany** incluye un informe compuesto por un conjunto de métricas. Estas métricas se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona una visión general de las visualizaciones en el contenido de **CustCollectionsBICrossCompany** en Power BI.

| Página de informes                 | Visualización |
|-----------------------------|---------------|
| Visión general de los cobros        | <ul><li>Actividad de cliente vencida</li><li>Clientes sobre límite de crédito</li><li>30 días de DSO</li><li>Casos abiertos</li><li>Promedio de días para cerrar el caso</li><li>Actividades abiertas</li><li>Promedio de días para cerrar las actividades</li><li>Abrir notas de interés</li><li>Abrir cartas de cobro</li><li>Cliente en espera</li><li>Ventas en espera</li><li>Saldos vencidos</li><li>Importes de estado de cobro</li><li>Importes de código de cobro</li><li>Motivo de cancelación</li><li>Saldo vencido por región</li><li>Pagos previstos</li></ul> |
| Visión general de crédito             | <ul><li>Actividad de cliente vencida</li><li>Límite de crédito frente a saldo pendiente</li><li>Cuadrícula de clientes sobre límite de crédito</li><li>Clientes sobre límite de crédito por empresa</li><li>Crédito utilizado frente a límite de crédito total</li><li>Límite de crédito frente a crédito usado por región</li><li>Clientes por clasificación crediticia</li></ul> |
| Límite de crédito                | <ul><li>Límite de crédito</li><li>Detalles de límite de crédito</li><li>Límite de crédito por cliente</li><li>Límite de crédito por grupo de clientes</li><li>Límite de crédito por clasificación crediticia por empresa</li><li>Límite de crédito frente a crédito usado por región</li></ul> |
| Clientes sobre límite de crédito | <ul><li>Clientes sobre límite de crédito</li><li>Detalle de clientes sobre límite de crédito</li><li>Clientes sobre límite de crédito por empresa</li><li>Cliente sobre límite de crédito por grupo de clientes</li><li>Clientes sobre límite de crédito por región</li></ul> |
| Actividad de cliente vencida          | <ul><li>Actividad de cliente vencida</li><li>Detalles sobre cliente vencido</li><li>Cliente vencido por empresa</li><li>Cliente vencido por grupo de clientes</li><li>Cliente vencido por región</li></ul> |
| Saldos vencidos               | <ul><li>Saldos vencidos</li><li>Detalles de saldos vencidos</li><li>Saldos vencidos por empresa</li><li>Saldos vencidos por grupo de clientes</li></ul> |
| Pagos previstos           | <ul><li>Pagos previstos</li><li>Detalles de pagos previstos</li><li>Pagos previstos por empresa</li><li>Pagos previstos por grupo de clientes</li><li>Pagos previstos por región</li></ul> |
| Cancelaciones                  | <ul><li>Cancelaciones por región</li><li>Detalles de las cancelaciones</li><li>Cancelaciones por cuenta principal</li><li>Cancelaciones por empresa</li><li>Cancelaciones por grupo de clientes</li><li>Cancelaciones por región</li></ul> |
| Estado de cobros          | <ul><li>Con conflicto</li><li>Compromiso de pago roto</li><li>Compromiso de pago</li><li>Detalles de estado de cobros</li><li>Importes de estado de cobro</li><li>Casos abiertos</li><li>Actividades abiertas</li></ul> |
| Cartas de cobros         | <ul><li>Importes por código de cobro</li><li>Detalles de importes por código de cobro</li><li>Importe de cartas de cobro por empresa</li><li>Importe de carta de cobro por grupo de clientes</li><li>Importe de carta de cobro por región</li></ul> |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). También puede usar la funcionalidad subyacente de exportación de datos para exportar los datos subyacente que se resume en una visualización.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
