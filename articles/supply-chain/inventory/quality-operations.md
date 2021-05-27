---
title: Operaciones para disconformidades
description: Este tema describe cómo crear y utilizar operaciones para no conformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a6cc88b80f82d77edac0341cb6a3c0db4b42ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022213"
---
# <a name="operations-for-nonconformances"></a>Operaciones para disconformidades

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear y utilizar operaciones para no conformidades.

Use la página **Operaciones** para definir clasificaciones del trabajo que se puede efectuar para un caso de disconformidad aprobado. Al asignar una operación relacionada a una disconformidad, también puede proporcionar detalles, como el material asociado, las horas de trabajo y los gastos requeridos para llevar a cabo la operación. El sistema usa esta información para calcular el coste estimado para la operación. La información detallada y los costes estimados sirven como referencia. Las operaciones relacionadas para la calidad son diferentes de las operaciones que se pueden definir para una ruta de producción.

> [!NOTE]
> Aunque puede realizar un seguimiento de los costos, el tiempo y los elementos que se utilizan en una operación relacionada con una disconformidad, los datos que introduce son solo informativos. No se integra automáticamente con el libro mayor, el subdirectorio de inventario ni el módulo **Tiempo y asistencia**.

## <a name="examples-of-operations"></a>Ejemplos de operaciones

Usted trabaja para una empresa de fabricación. Se creó y aprobó una disconformidad para los artículos que no pasaron una prueba de calidad. Se creó una corrección para indicar que el problema estaba relacionado con un rodamiento averiado de una máquina. Se requieren varios pasos para reemplazar el rodamiento y se hace un seguimiento de la responsabilidad de cada operación. Por ejemplo, es posible que se requieran los siguientes pasos:

1. Se detiene la línea de producción y se realiza la rutina de limpieza.
1. El personal de mantenimiento reemplaza el rodamiento.
1. El personal de control de calidad inspecciona la máquina antes de volver a encenderla.

Para este ejemplo, se pueden crear las siguientes operaciones para representar el trabajo que se debe realizar:

- Detener la línea de producción.
- Limpiar la línea de producción.
- Realizar mantenimiento de la máquina.
- Inspeccionar la máquina.

## <a name="create-an-operation"></a>Crear una operación

1. Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Operaciones**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Operación**: introduzca un id. o nombre único para la operación.
    - **Descripción**: escriba una descripción detallada de la operación.
    - **Tipo**: si la operación se puede utilizar solo con disconformidades relacionadas con un tipo específico de pedido, seleccione el tipo de pedido (*Pedido de compra* o *Pedido de ventas*).

1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Crear y procesar disconformidades](tasks/create-process-non-conformance.md)
- [Trabajadores responsables de aprobar no conformidades](quality-responsible-workers.md)
- [Zonas de cuarentena para disconformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Tipos de probemas para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
