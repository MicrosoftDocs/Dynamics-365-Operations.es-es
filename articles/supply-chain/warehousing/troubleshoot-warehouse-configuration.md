---
title: Solución de problemas de configuración de almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al configurar Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 09b5770190fea9591f422b61ce6deedb2b9fa790
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994012"
---
# <a name="troubleshoot-warehouse-configuration"></a>Solución de problemas de configuración de almacén

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al configurar Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Recibo el siguiente mensaje de error: "La matrícula o la ubicación no es válida".

### <a name="issue-description"></a>Descripción del problema

Recibe este mensaje de error cuando escanea la identificación o ubicación de una placa de matrícula.

### <a name="issue-resolution"></a>Solución del problema

Asegúrese de que la identificación de la matrícula no esté reservada por otra persona. Este problema solía ocurrir cuando el valor que un usuario escaneaba en la aplicación del almacén era tanto una ubicación válida como una identificación de matrícula válida. Sin embargo, este problema se resolvió en la versión 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Recibo el siguiente mensaje de error: "La matrícula se debe especificar para esta ubicación".

### <a name="issue-description"></a>Descripción del problema

Recibirá este mensaje de error si crea una orden de transferencia utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y, luego, una vez completado el trabajo, intenta confirmar el envío.

### <a name="issue-resolution"></a>Solución del problema

El campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde". Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito. Asegúrese de que esta ubicación esté controlada por matrículas.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Recibo el siguiente mensaje de error: "No puede crear una línea de plantilla de trabajo para el cambio de estado de inventario porque el tipo de trabajo no es válido. Seleccione un tipo de trabajo diferente ".

### <a name="issue-description"></a>Descripción del problema

Para una plantilla de trabajo, no puede seleccionar *Cambio de estado de inventario* en la columna **Tipo de trabajo** columna de la sección **Detalles de la plantilla de trabajo**.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. El tipo de trabajo *Cambio de estado de inventario* solo lo utilizan los procesos del sistema. No se puede configurar. Debido a que la lista de tipos de trabajo se fija como una enumeración, las entradas adicionales no se pueden filtrar del menú desplegable **Tipo de trabajo**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Recibo el siguiente mensaje de error: "La cantidad no es válida para la unidad 1%".

### <a name="issue-description"></a>Descripción del problema

La cantidad no es válida para la unidad *ea* cuando hay trabajo de recolección que tiene varias placas en un solo lugar.

### <a name="issue-resolution"></a>Solución del problema

Verifique que los campos **ID de grupo de secuencia de unidad** y **Conversiones de unidades** del producto lanzado o la variante del producto están configurados correctamente.

Tenga en cuenta que el mensaje de error se ha mejorado en la versión 10.0.15 (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). El nuevo mensaje de error es "La cantidad no es válida. Se esperaba %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>En las directivas de ubicación para el trabajo de colocación de pedidos de ventas, la opción de SKU múltiple no evalúa múltiples acciones de directiva de ubicación.

### <a name="issue-description"></a>Descripción del problema

Las directivas de ubicación del tipo de orden de trabajo *Ordenes de venta* y del tipo de trabajo *Ubicación* no evalúan múltiples acciones de directiva de ubicación cuando está seleccionada la opción **Varios SKU** . Solo se evalúa la primera acción directiva de ubicación.

### <a name="issue-resolution"></a>Solución del problema

Una nueva característica, *Evaluar todas las acciones para las directivas de ubicación de múltiples SKU*, se ha agregado en la versión 10.0.15 (ver [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Esta función evalúa todas las acciones para las directivas de ubicación de varios SKU. Si necesita esta función, utilice [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activarla.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>No puedo usar la aplicación del almacén para hacer picking parcial.

### <a name="issue-description"></a>Descripción del problema

Para las órdenes de venta y transferencia, no puede omitir artículos y realizar un picking parcial.

### <a name="issue-resolution"></a>Solución del problema

En la página **Elementos del menú del dispositivo móvil**, para cada elemento del menú que está configurado para procesar órdenes de venta o órdenes de transferencia, establezca la opción **Permitir la división del trabajo** en la ficha desplegable **General** en *Sí*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>¿Cómo puedo hacer un cambio de estado de inventario para trabajo de cantidad parcial?

### <a name="issue-description"></a>Descripción del problema

Desea realizar un cambio de estado de inventario para una cantidad parcial de un lote.

### <a name="issue-resolution"></a>Solución del problema

Para permitir que los trabajadores realicen este cambio, puede crear un elemento de menú para la aplicación del almacén. En la página **Elementos de menú del dispositivo móvil**, cree (o edite) un elemento de menú con la siguiente configuración:

- **Modo:** *Trabajo*
- **Usar trabajo existente:** *No*
- **Proceso de creación de trabajo:** *Movimiento*
- **Mostrar estado de inventario**: *Sí*

Puede configurar otros campos en la página según sus necesidades.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]