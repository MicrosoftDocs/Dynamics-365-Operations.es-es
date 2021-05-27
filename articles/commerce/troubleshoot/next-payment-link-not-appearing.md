---
title: La opción Guardar para mi próximo pago no aparece
description: Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla Guardar para mi próximo pago no aparece en Método de pago en la página de pago de un sitio de comercio electrónico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018443"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>La opción "Guardar para mi próximo pago" no aparece

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla **Guardar para mi próximo pago** no aparece en **Método de pago** en la página de pago de un sitio de comercio electrónico.

## <a name="description"></a>Descripción

La casilla **Guardar para mi próximo pago** no aparece en la sección **Método de pago** de la página de pago de un sitio de comercio electrónico.

La siguiente ilustración muestra un ejemplo de una página de pago que incluye la casilla **Guardar para mi próximo pago**.

![Casilla Guardar para mi próximo pago en el módulo Pagos](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Resolución

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Verifique que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce

Para verificar que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.
1. Seleccione la tienda en línea.
1. En la ficha desplegable **Cuentas de pago**, asegúrese de que el campo **Permitir guardar información de pago en comercio electrónico** esté establecido en **Verdadero**.

![Permitir guardar información de pago en el campo de comercio electrónico en la sede de Commerce](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de pago](../payment-module.md)

[Guardar los instrumentos de pago en línea con el conector de Adyen](../dev-itpro/adyen-connector-listPI.md)
