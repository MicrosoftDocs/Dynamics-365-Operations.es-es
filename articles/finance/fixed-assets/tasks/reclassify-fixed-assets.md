---
title: Reclasificar activos fijos
description: Este tema explica el proceso de reclasificación de activos. Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5fadebe685810d6833d1cb0581ed9a4869cc124
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883655"
---
# <a name="reclassify-fixed-assets"></a>Reclasificar activos fijos

[!include [banner](../../includes/banner.md)]

Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo. 

Cuando se reclasifica un activo fijo:

- Todos los libros del activo fijo existente se crean para el activo fijo nuevo. Cualquier información que se haya configurado para el activo fijo se copia en el activo fijo nuevo. El estado de los libros para el activo fijo original es Cerrado. 

- Los libros nuevos para un nuevo activo fijo contienen la fecha de reclasificación en el campo **Fecha de adquisición**. La fecha del campo **Fecha de ejecución de la depreciación** se copia de la información del activo original. Si ya se inició la depreciación, el campo **Fecha en la que se ejecutó la última depreciación** mostrará la fecha de reclasificación. 

- Las transacciones de activos fijos existentes para el activo fijo original se cancelan y se vuelven a generar para el activo fijo nuevo.

- Cuando un activo que tiene una transacción de transferencia ha sido reclasificado, el sistema mostrará un mensaje en el **Centro de acciones** para indicar que una transacción de transferencia no se completó durante el proceso de reclasificación. Es necesario completar una transacción de transferencia para mover las transacciones de reclasificación existentes a las dimensiones financieras adecuadas. 

   Durante el proceso de reclasificación, el sistema ejecuta las siguientes acciones para reclasificar el saldo de activo del activo original al activo nuevo. 
   
   - El proceso de reclasificación copia los datos del libro de activos fijos original al nuevo libro de activos fijos.

   - La transacción de reclasificación utiliza información de la adquisición contabilizada original que incluye información de la dimensión financiera que se incluye en la transacción de adquisición.  
   
   - Al mismo tiempo, el proceso de reclasificación revierte la transacción original de adquisición y transferencia de activos. 

El siguiente diagrama y procedimiento proporcionan un ejemplo del proceso de reclasificación. 

[![Diagrama que muestra el proceso de reclasicificación.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

Siga estos pasos para reclasificar un activo fijo:

1. Vaya a **Activos fijos > Tareas periódicas > Reclasificación**.
2. En el campo **Grupo de activos fijos**, seleccione el grupo a reclasificar.
3. En el campo **Número de activo fijo**, seleccione el activo fijo a reclasificar.
4. En el campo **Nuevo grupo de activos fijos**, seleccione un grupo al que transferirle el activo fijo.
    * Si el nuevo grupo de activos fijos está vinculado a una secuencia numérica, el campo **Nuevo número de activo fijo** se actualiza con el número de la nueva secuencia numérica del grupo de activos fijos. De no ser así, el campo **Nuevo número de activo fijo** se actualizará con el número de la secuencia numérica que esté configurada en la página de los **Parámetros de activo fijo**. Si no hay configurada una secuencia numérica en la página de **Parámetros del Activo fijo**, introduzca un número en el campo **Nuevo número de activo fijo**.  
5. En el campo **Fecha de reclasificación**, escriba una fecha.
6. En el campo **Series de asientos**, especifique o seleccione un valor.
7. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
