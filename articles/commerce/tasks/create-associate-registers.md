---
title: Crear y asociar registros
description: Este procedimiento muestra cómo crear un registro de punto de venta (PDV).
author: rubencdelgado
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff6fb42cd0b080ff576aa3a784cfce985d69fe0347af44dfa9935b4e8e5ffe00
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743368"
---
# <a name="create-and-associate-registers"></a>Crear y asociar registros

[!include [banner](../includes/banner.md)]

Este procedimiento muestra cómo crear un registro de punto de venta (PDV). Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Retail y Commerce > Configuración de canal > Configuración de PDV > PDV > Cajas registradoras.
2. Haga clic en Nuevo.
3. En el campo Número de registro, escriba un id. para el nuevo registro.
    * El id. de registro incluye normalmente códigos que ayudan a asignar el registro a la tienda a la que pertenece y a la ubicación dentro del almacén.  
4. En el campo Nombre, escriba un nombre descriptivo para el registro.
5. En el campo Número de tienda, especifique o seleccione un valor.
6. En el campo Perfil de hardware, especifique o seleccione un valor.
    * Los perfiles de hardware se utilizan para especificar los periféricos que se conectarán con el registro, como la caja registradora y la impresora de recibos.  
7. En el campo Perfil visual, especifique o seleccione un valor.
    * Los perfiles visuales se utilizan para especificar las imágenes usadas en el fondo del PDV y la página de inicio de sesión así como los temas para el PDV.  
8. En el campo Número de caja registradora de PDV de EFT, escriba un valor.
    * El número de registro de PDV de EFT se utiliza para informar al procesador de pagos de qué terminal de pago está enviando solicitudes de autorización. Este valor a menudo se denomina "Id. de terminal" o "TID". El TID se puede encontrar generalmente en una etiqueta adhesiva del dispositivo de pago.  
9. Haga clic en Guardar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]