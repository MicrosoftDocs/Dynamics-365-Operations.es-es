---
title: Cargos para operaciones de disconformidad
description: Este tema describe cómo crear cargos por calidad que se pueden usar con operaciones para una disconformidad.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3306f3f9215ab03f408b8026f335dcf496515a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580969"
---
# <a name="charges-for-nonconformance-operations"></a>Cargos para operaciones de disconformidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear cargos por calidad que se pueden usar con operaciones para una disconformidad.

Use la página **Gastos de calidad** para definir los tipos de cargos que pueden agregarse a operaciones para una disconformidad. Los cargos le permiten realizar un seguimiento de los detalles sobre las tarifas o los cargos que debe a un cliente por productos en disconfomidad, o que un proveedor le debe por productos en disconformidad que recibió. También puede utilizar cargos para realizar un seguimiento de los costes que son necesarios para que los proveedores o servicios externos realicen una operación.

## <a name="examples-of-quality-charges"></a>Ejemplos de cargos de calidad

Usted trabaja para una empresa de fabricación. Su empresa tiene contratos con varios proveedores. Esos contratos describen los estándares para el envío a tiempo, los daños y la calidad del producto para los artículos. Asimismo, varios de sus clientes tienen acuerdos con su empresa sobre devoluciones, daños y calidad del producto.

Se define una estructura de precios para cada circunstancia y se especifica en el contrato. Puede configurar cargos de calidad para describir los distintos tipos de cargos, como *Daños*, *Envío tardío*, y *Calidad*. Luego, cuando crea una disconformidad, agregue una o más operaciones. Para cada operación, seleccione **Cargos** para definir los detalles sobre los precios.

## <a name="create-a-quality-charge"></a>Crear un cargo de calidad

1. Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Cargos de calidad**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Código de cargos**: introduzca un id. o nombre único para el cargo de calidad.
    - **Descripción**: escriba una descripción detallada del cargo de calidad.

1. Cierre la página.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Agregar un cargo de calidad a una operación para una disconformidad

Para obtener detalles sobre cómo agregar operaciones a una disconformidad y aplicarles cargos, consulte [Operaciones para disconformidades](quality-operations.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Trabajadores responsables de aprobar no conformidades](quality-responsible-workers.md)
- [Zonas de cuarentena para disconformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Operaciones para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
