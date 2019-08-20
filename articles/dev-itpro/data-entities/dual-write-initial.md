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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797307"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Orden de ejecución para la sincronización inicial de Finance and Operations y Common Data Service

Antes de usar la integración de datos, debe crear los datos iniciales necesarios para clientes, proveedores y los contactos. Por ejemplo, si desea crear un nuevo elemento **Grupo de proveedores** y establecer sus **Condiciones de pago** como **Net30**, antes de intentar crear el elemento **Grupo de proveedores** necesita asegurarse de que exista **Net30** en Finance and Operations y Common Data Service. (En el futuro, lanzaremos al mercado una funcionalidad de plataforma de escritura dual denominada **Sincronización inicial**. Hará una única sincronización de datos entre Finance and Operations y Common Data Service como parte de la configuración de la escritura dual).

Sugerencias: Estamos lanzando al mercado una asignación de escritura dual para todos los datos de referencia, incluidas las **Condiciones de pago**. Si ya tiene los datos iniciales en un sistema, una pequeña operación de actualización de un registro puede activar la escritura dual en dicho registro. 

Debe seguir el siguiente orden de prioridad y asegurarse de que los datos iniciales están disponibles en Finance and Operations y Common Data Service.   

## <a name="vendor"></a>Proveedor

El orden de ejecución para el proveedor es:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Cliente (Organización)

El orden de ejecución para el cliente es:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Contacto (Persona)

El orden de ejecución para el contacto es:

```
Customer
Vendor               
```
