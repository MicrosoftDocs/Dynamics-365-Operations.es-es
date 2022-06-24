---
title: Límite de umbral y límite de umbral de excepción
description: Este artículo describe los límites de umbral y de excepción para los impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: aceebad08b5454b64059e7ef374b9634bad35c37
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877947"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Límite de umbral y límite de umbral de excepción

[!include [banner](../includes/banner.md)]

Este artículo describe los límites de umbral y de excepción para los impuestos deducidos en el origen (TDS). El TDS en facturas y pagos siempre se calcula teniendo en cuenta el límite de umbral y el límite de umbral de excepción definidos para los componentes de impuestos de TDS en la página **Componentes de retención de impuestos**. Los componentes de impuestos de TDS se adjuntan a los códigos de impuestos de TDS, que se incluyen en los grupos de impuestos de TDS. Los grupos de impuestos de TDS se adjuntan a proveedores y clientes para calcular los TDS a nivel de factura o de pago.

El TDS se calcula si el importe de una transacción o las transacciones acumuladas registradas con un grupo de TDS específico para un proveedor excede el límite de umbral especificado en la página **Componentes de retención de impuestos**. El TDS no se calculará hasta que el importe acumulado de la transacción exceda el límite de umbral especificado.

Si se especifica un límite de umbral de excepción junto con el límite de umbral para un componente de TDS, el TDS se calcula cuando un importe de transacción específico excede el límite de umbral de excepción incluso si el importe de transacción acumulativo no excede el límite de umbral especificado.

### <a name="example"></a>Ejemplo
Se configura un componente de impuestos llamado TDS y se adjunta al grupo de impuestos TDS denominado Contratista. El umbral se ha definido como 50 000 y el umbral de excepción se ha definido como 20 000 para el componente de impuestos TDS. El contratista del grupo de TDS se define como el grupo de TDS predeterminado para el proveedor 1.

Se registra una factura de compra 001 para el proveedor 1 de 10 000. El TDS no se calcula para la factura porque el importe de la factura no ha cruzado el límite de umbral o el límite de umbral de excepción. Se registra una factura de compra 002 para el proveedor 1 de 25 000. El TDS se calcula para la factura porque el importe de la factura ha cruzado el límite de umbral de excepción. Se registra una factura de compra 003 para el proveedor 1 de 20 000. El TDS se calcula para la factura porque el importe total de la factura de las tres facturas emitidas para el proveedor ha cruzado el límite de umbral. El TDS se calcula en todas las facturas emitidas para el proveedor en el que no se ha calculado anteriormente el TDS. Por lo tanto, el TDS se calcula sobre 30 000, que es el importe total de la factura 001 y 003.

El límite de umbral y el límite de umbral de excepción no se tienen en cuenta para el cálculo de TDS si la casilla **Omitir el umbral** se ha seleccionado para códigos de impuestos de TDS en el grupo de TDS adjunto a la transacción. El límite de umbral no se utilizará en los códigos de impuestos de TDS en el grupo de TDS en el que se haya marcado la casilla **Omitir el umbral**.

Se la casilla **Omitir el umbral** se ha seleccionado para un grupo de TDS específico para algunas facturas, pero no está seleccionada para otras facturas que se crearon para un proveedor/cliente específico, podría tener lugar el cálculo de TDS sin omitir el límite del umbral para algunas facturas teniendo en cuenta el importe acumulativo de todas las facturas en las que el TDS no se ha calculado con anterioridad.

Por ejemplo, el límite de umbral es 25 000. Se crean las siguientes facturas para el proveedor A.

- Factura 1 – 20 000 – (No se ha seleccionado la casilla **Omitir el umbral**): no se calcula el TDS.

- Factura 2 – 4000 – (Se ha seleccionado la casilla **Omitir el umbral**): se calcula el TDS sobre 4000.

- Factura 2 – 3000 – (No se ha seleccionado la casilla **Omitir el umbral**): el TDS se calcula porque el importe acumulado de la factura, es decir, 27 000 (20 000 + 4000 + 3000) excedió el límite del umbral. El TDS se calcula sobre el importe acumulado de facturas en las que el TDS no se ha calculado anteriormente, es decir, 23 000 (20 000 + 3000).
