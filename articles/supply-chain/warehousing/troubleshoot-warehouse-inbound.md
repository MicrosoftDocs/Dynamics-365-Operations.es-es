---
title: Solucionar problemas de operaciones de almacén de entrada
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970264"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Solucionar problemas de operaciones de almacén de entrada

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Recibo el siguiente mensaje de error: "Pedido de calidad %1 ha sido generado. No se encuentra el perfil de clúster. Compruebe la configuración".

### <a name="issue-description"></a>Descripción del problema

Este mensaje de error está relacionado con un proceso de recepción donde la gestión de la calidad (QMS) está activada. Según las configuraciones de su entorno, los detalles adicionales sobre la transacción que genera el mensaje de error pueden ayudar a solucionar el problema.

### <a name="issue-resolution"></a>Solución del problema

Primero, revise la configuración de la [selección de clúster](set-up-cluster-picking.md) y asegúrese de que los perfiles de clúster estén configurados correctamente. No puede utilizar un elemento del menú de un dispositivo móvil para la selección de grupos a menos que se configuren perfiles de grupos. Dependiendo de su entorno, es posible que también deba revisar otras configuraciones relacionadas.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>La recepción de matrículas mixtas no funciona para ningún código de disposición, excepto Crédito.

### <a name="issue-description"></a>Descripción del problema

Cuando el campo **Acción** para un código de disposición se establece en *Crédito* o *Chatarra*, puede usar solo el elemento de menú [Recepción de matrículas mixtas](mixed-license-plate-receiving.md) para procesar elementos devueltos.

### <a name="issue-resolution"></a>Solución del problema

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, solo se admiten [códigos de disposición](../service-management/set-up-disposition-codes.md) donde el campo **Acción** está configurado en *Crédito* o *Chatarra* para la recepción de matrículas mixtas.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Cuando ejecuto la tarea periódica Actualizar recibos de productos, se confirman los pedidos de compra no confirmados.

### <a name="issue-description"></a>Descripción del problema

Después de ejecutar la tarea periódica *Actualizar recibos de productos*, el sistema confirma automáticamente las órdenes de compra no confirmadas que tienen un estado de transacción de inventario de *Registrado*.

### <a name="issue-resolution"></a>Solución del problema

Una nueva función de manipulación de carga entrante, *Sobre recepción de cantidades de carga*, soluciona este problema. Para activar esta característica, vaya a [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las siguientes características (en el mismo orden):

1. Asociar transacciones de inventario de pedido de compra a carga
1. Recepción en exceso de cantidades de carga

Para más información, vea [Contabilice las cantidades de producto registradas contra las órdenes de compra](inbound-load-handling.md#post-registered-quantities).
