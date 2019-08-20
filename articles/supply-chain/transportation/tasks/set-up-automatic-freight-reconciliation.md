---
title: Configurar la conciliación automática de flete
description: Este procedimiento muestra cómo configurar los datos para la conciliación automática de flete.
author: ShylaThompson
manager: AnnBe
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 057d1b3a1b5294c75f02f4ed443ae6f525ac6b83
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837623"
---
# <a name="set-up-automatic-freight-reconciliation"></a>Configurar la conciliación automática de flete

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar los datos para la conciliación automática de flete. Este proceso normalmente lo realiza el director del almacén. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.


## <a name="set-up-the-freight-bill-type"></a>Configurar el tipo de albarán de flete
1. Ir a Administración de transporte > Configuración > Conciliación de transporte > Tipo de albarán de transporte.
    * El tipo de albarán de flete define cómo deben conciliarse las cuentas de flete y las facturas del transportista.  
2. Haga clic en Nuevo.
3. En el campo Tipo de alabarán de flete, escriba un valor.
4. En el campo Ensamblado de motores, escriba "Microsoft.Dynamics.Ax.Tms.dll".
    * Esta es la biblioteca de códigos estándar del motor que coincide con la gestión de transporte.  
5. En el campo Tipo de motor, escriba "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer".
    * Esta es la clase del motor estándar que coincide con la gestión de transporte.  
6. Haga clic en Nuevo.
7. En el campo Descripción, elija el valor que se debe coincidir con el albarán de flete y la factura de transportista.  
8. Seleccione Sí en el campo Correspondencia requerida.
    * Si configura este campo en Sí esto significa que el valor seleccionado en el campo Descripción debe coincidir con el albarán de flete y la factura de transportista. Si configura en No, el campo puede quedar en blanco en uno de ellos.  
9. Haga clic en Guardar.

## <a name="set-up-the-freight-bill-type-assignment"></a>Configurar la asignación de tipo de albarán de flete
1. Cierre la página.
2. Ir a Administración de transporte > Configuración > Conciliación de transporte > Asignación de tipos de albarán de transporte.
    * La asignación del tipo de albarán de flete se utiliza para especificar el tipo de albarán de flete que se usa para un transportista determinado.   
3. Haga clic en Nuevo.
4. En el campo Modo, especifique o seleccione un valor.
5. En el campo Transportista de envío, especifique o seleccione un valor.
6. En el campo Tipo de albarán de flete, seleccione el tipo de albarán de flete que creó anteriormente.
7. Cierre la página.

## <a name="set-up-the-audit-master"></a>Configurar el maestro de auditoría
1. Ir a Administración de transporte > Configuración > Conciliación de transporte > Director de auditoría.
    * El maestro de auditoría define los límites de tolerancia para la conciliación automática de flete. Especifica en cuánto pueden variar los importes monetarios en el albarán de flete y la factura de transportista y que se permita la conciliación. También define cómo gestionar discrepancias.  
2. Haga clic en Nuevo.
3. En el campo Id. de maestro de auditoría, especifique un valor.
4. En el campo Transportista de envío, seleccione el mismo transportista de envío que seleccionó anteriormente.
5. En el campo Tipo de albarán de flete, seleccione el tipo de albarán de flete que creó anteriormente.
6. Expanda la sección Tolerancia.
7. Especifique un número en el campo Nivel de tolerancia mínimo.
8. Especifique un número en el campo Nivel de tolerancia máximo.
9. Expanda la sección Resultado.
10. En el campo Código de motivo de sobrepago, especifique o seleccione un valor.
    * Si los importes monetarios difieren en el albarán de flete y la factura de transportista, los códigos de motivo de sobrepago y de pago insuficiente especifican las cuentas donde debe registrarse la diferencia, siempre que la diferencia se encuentre dentro de los niveles de tolerancia.  
11. En el campo Código de motivo de pago insuficiente, especifique o seleccione un valor.
12. Cierre la página.

