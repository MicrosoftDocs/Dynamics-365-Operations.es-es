---
title: Tipos de diagnóstico para disconformidades
description: Este tema describe cómo usar y crear tipos de diagnóstico que se pueden usar con disconformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edaa3a8b5c6446f039f33589166d832dcd9d0b9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580945"
---
# <a name="diagnostic-types-for-nonconformances"></a>Tipos de diagnóstico para disconformidades

[!include [banner](../includes/banner.md)]

Este tema describe cómo usar y crear tipos de diagnóstico que se pueden usar con disconformidades.

Use la página **Tipos de diagnóstico** para definir una clasificación de acciones de diagnóstico. Luego, al crear una corrección para una no conformidad, seleccione un diagnóstico. Una corrección especifica qué tipo de acción de diagnóstico se debe realizar en una disconformidad aprobada, quién debe efectuarla. También especifica la fecha de finalización solicitada y la fecha de finalización planificada.

## <a name="examples-of-diagnostic-types"></a>Ejemplos de tipos de diagnósticos

Trabaja para una empresa de fabricación y varios artículos no han superado las pruebas de calidad. Esos artículos se mueven a un área de cuarentena y se marcan como productos no conformes. Se crea un registro de disconformidad en Microsoft Dynamics 365 Supply Chain Management para rastrear los detalles a través de la resolución de problemas.

En este caso, los problemas de calidad se deben a que los cojinetes de la máquina que empaqueta los artículos se han estropeado y se están sobrecalentando. La corrección de este problema es reemplazar las piezas de la máquina.

Cuando configura los tipos de diagnóstico, puede crear varios registros, cada uno de los cuales representa un tipo diferente de problema que podría tener la máquina. Alternativamente, puede crear un tipo de diagnóstico genérico que represente la reparación de la máquina.

## <a name="create-a-diagnostic-type"></a>Crear un tipo de diagnóstico

1. Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Tipos de diagnóstico**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Diagnóstico**: introduzca un id. o nombre único para el tipo de diagnóstico.
    - **Descripción**: escriba una descripción detallada del tipo de diagnóstico.

1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Trabajadores responsables de aprobar no conformidades](quality-responsible-workers.md)
- [Zonas de cuarentena para disconformidades](quality-quarantine-zones.md)
- [Tipos de probemas para disconformidades](quality-problem-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Operaciones para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
