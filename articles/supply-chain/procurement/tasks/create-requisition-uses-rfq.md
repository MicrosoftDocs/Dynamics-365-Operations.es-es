--- 
title: Crear una solicitud que utilice una solicitud de presupuesto
description: "En esta guía se muestra cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Crear una solicitud que utilice una solicitud de presupuesto

[!include [task guide banner](../../includes/task-guide-banner.md)]

En esta guía se muestra cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF y debe haber iniciado sesión como administrador para completar todos los pasos. Las tareas de esta guía las realizarán normalmente profesionales de compras.


## <a name="create-a-requisition"></a>Creación de una solicitud
1. Vaya a Adquisición y abastecimiento > Solicitudes de compra > Solicitudes de compra preparadas por mí.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Fecha solicitada, especifique una fecha.
5. En el campo Fecha contable, escriba una fecha.
6. Haga clic en Aceptar
7. En el campo Motivo, especifique o seleccione un valor.
8. Haga clic en Agregar línea.
9. En el campo Categoría de compras , seleccione una categoría en el árbol y, a continuación, haga clic en Aceptar.
10. En el campo Nombre de producto, escriba un valor.
11. En el campo Cantidad, especifique un número.
12. En el campo Unidad, especifique o seleccione un valor.
13. Haga clic en Guardar.
14. Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.
15. Haga clic en Enviar.
16. Cierre la página.
17. Haga clic en Enviar.

## <a name="reassign-a-workflow-task"></a>Reasignar una tarea de flujo de trabajo
    * La siguiente tarea es crear una solicitud de presupuesto para obtener ofertas de proveedores para el producto. En los datos de demostración USMF, el flujo de trabajo de solicitud se configura para que, en el caso de que no se seleccione un proveedor, o el precio unitario sea 0 para una línea, se asigne una tarea a un trabajador específico para crear una solicitud de presupuesto. Para continuar con esta guía, necesita reasignar esa tarea a otro usuario (usted mismo). Puede hacerlo solamente si inicia sesión como administrador.  
1. Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.
2. Haga clic en Ver historial.
3. Actualice la página.
4. Expanda la sección Detalles de seguimiento.
5. En el árbol, seleccione “la línea que empieza con “Activación del flujo de trabajo de elementos””.
6. Haga clic en Ver detalles del flujo de trabajo.
7. Expanda la sección Elementos de trabajo.
8. Haga clic en Reasignar.
9. En el campo Usuario, seleccione Administrador.
10. Haga clic en Reasignar.
11. Cierre la página.
12. Cierre la página.

## <a name="create-an-rfq"></a>Crear una solicitud de presupuesto
1. Actualice la página.
2. Haga clic en Solicitud de presupuesto.
3. En el campo Entidad jurídica compradora, seleccione USMF.
    * Debe seleccionar la misma entidad jurídica que se encuentra en la línea de solicitud.  
4. En la lista, marque la fila seleccionada.
    * Si tenía varias líneas en su solicitud de compra, seleccione todas las líneas que usted quiere agregar a la solicitud de compra.  
5. Haga clic en Aceptar
6. Actualice la página.
7. Abra el cuadro informativo y, a continuación, expanda la sección Documentos relacionados.
    * Puede tener ya el cuadro informativo abierto. Busque el icono con una flecha encima, a la derecha de los botones de alternancia Línea/Encabezado. Si la flecha está señalando a la derecha, el cuadro informativo ya está abierto. Si la flecha señala a la izquierda, haga clic en ella para abrir el cuadro informativo.  
8. Haga clic en el vínculo en el campo Solicitud de presupuesto para abrir la solicitud de presupuesto que se acaba de crear.
9. Haga clic en Encabezado.
10. Haga clic en Agregar.
11. En el campo Cuenta de proveedor, especifique o seleccione un valor.
12. Haga clic en Agregar.
13. En el campo Cuenta de proveedor, especifique o seleccione un valor.
14. Haga clic en Enviar.
15. Haga clic en Aceptar
16. Haga clic en Especificar respuesta.
17. En el panel de acciones, haga clic en Contestación.
18. Haga clic en Copiar datos en respuesta.
    * Esto copia datos, como la cantidad y las fechas, de la solicitud de presupuesto a la respuesta.  
19. En el campo Precio unitario, escriba un número.
    * Este es el precio que ha recibido del proveedor. También es posible que desee especificar información adicional del proveedor.  
20. Haga clic en Aceptar.
21. Haga clic en Aceptar

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Comprobar que el proveedor y el precio se han transferido a la solicitud
1. Cierre la página.
2. Haga clic en Líneas.
3. Haga clic en Información relacionada.
4. Haga clic en Solicitud de compra.
5. Seleccione la línea que se transfirió a la solicitud de presupuesto.
    * Compruebe que el precio y el proveedor se han copiado a la solicitud.  
6. Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.
7. Haga clic en Completar.
8. Cierre la página.
9. Haga clic en Completar.


