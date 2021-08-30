---
title: Proponer adquisiciones de activos fijos
description: Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99202763ae32d02f94f1590783727d4f2cf7a7bbe45963d0e175bfc449b134d9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742938"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proponer adquisiciones de activos fijos

[!include [banner](../../includes/banner.md)]

Este tema describe cómo adquirir un activo fijo mediante la propuesta de adquisición del diario de activos fijos. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF. Para adquirir un activo fijo a través de un diario de propuestas de activos fijos, primero debe crear el registro de activos fijos y luego definir el precio de adquisición en el libro de activos.

## <a name="create-an-asset-acquisition-proposal"></a>Crear una propuesta de adquisición de activos

Complete los siguientes pasos para crear una propuesta de adquisición de activos. 

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
- Compruebe que se creen las líneas de transacción.  
- Solo los activos fijos con la fecha de adquisición y el precio de adquisición establecidos en el libro se incluirán en la propuesta de adquisición.  
11. En la página, seleccione la ficha **Libros**.
12. Seleccione **Registrar**.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Incluir dimensiones financieras predeterminadas en una propuesta de adquisición

La transacción de adquisición se puede crear utilizando complementos de Excel, yendo a **Activos fijos > Asientos de diario > Diario de activos fijos**. Cree un nuevo diario, vaya a la sección **Líneas** de la página, seleccione el icono de Excel, y luego elija una línea de diario de activos fijos. El sistema creará y abrirá una plantilla de Excel que representa las líneas del diario. Puede agregar datos para las líneas de diario que esté agregando a la plantilla y luego publicar esa información otra vez en el sistema. 

Si se han configurado dimensiones predeterminadas para el libro de activos seleccionado y los activos fijos correspondientes que se introdujeron en la plantilla de Excel, las dimensiones financieras predeterminadas se llamarán desde los datos maestros del libro de activos cuando el diario se publique desde Excel en el sistema. Para incluir dimensiones financieras en un libro de activos automáticamente mientras se publica el diario de activos fijos desde el complemento de Excel, las dimensiones predeterminadas deben configurarse de antemano.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
