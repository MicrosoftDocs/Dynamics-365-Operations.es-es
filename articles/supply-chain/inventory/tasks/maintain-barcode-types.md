---
title: Mantener tipos de códigos de barras
description: Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 052311e15aeb20b927cbed217a2bda600dad60a5
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345659"
---
# <a name="maintain-bar-code-types"></a>Mantener tipos de códigos de barras

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo configurar una nueva definición de código de barras que se puede usar como parte del informe de lista de selección. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Si está usando USMF, puede utilizar los valores del ejemplo mostrados. Estas tareas las realizará normalmente el director del almacén.

1. Vaya a **Códigos de barras**.
1. Seleccione **Nuevo**.
1. En el campo **Configuración de código de barras**, escriba un valor.
1. En el campo **Descripción**, escriba un valor.
1. En el campo **Tipo de código de barra**, seleccione una opción.
    * Si está usando USMF, puede seleccionar "Código 39".  
1. En el campo **Tamaño**, escriba un número.
1. Escriba un número en el campo **Longitud máxima**.
1. Seleccione **Guardar**.
1. Cierre la página.
1. Vaya a **Parámetros de gestión de inventario y almacenes**.
1. En el campo **Configuración de código de barras**, especifique o seleccione un valor.
    * Seleccione la configuración del código de barras que ha creado antes, pero tenga en cuenta que el formato del código de barras debe coincidir con el formato del identificador único del tipo de registro usado en el proceso. Por ejemplo, para las rutas de picking, el formato del código de barras debe coincidir con el formato de la referencia de la ruta de picking, que suele ser una secuencia numérica.  
1. Seleccione **Guardar**.
1. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]