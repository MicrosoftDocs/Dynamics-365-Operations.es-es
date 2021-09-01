---
title: Zonas de cuarentena para disconformidades
description: Este tema describe cómo crear y utilizar zonas de cuarentena para disconformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c770da899f07597896d0d392b5192ddc4162bec6271d0e11c34797d7a15f857e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754044"
---
# <a name="quarantine-zones-for-nonconformances"></a>Zonas de cuarentena para disconformidades

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear y utilizar zonas de cuarentena para disconformidades.

Use la página **Zonas de cuarentena** para definir zonas que pueden asignarse a disconformidades. Cuando crea una disconformidad, puede establecer los campos **Zona de cuarentena** y **Tipo de cuarentena** en la pestaña **General** de la página **Disconformidades**. El campo **Zona de cuarentena** normalmente indica el área o ubicación donde se encuentra el artículo. El campo **Tipo de cuarentena** define el elemento como *Uso restringido* o *Inutilizable*.

Cuando imprime un informe de disconformidad o correcciones para una no conformidad, puede ver la zona de cuarentena donde se encuentra el artículo.

También puede imprimir una etiqueta de disconformidad para una disconformidad. Este informe muestra la zona de cuarentena asignada e información de uso para ofrecer orientación sobre como debe manejarse el material defectuoso. Las zonas de cuarentena pueden corresponder a ubicaciones de inventario o a recursos de operaciones.

## <a name="examples-of-quarantine-zones"></a>Ejemplos de zonas de cuarentena

### <a name="example-1"></a>Ejemplo 1

Trabaja en una empresa de fabricación de productos electrónicos que produce y distribuye televisores, altavoces y reproductores multimedia. En este caso, puede configurar una zona de cuarentena para representar cada tipo de producto.

### <a name="example-2"></a>Ejemplo 2

Se utilizan tres contenedores y dos estantes para almacenar artículos que no son conformes. En este caso, puede configurar cinco zonas de cuarentena, una para cada contenedor y cada bastidor.

## <a name="create-a-quarantine-zone"></a>Crear una zona de cuarentena

1. Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Zonas de cuarentena**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Zona de cuarentena**: introduzca un id. o nombre único para la zona de cuarentena.
    - **Descripción**: escriba una descripción detallada de la zona de cuarentena.

1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Trabajadores responsables de aprobar no conformidades](quality-responsible-workers.md)
- [Tipos de probemas para disconformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Operaciones para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
