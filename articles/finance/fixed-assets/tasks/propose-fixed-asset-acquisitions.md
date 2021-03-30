---
title: Proponer adquisiciones de activos fijos
description: Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 426a5e42c1fc26958ab37eddd915334f8b0e19cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205037"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proponer adquisiciones de activos fijos

[!include [banner](../../includes/banner.md)]

Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF. Para adquirir un activo fijo a través de un diario de propuestas de activos fijos, primero debe crear el registro de activos fijos y luego definir el precio de adquisición en el libro de activos.

1. En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, especifique o seleccione un valor.
4. En el panel de acciones, seleccione **Líneas**.
5. Seleccione **Propuestas**.
6. Seleccione **Propuesta de adquisición**.
7. Seleccione **Filtro**. Seleccione **Restablecer** para borrar los valores anteriores.
8. Seleccione la fila **Número de activo fijo**.
9. En el campo **Criterios**, especifique o seleccione un valor. Establezca los criterios restantes para los activos fijos que desea adquirir con esta propuesta.  
10. Seleccione **Aceptar** dos veces para salir fuera del panel.
- Compruebe las líneas de transacción creadas.  
- Solo los activos fijos con la fecha de adquisición y el precio de adquisición establecidos en el libro se incluirán en la propuesta de adquisición.  
11. En la página, seleccione la ficha **Libros**.
12. Seleccione **Registrar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]