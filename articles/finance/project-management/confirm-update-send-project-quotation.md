---
title: Confirmar, actualizar y enviar un presupuesto de proyecto
description: Este tema proporciona información sobre cómo enviar un presupuesto al cliente para su confirmación, modificarlo en función de los comentarios y luego volver a enviar el presupuesto.
author: kfend
manager: AnnBe
ms.date: 05/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 7c2f7435ed63702dafb52b0eff57c0f174ff829e
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410264"
---
# <a name="confirm-update-and-send-a-project-quotation"></a>Confirmar, actualizar y enviar un presupuesto de proyecto

[!include [banner](../includes/banner.md)]

Después de crear y enviar un presupuesto de proyecto a un cliente, debe obtener la confirmación del cliente antes de actualizar el estado del presupuesto a **Enviado**. Cualquier modificación solicitada por el cliente puede actualizarse en el presupuesto. Después de actualizar el estado del presupuesto **Enviado**, no puede modificarlo. El siguiente procedimiento describe las opciones para enviar un presupuesto para confirmación, realizar actualizaciones basadas en comentarios y luego enviar el presupuesto.

## <a name="send-a-project-quotation-confirmation"></a>Enviar una confirmación de presupuesto de proyecto  

Puede enviar un presupuesto de proyecto existente para confirmación por correo electrónico o como una copia impresa. 

1. Vaya a **Gestión de proyectos y contabilidad** > **Presupuestos** > **Presupuestos de proyecto.** 
2. En la página **Presupuesto del proyecto**, seleccione el presupuesto que desea enviar para su confirmación. 
3. En la pestaña **Seguimiento** del grupo **Generar**, seleccione **Confirmar**. 
4. En la página **Confirmar presupuesto**, establezca los parámetros requeridos. Por ejemplo, para imprimir la confirmación, en las opciones de **Impresión**, active **Confirmación de impresión** y luego seleccione **Aceptar**.
5. En la página **Enviar presupuesto**, seleccione **Opciones** y, en la página **Configuración de destino de impresión**, seleccione si desea enviar el presupuesto a **Pantalla**, **Correo electrónico**, **Archivo**, **Imprimir archivo** o **Impresora** y luego realice los ajustes que desee en el área **Especificación** para encaminar el presupuesto.
6. En la página **Configuración de destino de impresión** , seleccione **Aceptar**.  

## <a name="update-a-project-quotation"></a>Actualizar un presupuesto de proyecto

Para modificar un presupuesto de proyecto existente, el estado del presupuesto debe ser **Creado**. Complete los siguientes pasos para actualizar un presupuesto existente. 

1. Vaya a **Gestión de proyectos y contabilidad** > **Presupuestos** > **Presupuestos de proyecto**.
2. En la página **Presupuestos de proyecto**, seleccione el presupuesto que desea actualizar y, en el panel Acciones, seleccione **Editar**.
3. Actualice la información de campos necesaria y, en el panel Acciones, seleccione **Guardar**.  

## <a name="send-a-project-quotation-to-a-customer"></a>Enviar un presupuesto de proyecto al cliente 

1. Vaya a **Gestión de proyectos y contabilidad** > **Citas** > **Presupuestos de proyectos** y seleccione el presupuesto del proyecto que desea enviar.
2. En la página **Presupuestos de proyectos**, en la pestaña **Presupuesto**, en el grupo **Proceso**, seleccione **Enviar presupuesto**. El estado del presupuesto se actualiza a **Enviado**.

> [!NOTE]
> No puede modificar un presupuesto de proyecto después de que el estado se cambie a **Enviado**.
