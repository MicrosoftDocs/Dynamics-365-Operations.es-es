---
title: Tareas periódicas de gestión de crédito.
description: En este artículo se describen las tareas periódicas que son parte del proceso de administración de los límites de crédito para los clientes.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9ad72463acba301f7fc931f9fe316a9a9758922e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888017"
---
# <a name="periodic-credit-management-tasks"></a>Tareas periódicas de gestión de crédito.

[!include [banner](../includes/banner.md)]

En este artículo se describen las tareas periódicas que son parte del proceso de administración de los límites de crédito para los clientes.

## <a name="update-risk-scores"></a>Actualizar clasificaciones del riesgo

A medida que las empresas evolucionan y las circunstancias cambian, los riesgos de crédito para un cliente determinado también pueden cambiar. Para ayudar a mantener los límites de crédito apropiados para sus clientes debe revisar periódicamente los criterios para cada puntuación de riesgo y actualizar las puntuaciones para cada cliente. Puede actualizar las siguientes puntuaciones a través de la página **Actualizar puntajes de riesgo** (**Créditos y cobros \> Tareas periódicas \> Administración de crédito \> Actualizar puntuaciones de riesgo**). Todos los cálculos definidos por el usuario también se procesan.

- **Media de días para efectuar el pago**: este puntuación es el número medio de días que un cliente tarda en pagar las facturas.
- **Cliente desde**: esta puntuación es el número de años que un cliente ha sido cliente de su organización.
- **Opera desde**: esta puntuación es el número de años que lleva un cliente en el negocio. Utiliza el valor del campo **Inicio del negocio** en la página **Clientes**.
- **Ventas diarias pendientes**: esta puntuación se basa en el saldo de clientes, los ingresos por ventas y la cantidad de días para el período de 12 meses anterior.
- **Saldo medio**: esta puntuación se basa en el saldo de clientes del período de 12 meses anterior.
- **Grupo de administración de crédito**, **Estado de cuenta** y **País**: estas puntuaciones utilizan información del cliente.

## <a name="update-customer-balance-statistics"></a>Actualizar las estadísticas de saldo del cliente

Puede ejecutar el proceso **Actualizar las estadísticas de saldo del cliente** para actualizar el cálculo de estadísticas de saldo que se muestra en la página **Consulta de estadísticas de saldo**. Esta información se usa para calcular las puntuaciones de riesgo y los valores que se muestran en los cuadros de datos de estadísticas de crédito en la página **Cliente**.

Al ejecutar el proceso, actualiza las estadísticas de saldo de cliente para un solo cliente. Para configurar un trabajo por lotes con el fin de ejecutar el proceso para varios clientes, puede usar la página **Calcular estadísticas de saldo** (**Administración de crédito \> Tareas periódicas \> Calcular estadísticas de saldo**).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
