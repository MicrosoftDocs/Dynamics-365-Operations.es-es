--- 
title: Almacenar configuraciones para los extractos de Retail
description: Este procedimiento muestra las configuraciones para la Tienda que afectan la manera en que se crean y se registran los extractos comerciales.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 2f73bca3bd1699ee1c2e98706a4d69f8b0b25052
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="store-configurations-for-retail-statements"></a>Almacenar configuraciones para los extractos de Retail

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento muestra las configuraciones para la Tienda que afectan la manera en que se crean y se registran los extractos comerciales. Las dimensiones financieras en tiendas se cubren en otro procedimiento. Este procedimiento usa la empresa de prueba USRT.

1. Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * La configuración de la sección Extracto o cierre afecta a la creación, la validación y al registro de extractos para el almacén.  Abra la sección Extracto o cierre.  
    * Seleccione el método que desea usar para agrupar las líneas de extracto.  
    * Seleccione "Sí" si solo se debería crear un extracto al día al crear extractos del trabajo por lotes de la creación de extractos.  
    * El campo Cálculo de declaración por forma de pago define si las declaraciones por forma de pago se deben agregar juntas o si se debe usar la última.  
    * Seleccione la cuenta contable en la que registrar diferencias de redondeo.  
    * En el campo de diferencias de redondeo máxima, puede especificar la diferencia de redondeo máxima permitida.  
    * En el campo Registro, puede especificar la diferencia de registro total máxima permitida para un extracto.  
    * En el campo Turno, puede especificar la diferencia total máxima dentro de un turno en un extracto.  
    * En el campo Transacción, puede especificar la diferencia total máxima en una línea de extracto.  
    * En el campo Método de cierre, puede definir si las transacciones que se incluirán en un extracto deben parte de un turno cerrado o si puede haber algunas transacciones dentro del intervalo definido de fecha o hora.  
    * En el campo Final del día laboral, puede especificar una hora si las transacciones que se producen después de medianoche se deben registrar con el día anterior.  
    * Seleccione "Sí" si las transacciones que se producen después de medianoche se deben registrar como parte del día anterior.  
    * Seleccione "Sí" para que se creen extractos para cada método de extracto definido. Esto puede resultar útil si el rendimiento del registro se debe mejorar para almacenes con volúmenes altos de transacción puesto que creará muchos extractos más pequeños que se pueden procesar en paralelo.  
    * En el campo Cliente predeterminado, puede seleccionar la cuenta de cliente que se usará para ventas a los clientes que entran.  


