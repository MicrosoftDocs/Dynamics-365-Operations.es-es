---
title: Orden de ejecución para la sincronización inicial de Finance and Operations y Common Data Service
description: Este tema especifica el orden de sincronización que debe seguir para crear datos de inicio.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873137"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a>Orden de ejecución para la sincronización inicial de Finance and Operations y Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Antes de usar la integración de datos, debe crear los datos iniciales necesarios para clientes, proveedores y los contactos. Por ejemplo, va a crear un nuevo elemento **Grupo de proveedores** y establece su valor **Condiciones de pago** en **Net30**. En este caso, antes de que se intente crear el elemento **Grupo de proveedores**, debe asegurarse de que exista **Net30** tanto en Microsoft Dynamics 365 for Finance and Operations como en Common Data Service. (En el futuro, Microsoft lanzará al mercado una funcionalidad de plataforma de escritura dual denominada Sincronización inicial. Hará una única sincronización de datos entre Finance and Operations y Common Data Service como parte de la configuración de la escritura dual).

> [!TIP]
> Microsoft va a lanzar al mercado una asignación de escritura dual para todos los datos de referencia, incluidas las **Condiciones de pago** (condiciones de pago). Si ya tiene los datos iniciales en un sistema, una pequeña operación de actualización de un registro puede activar la escritura dual en dicho registro.

Debe seguir el siguiente orden de prioridad y asegurarse de que los datos iniciales están disponibles en Finance and Operations y Common Data Service.

## <a name="vendor"></a>Proveedor

A continuación se indica el orden de la ejecución para la entidad **Proveedor**:

1. Grupo de proveedores

    1. Condiciones de pago

        1. Días de pago y líneas
        2. Multivencimientos

2. Método de pago de proveedor

## <a name="customer-organization"></a>Cliente (Organización)

A continuación se indica el orden de la ejecución para la entidad **Cliente**:

1. Grupo de clientes

    1. Condiciones de pago

        1. Días de pago y líneas
        2. Pago 

2. Método de pago de cliente

## <a name="contact-person"></a>Contacto (Persona)

A continuación se indica el orden de la ejecución para la entidad **Contacto**:

1. Cliente 
2. Proveedor
