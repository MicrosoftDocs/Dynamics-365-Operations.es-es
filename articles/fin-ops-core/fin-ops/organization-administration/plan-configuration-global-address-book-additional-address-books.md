---
title: Plan para la libreta de direcciones global y otras libretas de direcciones
description: Este tema describe las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar y configurar la libreta de direcciones global y todas las libretas de direcciones adicionales.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d83d6536d85100ef6a91e909be5a8e57e423371
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693939"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Plan para la libreta de direcciones global y otras libretas de direcciones

[!include [banner](../includes/banner.md)]

Este tema describe las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar y configurar la libreta de direcciones global y todas las libretas de direcciones adicionales. Algunas de las decisiones requerirán que confirme las decisiones que se han realizado para otras áreas de producto, como la jerarquía organizativa.

## <a name="global-address-book"></a>Libreta de direcciones global

Antes de comenzar a trabajar con la libreta de direcciones global, debe determinar los valores predeterminados para ella. Estos valores predeterminados se usan para todas las libretas de direcciones adicionales que cree.

**Decisiones**

- ¿En qué secuencia se deben mostrar los nombres para los registros de parte del tipo **Persona**? Por ejemplo, una secuencia es apellido, segundo nombre, nombre.
- ¿Se deben eliminar los registros de parte de la libreta de direcciones cuando se elimina el rol de registro? Por ejemplo, si se elimina un registro de cliente, ¿se debe eliminar también el registro de parte?
- Cuándo se crea un registro nuevo, ¿se deben notificar los usuarios se si encuentra un registro duplicado en la libreta de direcciones global?
- ¿Debe incluirse el número del Sistema de numeración universal de datos (DUNS) en la información del registro de parte?
- Si el número DUNS se incluye en un registro de parte, ¿debe comprobarse la unicidad del número?
- Cuándo se crea un registro de parte en la libreta de direcciones global, ¿desea un tipo de parte, una persona o una organización predeterminados?
- ¿Qué roles de usuario deben tener acceso a las direcciones privadas y a la información de los registros de partes?

## <a name="additional-address-books"></a>Libretas de direcciones adicionales

Después de crear la libreta de direcciones global, puede crear libretas de direcciones adicionales como sea necesario, como una libreta de direcciones independiente para cada empresa de su organización o para cada línea de negocio. Por ejemplo, Fabrikam es una organización internacional con varias empresas y líneas de negocios. Fabrikam planea crear una libreta de direcciones para cada línea de negocios. En el caso de las líneas de negocios que están presentes en más de una ubicación —por ejemplo, la empresa de herramientas neumáticas—, Fabrikam planea crear una libreta de direcciones para cada ubicación. Chris, el encargado de TI en Fabrikam, ha creado la lista siguiente de las libretas de direcciones que se requieren. Esta lista también describe los registros de parte que cada libreta de direcciones debe incluir.

- **Contratos del sector público (PubSC)**: registros de parte de todas las partes involucradas en los contratos del sector público que Fabrikam mantiene.
- **Contratos del sector privado (PriSC)**: registros de parte de todas las partes involucradas en los contratos del sector privado que Fabrikam mantiene.
- **Herramientas electrónicas (ET)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas electrónicas o que, de lo contrario, tienen relación con las herramientas electrónicas que proporciona o adquiere Fabrikam en la empresa Fabrikam-Japón.
- **Herramientas neumáticas (PTJPN)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas neumáticas o que, de lo contrario, tienen relación con las herramientas neumáticas que proporciona o adquiere Fabrikam en la empresa Fabrikam-Japón.
- **Herramientas neumáticas (PTUSA)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas neumáticas o que, de lo contrario, tienen relación con las herramientas neumáticas que proporciona o adquiere Fabrikam en la empresa Fabrikam-US.

**Decisión:**

- ¿Cuántas libretas de direcciones adicionales creará?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]