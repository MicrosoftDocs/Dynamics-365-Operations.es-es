---
title: Relaciones de objetos de servicio
description: Es posible crear relaciones de objeto de servicio entre un objeto de servicio y un acuerdo o pedido de servicio.
author: kamaybac
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eb5b185ca2ef5903eb1739edfdd7b60749babd4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576361"
---
# <a name="service-object-relations"></a>Relaciones de objetos de servicio 

[!include [banner](../includes/banner.md)]

Es posible crear relaciones de objeto de servicio entre un objeto de servicio y un acuerdo o pedido de servicio. Al crear una relación, se vincula un objeto de servicio al acuerdo o pedido de servicio.

Una vez creada la relación, puede vincular el objeto de servicio a cualquier línea del acuerdo o pedido de servicio.

## <a name="template-boms"></a>Plantilla de L. MAT

También se puede especificar una plantilla de L. MAT para la relación de objetos. Ésta es una lista de materiales para el objeto en el que se realiza el servicio. Si sustituye una pieza de componente del objeto de servicio durante una visita de servicio, puede registrar este cambio en la lista de materiales de servicio mediante el formulario Objetos de servicio.

## <a name="example"></a>Ejemplo

Puede crear un acuerdo de servicio para la reparación o el mantenimiento de dos ascensores en las instalaciones de un cliente.
El acuerdo de servicio tiene el identificador ID SAL-001.

Los ascensores se han configurado en el formulario Objetos de servicio como los objetos EL-S/1000 y EL-L/1000.

Puede vincular los objetos de servicio (EL-S/1000 y EL-L/1000) al acuerdo de servicio.

Dado que desea registrar los cambios en la lista de materiales para el objeto de servicio a medida que sustituye las piezas de componente del objeto, deberá vincular una lista de materiales de servicio a la relación de objeto de servicio, tal como se describe en la tabla siguiente.

| Objeto de servicio | Relación - Acuerdo de servicio | L. MAT de servicio   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | L. MAT-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | L. MAT-EL-L/1000 |

Dado que existen relaciones de objeto de servicio para el acuerdo, ahora puede crear líneas de acuerdo de servicio con estos objetos, tal como se muestra en la tabla siguiente.

| Tipo de transacción | Categoría           | Objeto de servicio |
|------------------|--------------------|----------------|
| Hora             | Inspección         | EL-S/1000      |
| Hora             | Limpieza de la caja de cambios  | EL-S/1000      |
| Artículo             | Material de limpieza | EL-S/1000      |
| Hora             | Inspección         | EL-L/1000      |
| Hora             | Limpieza de la caja de cambios   | EL-L/1000      |
| Artículo             | Material de limpieza | EL-L/1000      |

Durante una visita de servicio, deberá sustituir la caja de cambios del ascensor EL-S/1000. Para sustituir una pieza de componente del objeto, puede obtener acceso al Diseñador de L. MAT si usa la relación de objeto de servicio configurada para el acuerdo de servicio actual.

Acceso al Diseñador de L. MAT mediante una relación de objeto de servicio

1. Contratos de servicio
2. Haga doble clic en un contrato de servicio, o haga clic en Contrato de servicio para crear un nuevo acuerdo de servicio.
3. Haga clic en la pestaña Configurar.
4. Hga clic en Objetos de servicio para adjuntar una L. MAT de plantilla al contrato de servicio.
5. En el formulario Objetos de servicio, haga clic en Diseñador para abrir el formulario Diseñador para modificar la L. MAT. de plantilla.

## <a name="automatically-created-service-orders"></a>Pedidos de servicio creados automáticamente

Si crea pedidos de servicio automáticamente para un acuerdo de servicio, las relaciones de objeto de servicio del acuerdo también se crean en los pedidos de servicio.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]