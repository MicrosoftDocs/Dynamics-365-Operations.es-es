---
title: Solucionar problemas de picking y embalaje
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al Seleccionar y empaquetar en Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 5f606c71d24083f8458d220808c7bcae9e5e1a04979295b4a7059ace000f83d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717013"
---
# <a name="troubleshoot-picking-and-packing"></a>Solucionar problemas de picking y embalaje

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al Seleccionar y empaquetar en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Recibo el siguiente mensaje de error: "La ubicación de la dimensión no se puede dejar en blanco si se establece el número de serie de la dimensión".

### <a name="issue-description"></a>Descripción del problema

Recibirá este mensaje de error si crea una orden de transferencia para un elemento en serie utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y, luego, una vez completado el trabajo, intenta confirmar el envío.

### <a name="issue-resolution"></a>Solución del problema

El campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde". Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito. Asegúrese de que esta ubicación esté controlada por matrículas.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Recibo el siguiente mensaje de error: "Matrícula no válida".

### <a name="issue-description"></a>Descripción del problema

Recibe este mensaje de error en la aplicación móvil Warehouse Management cuando escanea la identificación de una placa de matrícula.

### <a name="issue-resolution"></a>Solución del problema

Asegúrese de que la identificación de la placa de matrícula exista en la tabla de matrículas y que los artículos y las cantidades en la matrícula estén disponibles (en otras palabras, no estén bloqueados).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Recibo el siguiente mensaje de error: "El campo 'Peso de carga'(=-%1) solo puede contener números positivos. Se ha cancelado la actualización".

### <a name="issue-description"></a>Descripción del problema

Recibirá este mensaje de error si hay trabajo abierto cuando procesa el trabajo desde las ubicaciones de embalaje a las ubicaciones de preparación, o desde las ubicaciones de preparación a las ubicaciones de muelle.

### <a name="issue-resolution"></a>Solución del problema

Para solucionar este problema, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Verificación de consistencia** y ejecute el proceso para **Comprobación de la coherencia del peso de la carga del almacén**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Recibo el siguiente mensaje de error: "La cantidad no es válida para la unidad %1".

### <a name="issue-description"></a>Descripción del problema

Recibe este mensaje de error cuando intenta realizar una *selección dividida* en varios lotes.

### <a name="issue-resolution"></a>Solución del problema

El trabajador del almacén debe utilizar el proceso de *picking corto* en la aplicación móvil Warehouse Management. Si está intentando elegir varios lotes de la misma ubicación, también puede utilizar la opción **Lleno** en la aplicación.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>No puedo mover el inventario a una ubicación que esté controlada por matrículas.

### <a name="issue-description"></a>Descripción del problema

No puede reducir las cantidades recogidas en una carga.

### <a name="issue-resolution"></a>Solución del problema

En versiones anteriores, no puede reducir las cantidades recogidas en una carga. Sin embargo, ahora puede anular la selección a una ubicación controlada por matrícula. Debe especificar tanto un valor de **Ubicación** como un valor de **Matrícula** para la línea de carga en la página **Reducir la cantidad recogida**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>¿Puedo imprimir un albarán de entrega o el contenido del embalaje por almacén?

### <a name="issue-description"></a>Descripción del problema

Quiere imprimir una nota de entrega o el contenido del embalaje por almacén o sitio en la página **Actualización de línea de plantilla de auditoría de trabajo**.

### <a name="issue-resolution"></a>Solución del problema

Cuando imprime un documento utilizando la configuración de administración de impresión, limite el alcance (sitio/almacén) a través de la administración de impresión en lugar de seleccionar **Editar la configuración de impresión** en la página **Actualización de línea de plantilla de auditoría de trabajo**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>No puedo cancelar un albarán después de que se haya registrado en un pedido de cliente.

### <a name="issue-description"></a>Descripción del problema

Cuando los procesos de recolección y envío están habilitados para WMS, no puede cancelar un albarán después de que se haya publicado desde un pedido de cliente.

### <a name="issue-resolution"></a>Solución del problema

Para corregir las notas de empaque publicadas para los artículos que están habilitados para WMS, la publicación debe ocurrir desde la carga, no desde el pedido. Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. En general, una orden de venta que se ha seleccionado y enviado a través de los procesos de gestión de almacén puede actualizarse con un albarán de la carga o envío y el documento de la orden de venta en sí. Sin embargo, si actualiza el albarán, la orden de venta desde el documento de la orden de venta, la reversión del albarán aún no se puede realizar desde la carga o la orden de venta. Por lo tanto, le recomendamos que utilice la publicación del albarán de la carga. En este caso, se habilitará la inversión que se debe hacer desde la carga.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Recibo el mensaje de error siguiente: "No se encuentra trabajo suficiente para el clúster".

### <a name="issue-description"></a>Descripción del problema

Cuando usa el proceso *Selección de grupos dirigida por el sistema*, si configura un perfil de clúster donde, por ejemplo, se pueden seleccionar 10 posiciones, el proceso funciona según lo planificado cuando hay suficiente trabajo para seleccionar 10 posiciones. Sin embargo, si solo hay ocho posiciones para elegir, recibirá este mensaje de error porque no hay suficiente trabajo para un grupo.

### <a name="issue-resolution"></a>Solución del problema

Para solucionar este problema, edite el perfil del clúster y configure la opción **Activar posiciones** como *No*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]