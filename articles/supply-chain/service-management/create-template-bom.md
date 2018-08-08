---
title: Crear plantilla de L. MAT manual
description: "Puede crear una plantilla de L. MAT mediante una serie de métodos."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a80cf596a3e7c7f08d493a0fb7350fad62d38c3e
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="create-a-template-bom"></a>Crear plantilla de L. MAT manual   

[!include [banner](../includes/banner.md)]


Puede crear una plantilla de L. MAT mediante cualquiera de los métodos siguientes. Para todos los métodos, los campos **Fecha inicial** y **Fecha final** son opcionales y solo para información.

## <a name="create-a-template-bom-manually"></a>Crear una plantilla de L. MAT manualmente

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Manual** .

4.  En el campo **Código de artículo**,escriba un artículo del tipo **L.MAT**.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Haga clic en **Aceptar**.

Se crea una nueva plantilla de L. MAT en blanco.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Crear una plantilla de L. MAT basada en otra plantilla de L. MAT

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Plantilla de L.MAT**.

4.  En el campo **Número de referencia**, seleccione una plantilla de L. MAT existente para copiar a la nueva plantilla de L. MAT.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Haga clic en **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la plantilla de L. MAT original.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Crear una plantilla de L. MAT basada en una L. MAT de artículo

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione **L.MAT**.

4.  En el campo **Número de referencia** , seleccione una versión de L. MAT. Se copia un artículo del tipo L. MAT en el **Número de artículo**.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Haga clic en **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **Listas de materiales**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Crear una plantilla de L. MAT basada en una L. MAT de producción

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.

2.  Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.

3.  En **Copiar líneas de L. MAT desde la referencia**, seleccione **Producción**.

4.  En el campo **Número de referencia** , seleccione una L. MAT de producción.

5.  En el campo **Nombre**, especifique un nombre para la plantilla.

6.  En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.

7.  Haga clic en **Aceptar**.

Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **L.MAT**.

## <a name="see-also"></a>Consulte también

[Plantilla de L. MAT](template-boms.md)

  



