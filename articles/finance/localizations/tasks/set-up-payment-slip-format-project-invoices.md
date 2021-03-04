---
title: Configuración de un formato de resguardo de pago para facturas de proyecto
description: Las empresas suelen adjuntar resguardos de pago impresos a las facturas para ofrecer asistencia a los clientes y proporcionar una referencia de pago para su registro y liquidación.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c843f3b504d8390b26fdc94dd747a73de75df6a9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447648"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Configuración de un formato de resguardo de pago para facturas de proyecto

[!include [banner](../../includes/banner.md)]

Las empresas suelen adjuntar resguardos de pago impresos a las facturas para ofrecer asistencia a los clientes y proporcionar una referencia de pago para su registro y liquidación. El resguardo de pago se puede usar para facturas de proyecto o texto sin formato, cartas de cobro, notas de interés y extractos de cuenta, además de las facturas de ventas y facturas de servicios. Para procesar resguardos de pago, configure en primer lugar los formatos de datos adjuntos del resguardo de pago y el número de identificación de un acreedor.

Este procedimiento usa la empresa de demostración DEMF. 

Esta funcionalidad solo está disponible para entidades jurídicas cuya dirección principal se encuentra en Dinamarca.


## <a name="set-up-a-creditor-id-number"></a>Configuración de un número de id. de acreedor
1. Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.
2. Expanda o contraiga la sección Información de cuenta bancaria.
3. Haga clic en Editar.
4. En el campo Id. de acreedor FI, escriba un valor.
5. Haga clic en Guardar.
6. Cierre la página.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Configuración de un formato de resguardo de pago para facturas, notas, cartas y extractos
1. Vaya a Clientes > Configuración > Formularios > Configuración de formulario.
2. Haga clic en la ficha Factura.
3. En el campo Pago asociado adjunto en la factura de cliente, seleccione una opción.
    * Ninguno: no imprimir un resguardo de pago. Elija esta opción si el importe del pago es en una divisa distinta a la corona danesa (DKK).   FIK 751: se imprime un resguardo de pago FIK 751 si desea escribir manualmente el importe y la fecha de vencimiento en el resguardo de pago.   FIK 752: imprima un resguardo del pago FIK 752 si pretende usar un resguardo generado de forma informática con un importe y una fecha de vencimiento de pago ya impresos.  
4. Haga clic en Guardar.
5. Haga clic en la ficha Factura de servicios.
6. En el campo Pago asociado adjunto en la factura de servicios, seleccione una opción.
    * Ninguno: no imprimir un resguardo de pago. Elija esta opción si el importe del pago es en una divisa distinta a la corona danesa (DKK).   FIK 751: se imprime un resguardo de pago FIK 751 si desea escribir manualmente el importe y la fecha de vencimiento en el resguardo de pago.   FIK 752: imprima un resguardo del pago FIK 752 si pretende usar un resguardo generado de forma informática con un importe y una fecha de vencimiento de pago ya impresos.  
7. Haga clic en Guardar.
8. Haga clic en la ficha Nota de interés.
9. En el campo Pago asociado adjunto en la nota de interés, seleccione una opción.
    * Ninguno: no imprimir un resguardo de pago. Elija esta opción si el importe del pago es en una divisa distinta a la corona danesa (DKK).   FIK 751: se imprime un resguardo de pago FIK 751 si desea escribir manualmente el importe y la fecha de vencimiento en el resguardo de pago.   FIK 752: imprima un resguardo del pago FIK 752 si pretende usar un resguardo generado de forma informática con un importe y una fecha de vencimiento de pago ya impresos.  
10. Haga clic en Guardar.
11. Haga clic en la ficha Carta de cobro.
12. En el campo Pago asociado adjunto en carta de cobro, seleccione una opción.
    * Ninguno: no imprimir un resguardo de pago. Elija esta opción si el importe del pago es en una divisa distinta a la corona danesa (DKK).   FIK 751: se imprime un resguardo de pago FIK 751 si desea escribir manualmente el importe y la fecha de vencimiento en el resguardo de pago.   FIK 752: imprima un resguardo del pago FIK 752 si pretende usar un resguardo generado de forma informática con un importe y una fecha de vencimiento de pago ya impresos.  
13. Haga clic en Guardar.
14. Haga clic en la ficha Extracto de cuenta.
15. En el campo Pago asociado adjunto del extracto de cuenta, seleccione una opción.
    * Ninguno: no imprimir un resguardo de pago. Elija esta opción si el importe del pago es en una divisa distinta a la corona danesa (DKK).   FIK 751: se imprime un resguardo de pago FIK 751 si desea escribir manualmente el importe y la fecha de vencimiento en el resguardo de pago.   FIK 752: imprima un resguardo del pago FIK 752 si pretende usar un resguardo generado de forma informática con un importe y una fecha de vencimiento de pago ya impresos.  
16. Haga clic en Guardar.
17. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]