---
title: Crear plantilla de L. MAT manual
description: Puede crear una plantilla de L. MAT mediante una serie de métodos.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f83048e5b4d7493b05351e4a711b7aa1f479f3911d67f8e030e0c9a3a8a1e178
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720237"
---
# <a name="create-a-template-bom"></a>Crear plantilla de L. MAT manual   

[!include [banner](../includes/banner.md)]


Puede crear una plantilla de L. MAT mediante cualquiera de los métodos siguientes. Para todos los métodos, los campos **Fecha inicial** y **Fecha final** son opcionales y solo para información.

## <a name="create-a-template-bom-manually"></a>Crear una plantilla de L. MAT manualmente

1.  Vaya a **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Seelccione **Nuevo** para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Manual** .

4.  En el campo **Código de artículo**,escriba un artículo del tipo **L.MAT**.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Seleccione **Aceptar**.

Se crea una nueva plantilla de L. MAT en blanco.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Crear una plantilla de L. MAT basada en otra plantilla de L. MAT

1.  Seleccione **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Seelccione **Nuevo** para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Plantilla de L.MAT**.

4.  En el campo **Número de referencia**, seleccione una plantilla de L. MAT existente para copiar a la nueva plantilla de L. MAT.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Seleccione **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la plantilla de L. MAT original.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Crear una plantilla de L. MAT basada en una L. MAT de artículo

1.  Seleccione **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Seelccione **Nuevo** para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione **L.MAT**.

4.  En el campo **Número de referencia** , seleccione una versión de L. MAT. Se copia un artículo del tipo L. MAT en el **Número de artículo**.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Seleccione **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **Listas de materiales**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Crear una plantilla de L. MAT basada en una L. MAT de producción

1.  Seleccione **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Seelccione **Nuevo** para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione **Producción**.

4.  En el campo **Número de referencia** , seleccione una L. MAT de producción.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Seleccione **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **L.MAT**.

## <a name="see-also"></a>Consulte también

[Plantilla de L. MAT](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]