---
title: Directivas fiscales para Europa
description: Puede especificar incluir una explicación de códigos de impuestos en las facturas de ventas y facturas de proyecto. Puede imprimir los números de referencia en facturas de venta, facturas de servicios y facturas de proyecto.
author: epodkolz
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Latvia, Lithuania, Netherlands, Norway, Poland, Spain, Sweden, Switzerland, Turkey, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2f0da36e2be20d5ae8c838ed73c6e8aa1c19b621
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407820"
---
# <a name="tax-directives-for-europe"></a>Directivas fiscales para Europa

[!include [banner](../includes/banner.md)]

La directiva de la UE proporciona la normativa que seguirán todos los estados miembros en relación con las reglas y a la información de la factura que se van a incluir al crear facturas. La directiva de la UE incluye la información requerida por los proveedores para los clientes en la UE. Por ejemplo, una factura podría incluir una referencia que describe los argumentos legales para una categoría de IVA cero o una exención. Si una factura ajusta una factura emitida anterior, como una nota de abono, se debe realizar una referencia clara a la factura original.

- Para imprimir una descripción de códigos de impuestos en una factura de ventas, la factura de servicios o el informe de la factura del proyecto, configure el texto de referencia a la directiva fiscal en los códigos de impuestos.
- Para las notas de crédito, el número y la fecha de la factura original se imprimen junto con el motivo de la corrección.

> [!NOTE]
> Verifique que el campo **Especificación de impuestos de venta** esté establecido en **Divisa de registro** o **Divisa de registro y empresa** en la página **Configuración de formulario** de la pestaña **General** (**Clientes > Configuración > Formularios > Configuración de formulario** o **Gestión y contabilidad de proyectos > Configuración > Formularios > Configuración de formularios**).
