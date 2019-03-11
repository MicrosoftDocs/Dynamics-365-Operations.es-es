---
title: Configurar la validación de conciliación de facturas de proveedores
description: Esta grabación usa la empresa de demostración USMF.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a26a057b524f162e4b288b88e8c30f7c5db7a45
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "346856"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Configurar la validación de conciliación de facturas de proveedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta grabación usa la empresa de demostración USMF. El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos. Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada. Si la entidad jurídica realiza un seguimiento de gastos, como el flete, usando los cargos, asegúrese de que la clave de configuración de cargos esté seleccionada.  La conciliación de facturas de proveedores es el proceso de conciliación de la factura de proveedor, el pedido de compra y la información de recepción de producto. Las diferencias entre estos documentos se denominan "discrepancias coincidentes". Las discrepancias de conciliación se comparan con las tolerancias especificadas. Si una discrepancia de conciliación supera el porcentaje o el importe de tolerancia, se mostrarán iconos de desviación de conciliación en el formulario Factura de proveedor y en el formulario Detalles de conciliación de facturas.

1. Vaya a Proveedores > Configuración > Parámetros de proveedores.
2. Haga clic en la ficha Validación de factura.
3. Active o desactive la casilla Habilitar validación de conciliación de facturas.
    * Seleccione si la aprobación es necesaria antes de que se pueda registrar una factura que contenga discrepancias en la conciliación de facturas. Si se define como Permitir con aviso, se mostrará una indicación visual cuando una discrepancia de la conciliación de la factura supera la tolerancia. Sin embargo, podrá registrar la factura. Para usar flujos de trabajo junto con la validación de conciliación de facturas, asegúrese de que el campo Registrar factura con discrepancias esté establecido en Permitir con aviso para evitar que se tenga que aprobar varias veces.  
    * En el campo Actualizar estado de encabezado de factura automáticamente, seleccione si la conciliación se realizará automáticamente durante la entrada de datos de la factura por el sistema. La configuración recomendada es Sí, a menos que le preocupe el rendimiento de la entrada de datos. Al deshabilitar las actualizaciones automáticas se puede habilitar un rendimiento del sistema más rápido porque la validación de conciliación de facturas se omitirá durante la entrada de datos. El responsable de entrada de datos deberá actualizar manualmente el estado de conciliación de la factura para ver los resultados de validación de conciliación de facturas cuando está establecido en No.  
4. Alterne la expansión de la sección Conciliación de totales de factura.
5. Active o desactive la casilla Totales de factura de conciliación para conciliar los totales de factura reales con los totales previstos.
    * Seleccione si se debe mostrar un icono si una discrepancia para la conciliación de la factura supera la tolerancia. Puede seleccionar mostrar el icono cuando una discrepancia positiva supere la tolerancia, o cuando una discrepancia positiva o negativa supere la tolerancia.  
    * Por ejemplo, la tolerancia es del 5 por ciento, y el importe total de la factura del pedido de compra es 100,00. Por tanto, se mostrará un icono de conciliación de precio si el importe total de la factura supera 105,00. Si selecciona Si es superior o inferior a la tolerancia, también se mostrará el icono si el importe de la factura es inferior a 95,00.  
6. En el campo Porcentaje de tolerancia de totales de factura, especifique un número.
7. Alterne la expansión de la sección Conciliación de precio y cantidad.
    * En el campo Directiva de conciliación de líneas, seleccione un valor que se usará como directiva predeterminada para la entidad jurídica con la que está trabajando. “No requerido” significa que no existe ninguna verificación de los precios individuales de la línea de factura en las cantidades de precio o de factura del pedido de compra con las cantidades de albarán necesarias. “Doble conciliación” significa que la verificación de las líneas de factura es necesaria pero solo el pedido de compra y los documentos de factura del proveedor están involucrados en la comprobación. La recepción de producto no se descompone en las validaciones de conciliación. “Triple conciliación” significa que el precio unitario neto de la factura se comparará con el precio unitario neto del pedido de compra y la cantidad de recepción de producto conciliada se comparará con la cantidad de la factura.  
    * Si usa una directiva de conciliación de líneas de doble conciliación o de triple conciliación, puede configurar porcentajes de tolerancia de precios para la entidad jurídica, los artículos y los proveedores en la página de tolerancia de precios de artículos. Al comparar las facturas de proveedores con la información de los pedidos de compra, se busca el porcentaje de tolerancia de precios aplicable.  
8. En el campo Directiva de conciliación de líneas, seleccione una opción.
    * Para permitir que se aplique un nivel diferente de conciliación a un artículo, proveedor, combinación de proveedor y artículo o línea de pedido de compra, seleccione un valor en el campo Permitir anulación de directiva de conciliación. La directiva de conciliación de líneas de la entidad jurídica se puede invalidar para un proveedor, artículo o combinación de proveedor y artículo concretos en la página Directiva de conciliación.  
    * Para conciliar los totales de precio de los artículos de línea en las facturas, seleccione un valor en el campo Conciliar totales de precios. Este tipo de conciliación es útil cuando el proveedor envía varias facturas para la misma línea de pedido de compra. Puede comparar la información sobre precios del importe neto de cada línea de factura y todas las líneas de factura pendientes y registradas anteriormente, con el importe neto de la línea del pedido de compra correspondiente.  
9. En el campo Conciliar totales de precios, seleccione una opción.
10. En el campo de tolerancia de totales de precio de compra, especifique un número.
11. Alterne la expansión de la sección Conciliación de gastos varios.
12. Para que los cargos reales coincidan con los previstos, según la información del pedido de compra, active la casilla Conciliar gastos varios.
13. Cierre la página.

