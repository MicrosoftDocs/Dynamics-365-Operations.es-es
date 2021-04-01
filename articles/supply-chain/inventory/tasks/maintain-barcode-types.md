---
title: Mantener tipos de códigos de barras
description: Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 112438417e425b8b77dd56f25e0b6e6db21c5148
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244408"
---
# <a name="maintain-barcode-types"></a>Mantener tipos de códigos de barras

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Si está usando USMF, puede utilizar los valores del ejemplo mostrados. Estas tareas las realizará normalmente el director del almacén.

1. Vaya a Códigos de barras.
2. Haga clic en Nuevo.
3. En el campo Configuración de código de barras, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo de código de barra, seleccione una opción.
    * Si está usando USMF, puede seleccionar "Código 39".  
6. En el campo Tamaño, escriba un número.
7. Escriba un número en el campo Longitud máxima.
8. Haga clic en Guardar.
9. Cierre la página.
10. Vaya a Parámetros de gestión de inventario y almacenes.
11. En el campo Configuración de código de barras, especifique o seleccione un valor.
    * Seleccione la configuración del código de barras que ha creado antes, pero tenga en cuenta que el formato del código de barras debe coincidir con el formato del identificador único del tipo de registro usado en el proceso. Por ejemplo, para las rutas de picking, el formato del código de barras debe coincidir con el formato de la referencia de la ruta de picking, que suele ser una secuencia numérica.  
12. Haga clic en Guardar.
13. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]