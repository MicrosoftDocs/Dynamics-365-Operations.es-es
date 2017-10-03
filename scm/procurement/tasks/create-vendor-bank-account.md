--- 
title: Crear una cuenta bancaria de proveedor
description: "Este procedimiento le muestra cómo crear una cuenta bancaria para un proveedor."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e84432faf32e519059a21d2b56e320a46599c1e8
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-vendor-bank-account"></a>Crear una cuenta bancaria de proveedor

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear una cuenta bancaria para un proveedor. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.

1. Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.
2. Seleccione el proveedor para el que desea crear una cuenta bancaria y, a continuación, haga clic en el vínculo del id. de la cuenta de proveedor.
3. En el panel de acciones, haga clic en Proveedor.
4. Haga clic en Cuentas bancarias.
5. Haga clic en Nuevo.
6. En el campo Cuenta bancaria, escriba un valor.
    * Este id. se utilizará para identificar la cuenta bancaria en el registro del proveedor.  
7. En el campo Nombre, escriba un valor.
8. En el campo Grupos de bancos, especifique o seleccione un valor.
9. En el campo Tipo de número de ruta, seleccione una opción.
    * Este es el tipo de número de ruta que se utiliza para los pagos internacionales.  
10. En el campo Número de cuenta bancaria, escriba un valor.
11. En el campo Código SWIFT, escriba un valor.
12. Escriba un valor en el campo IBAN.
    * El número IBAN debe estar en el formato correcto. Por ejemplo, podría utilizar DE89370400440532013000.  
    * El estado de la cuenta bancaria es Activo si se ha alcanzado la fecha activa y no se ha superado la Fecha de vencimiento. También está activo si los campos Fecha de activación y Fecha de vencimiento están en blanco. Si las fechas tanto del campo Fecha de activación como del campo Fecha de vencimiento son posteriores, los pagos electrónicos no estarán disponibles. Otros tipos de pago estarán disponibles y la cuenta bancaria estará activa.  
13. Expanda la sección Configuración.
14. En el campo Código de texto, escriba un valor.
    * Este campo especifica un código que aparecerá en el extracto de cuenta del destinatario.  
15. En el campo Mensaje para el banco, escriba un valor.
16. En el campo Referencia de cambio, escriba un valor.
    * Este es el número de referencia para cualquier tipo de cambio futuro o a plazo fijo.  
17. En el campo Divisa, especifique o seleccione un valor.
    * Cuando se publican las validaciones de cuentas, esta sección proporciona una visión general de su estado (pendiente o aprobado).  
18. Expanda la sección Dirección.
19. Expanda la sección Validaciones de cuentas.
20. Expanda la sección Información de contacto.
21. En el campo Teléfono, escriba un valor.
22. Cierre la página.
23. Haga clic en Editar.
24. Expanda la sección Pago.
25. En el campo Cuenta bancaria, seleccione la cuenta que acaba de crear.
26. Haga clic en Guardar.
    * La dirección se puede heredar del grupo bancario, si se especifica uno, o se puede agregar aquí.  


