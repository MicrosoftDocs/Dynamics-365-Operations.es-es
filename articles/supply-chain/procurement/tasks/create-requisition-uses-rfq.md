---
title: Crear una solicitud que utilice una solicitud de presupuesto
description: Este artículo explica cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecde250e3517464611b68fe3c960bfbfdf06319
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846022"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Crear una solicitud que utilice una solicitud de presupuesto

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF y debe haber iniciado sesión como administrador para completar todos los pasos. Las tareas de esta guía las realizarán normalmente profesionales de compras.


## <a name="create-a-requisition"></a>Creación de una solicitud
1. En el Panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Solicitudes de compra > Solicitudes de compra preparadas por mí**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Fecha solicitada**, especifique una fecha.
5. En el campo **Fecha contable**, escriba una fecha.
6. Seleccione **Aceptar**.
7. En el campo **Motivo**, especifique o seleccione un valor.
8. Seleccione **Agregar línea**.
9. En el campo **Categoría de compras**, seleccione una categoría en el árbol y, a continuación, haga clic en **Aceptar**.
10. En el campo **Nombre de producto**, escriba un valor.
11. En el campo **Cantidad**, especifique un número.
12. En el campo **Unidad**, especifique o seleccione un valor.
13. Seleccione **Guardar**.
14. Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.
15. Seleccione **Enviar**.
16. Cierre la página.
17. Seleccione **Enviar**.

## <a name="reassign-a-workflow-task"></a>Reasignar una tarea de flujo de trabajo
La siguiente tarea es crear una solicitud de presupuesto para obtener ofertas de proveedores para el producto. En los datos de demostración USMF, el flujo de trabajo de solicitud se configura para que, en el caso de que no se seleccione un proveedor, o el precio unitario sea 0 para una línea, se asigne una tarea a un trabajador específico para crear una solicitud de presupuesto. Para continuar con esta guía, necesita reasignar esa tarea a otro usuario (usted mismo). Puede hacerlo solamente si inicia sesión como administrador.  

1. Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.
2. Seleccione **Ver el historial**.
3. Actualice la página.
4. Expanda la sección **Detalles de seguimiento**.
5. En el árbol, seleccione la línea que empieza con "Activación del flujo de trabajo de elementos".
6. Seleccione **Ver detalles del flujo de trabajo**.
7. Expanda la sección **Elementos de trabajo**.
8. Seleccione **Reasignar**.
9. En el campo **Usuario**, seleccione **Administrador**.
10. Seleccione **Reasignar**.
11. Cierre las dos páginas.

## <a name="create-an-rfq"></a>Crear una solicitud de presupuesto

1. Actualice la página.
2. Seleccione **Solicitud de presupuesto**.
3. En el campo **Entidad jurídica compradora**, seleccione **USMF**. Debe seleccionar la misma entidad jurídica que se encuentra en la línea de solicitud.  
4. En la lista, marque la fila seleccionada. Si tenía varias líneas en su solicitud de compra, seleccione todas las líneas que usted quiere agregar a la solicitud de compra.  
5. Seleccione **Aceptar**.
6. Actualice la página.
7. Asegúrese de que la ficha desplegable está abierta y, después, expanda la sección **Documentos relacionados**.
8. Seleccione el vínculo en el campo **Solicitud de presupuesto** para abrir la solicitud de presupuesto que se acaba de crear.
9. Seleccione **Encabezado**.
10. Seleccione **Agregar**.
11. En el campo **Cuenta de proveedor**, especifique o seleccione un valor.
12. Seleccione **Agregar**.
13. En el campo **Cuenta de proveedor**, especifique o seleccione un valor.
14. Seleccione **Enviar**.
15. Seleccione **Aceptar**.
16. Seleccione **Especificar respuesta**.
17. En el panel de acciones, haga clic en **Responder**.
18. Seleccione **Copiar datos a respuesta**. Esto copia datos, como la cantidad y las fechas, de la solicitud de presupuesto a la respuesta.  
19. En el campo **Precio unitario**, escriba un número. Este es el precio que ha recibido del proveedor. También es posible que desee especificar información adicional del proveedor.  
20. Seleccione **Aceptar**.
21. Seleccione **Aceptar**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Comprobar que el proveedor y el precio se han transferido a la solicitud
1. Cierre la página.
2. Seleccionar **Líneas**.
3. Seleccione **Información relacionada**.
4. Seleccionar **Solicitud de compra**.
5. Seleccione la línea que se transfirió a la solicitud de presupuesto. Compruebe que el precio y el proveedor se han copiado a la solicitud.  
6. Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.
7. Seleccione Completar.
8. Seleccionar la página.
9. Seleccione Completar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]