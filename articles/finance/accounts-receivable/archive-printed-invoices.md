---
title: Archivar facturas de cliente impresas con números hash
description: Este tema explica cómo habilitar el archivo para almacenar facturas de clientes impresas con números de hash.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 841e6059f5b0d70dbd1fe12a1f8910bbb31ddc86
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018987"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Archivar facturas de cliente impresas con números hash

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

En algunos países, existe un requisito legal para almacenar los números hash calculados en el sistema junto con las impresiones de algunos documentos. Los números hash se pueden utilizar para informar a las autoridades y durante las auditorías.

Este tema explica cómo configurar el archivo para almacenar facturas de clientes impresas con números de hash.

## <a name="prerequisites"></a>Requisitos previos

- En el espacio de trabajo **Administración de características**, active la característica **Archivar facturas de clientes impresas con números hash**. Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configure los formatos imprimibles de los documentos necesarios en **Administración de impresión**.

Esta funcionalidad es aplicable a los siguientes documentos.

**Clientes**
- Factura de cliente
- Nota de abono de cliente
- Factura de servicios
- Nota de abono de texto sin formato

**Gestión y contabilidad de proyectos**
- Factura de proyecto
- Nota de abono de proyecto

## <a name="configure-customer-master-data"></a>Configurar datos maestros de clientes
Complete los siguientes pasos para configurar los datos de clientes y activar la capacidad de guardar automáticamente facturas impresas como archivos adjuntos.

1. Vaya a **Clientes** > **Todos los clientes**. 
2. Seleccione un cliente y, en la ficha desplegable **Factura y entrega**, en la sección **FACTURA ELECTRÓNICA**, en el campo **Adjunto de factura electrónica**, seleccione **Sí**.

## <a name="print-invoices"></a>Imprimir facturas
Puede publicar e imprimir cualquier texto libre, factura de cliente y proyecto o nota de crédito para el cliente configurado en el procedimiento anterior.

Abra la página **Archivos adjuntos** de la factura impresa. En la ficha desplegable **Archivo adjunto**, en el grupo de campo **Detalles adicionales**, en el campo **Número de hash del documento**, busque el número hash almacenado calculado para la factura impresa.

![Número de hash de adjunto](media/attach-hash-num.jpg)

