---
title: Grupos de crédito del cliente
description: Este artículo proporciona información sobre los grupos de crédito de cliente.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 032e92431946f0a41bf2e52c155e422d4ea0b3b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886527"
---
# <a name="customer-credit-groups"></a>Grupos de crédito del cliente

[!include [banner](../includes/banner.md)]

Puede definir grupos de clientes que tienen un límite de crédito compartido. También se considera el límite de crédito individual que se define en la cuenta de la factura del cliente.

Los miembros de un grupo de crédito de cliente pueden seleccionarse de diferentes entidades jurídicas. Cuando agrega un cliente a la lista de clientes en el grupo de crédito de cliente, la fecha de vencimiento del límite de crédito para cada cliente cambia a la fecha de vencimiento que se asigna al grupo.

Puede configurar grupos de crédito de cliente en la página **Grupos de crédito de cliente** (**Administración de crédito \> Grupos de crédito de cliente \> Grupos de crédito de cliente**).

1. En los campos **Número de grupo** y **Descripción**, introduzca un identificador y una descripción para el grupo.
2. En los campos **Límite de crédito** y **Divisa**, introduzca el límite de crédito y la divida que se deben usar cuando el sistema comprueba el límite de crédito de cualquier miembro del grupo.
3. En el campo **Límite de crédito hasta la fecha**, introduzca la fecha en la que vence el límite de crédito. Los grupos de crédito de cliente deben tener una fecha de vencimiento.

Una vez que haya terminado de configurar un grupo de crédito de cliente, puede agregar clientes especificado su entidad jurídica y su id. de cuenta de cliente. Al agregar un nuevo cliente a un grupo de crédito de cliente, el sistema busca la misma cuenta de cliente en todas las entidades jurídicas y le solicita que la agregue al grupo de crédito de cliente.

Use el menú **Saldos vencidos** para ver los detalles de saldo vencido de todos los clientes de factura en un grupo de crédito de cliente. La página **Saldo vencido** muestra un resumen de los saldos vencidos de las cuentas de cliente de factura.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
