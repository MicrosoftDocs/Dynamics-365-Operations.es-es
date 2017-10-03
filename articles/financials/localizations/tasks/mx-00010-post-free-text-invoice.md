--- 
title: "Registrar una factura de texto libre (México)"
description: "Use el formulario Factura de texto libre para crear y registrar una factura de cliente como factura electrónica mediante el método CFDI."
author: sndray
manager: AnnBe
ms.date: 05/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ab7beec496075285c50afbcb31b7b8de997132c1
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="post-a-free-text-invoice-mexico"></a>Registrar una factura de texto libre (México)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use el formulario Factura de texto libre para crear y registrar una factura de cliente como factura electrónica mediante el método CFDI. Debe haber iniciado sesión en una entidad jurídica mexicana. Esta tarea se creó con los datos de la empresa de demostración MXMF.


## <a name="post-and-issue-a-cfdi-electronic-invoice"></a>Registro y emisión de una factura electrónica CFDI
1. Vaya a Clientes > Facturas > Todas las facturas de servicios.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Descripción, escriba un valor.
7. En el campo Cuenta principal, especifique los valores deseados.
8. En el campo de grupo de impuestos, escriba un valor.
9. En el campo Grupos de impuestos de artículos, escriba un valor.
10. En el campo Precio unitario, escriba un número.
11. Expanda o contraiga la sección Detalles de línea.
12. Haga clic en la ficha Facturas electrónicas.
13. En el campo Número de propiedad, escriba un valor.
    * Debe especificar el número de registro de propiedad proporcionado por el gobierno mexicano cuando creó la factura de servicios del servicio de leasing.  
14. Haga clic en Registrar.
15. Haga clic en Aceptar
    * Tras presionar Aceptar, la factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).  
16. Cierre la página.
17. Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.
18. Haga clic en Aceptar
    * Este trabajo por lotes ejecuta la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica CFDI. La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.    Tras presionar Aceptar, se establece la conexión web para obtener la validación y la firma digital. Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualiza para su aprobación. Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto. Las casillas Enviar correo y Enviar archivo de informe: PDF deben estar activadas en los parámetros de factura electrónica. Si no, puede enviar por correo electrónico o imprimir un informe PDF basándose en la solicitud del cliente mediante el menú Consultar e informar > CFDI (facturas electrónicas).    
19. Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).
20. En la lista, marque la fila seleccionada.
21. En la lista, haga clic en el vínculo de la fila seleccionada.

