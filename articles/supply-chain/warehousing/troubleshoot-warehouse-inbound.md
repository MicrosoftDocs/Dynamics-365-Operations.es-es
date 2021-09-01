---
title: Solucionar problemas de operaciones de almacén de entrada
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de entrada en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6d7fcb2ed32c57b8701bee5b90889a0a63e1f7061aa9014480ae8c543e1f229a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748676"
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

Una nueva función de manipulación de carga entrante, *Sobre recepción de cantidades de carga*, soluciona este problema. Para activar esta característica, vaya al espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las siguientes características (en el mismo ordenen que se enumeran):

1. Asociar transacciones de inventario de pedido de compra a carga
1. Recepción en exceso de cantidades de carga

Para más información, vea [Contabilice las cantidades de producto registradas contra las órdenes de compra](inbound-load-handling.md#post-registered-quantities).

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>Cuando registro pedidos entrantes, recibo el siguiente mensaje de error: "La cantidad no es válida".

### <a name="issue-description"></a>Descripción del problema

Si el campo **Directiva de agrupación de matrículas** está configurado en *Definido por el usuario* para un elemento de menú de dispositivo móvil que se utiliza para registrar pedidos entrantes, recibe un mensaje de error ("La cantidad no es válida") y no puede completar el registro.

### <a name="issue-cause"></a>Causa del problema

Cuándo *Definido por el usuario* se utiliza como una directiva de agrupación de matrículas, el sistema divide el inventario entrante en matrículas separadas, como lo indica el grupo de secuencia de unidades. Si se utilizan números de lote o de serie para rastrear el artículo que se está recibiendo, las cantidades de cada lote o serie deben especificarse por matrícula registrada. Si la cantidad que se especifica para una matrícula excede la cantidad que aún debe recibirse para las dimensiones actuales, recibirá el mensaje de error.

### <a name="issue-resolution"></a>Solución del problema

Cuando registra un elemento utilizando un elemento de menú de dispositivo móvil donde el campo **Directiva de agrupación de matrículas** el campo está configurado en *Definido por el usuario*, es posible que el sistema requiera que confirme o ingrese números de matrícula, números de lote o números de serie.

En la página de confirmación de la matrícula, el sistema mostrará la cantidad asignada para la matrícula actual. En las páginas de confirmación del lote o de la serie, el sistema mostrará la cantidad que aún debe recibirse en la matrícula actual. También incluirá un campo donde puede ingresar la cantidad a registrar para esa combinación de placa y lote o número de serie. En este caso, asegúrese de que la cantidad que se está registrando para la matrícula no exceda la cantidad que aún debe recibirse.

Alternativamente, si se generan demasiadas matrículas en el registro de pedidos entrantes, el valor del campo **Directiva de agrupación de matrículas** se puede cambiar a *Agrupación de matrículas*, se puede asignar un nuevo grupo de secuencia de unidades al artículo, o la opción **Agrupación de matrículas** para el grupo de secuencia de unidades se puede desactivar.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
