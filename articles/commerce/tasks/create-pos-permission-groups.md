---
title: Crear grupos de permisos de PDV
description: Este artículo explica cómo crear un grupo de permisos de PDV.
author: josaw1
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailPosPermissionGroup, HcmJob
ms.openlocfilehash: 0aa394e5dc6685954c31cdddae7cdc042b80af29
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277970"
---
# <a name="create-pos-permission-groups"></a>Crear grupos de permisos de PDV

[!include [banner](../includes/banner.md)]

Este artículo explica cómo crear un grupo de permisos de PDV. La empresa de datos de prueba utilizada para crear esta tarea es USRT. Esta tarea está pensada para el rol de encargado de operaciones de Commerce.

1. En el panel de navegación, vaya a **Módulos > Retail y Commerce> Empleados > Grupos de permisos**.
2. Seleccione **Nuevo**.
3. En el campo **Id. de grupo de permisos de PDV**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Seleccione **Sí** en el campo **Ver entradas de reloj de tiempo**. Ahora puede habilitar o deshabilitar varios permisos para el grupo de permisos de PDV. Para algún permiso puede establecer un valor que se usará para evaluar si el usuario del PDV puede realizar la acción. Esta guía de tareas permite algunos permisos que se pueden dar a un cajero.  
6. Seleccione **Sí** en el campo **Permitir creación de pedidos**.
7. Seleccione **Sí** en el campo **Permitir edición de pedidos**.
8. Seleccione **Sí** en el campo **Permitir recuperación de pedidos**.
9. Seleccione **Sí** en el campo **Permitir cambio de contraseña**.
10. Seleccione **Sí** en el campo **Permitir cierre en ciego**.
11. Seleccione **Guardar**. Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales de Commerce. 
12. En el Panel de exploración, vaya a **Módulos > Recursos humanos > Trabajos > Trabajos**.
13. A continuación asignaremos el grupo de permisos de PDV a un trabajo. En la lista, busque y seleccione el registro deseado.
14. Seleccione **Editar**.
15. Expanda la sección **Clasificación de trabajos**.
16. En el campo Grupo de permisos de PDV, especifique o seleccione un valor. Todos los trabajadores de puestos para este trabajo usarán los parámetros de este grupo de permisos de PDV a menos que los permisos de PDV de los trabajadores se hayan anulada en su nivel del puesto.  
17. Seleccione **Guardar**. Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
