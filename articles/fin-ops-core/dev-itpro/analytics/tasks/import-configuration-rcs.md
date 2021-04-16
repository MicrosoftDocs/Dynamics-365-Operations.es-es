---
title: (ER) Importar configuraciones desde RCS
description: En este tema se proporciona información acerca de cómo un usuario puede importar una nueva versión de una configuración de ER desde RCS.
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77d637b2ec1deeabc04a6796644363b330f5756e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744900"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importar configuraciones desde RCS

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Regulatory Configuration Services (RCS). En este ejemplo, seleccionará la versión de la configuración de ER que se ha configurado en una instancia de RCS y la importará en la instancia actual para la empresa de ejemplo, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa ya que las configuraciones de ER se comparten entre empresas. Para completar estos pasos, primero debe completar los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). Para completar estos pasos, también debe tener acceso a una instancia de RCS que contenga al menos una configuración de ER en estado **Completado** o **Compartido**.

1. Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**. 
2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**. Si no ve a este proveedor de configuración, complete los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). 
3. Si no tiene ningún entorno de RCS aprovisionado en su empresa, seleccione el vínculo externo **Regulatory services – Configuration** y siga las instrucciones para aprovisionar un entorno de RCS. 
4. Seleccione **Parámetros de informes electrónicos**. 
5. Seleccione la pestaña **RCS**. 
6. Si ya se ha aprovisionado un entorno de RCS a su empresa, utilice las direcciones URL presentadas en la página para obtener acceso. 
7. Cierre la página. 

## <a name="register-a-new-er-repository"></a>Registrar un nuevo repositorio de ER. 
1. En la lista, marque la fila seleccionada. 
2. Seleccione el proveedor Litware, Inc. 
3. Seleccione Repositorios. 
4. Seleccione Agregar para abrir el cuadro desplegable. 
5. En el campo Repositorio de configuración, escriba "RCS". 
6. Seleccione Crear repositorio. 
7. En el campo Nombre de visualización del entorno de RCS, especifique o seleccione un valor. 
8. Seleccione la instancia de RCS que desee. Puede tener varias. 
9. Seleccione Aceptar. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importe las configuraciones de ER desde el repositorio basado en RCS
1. Seleccione **Mostrar filtros**. 
2. Introduzca un valor de filtro de "RCS" en el campo **Nombre** mediante el operador de filtro **empieza por**. 
3. Cuando abra el repositorio seleccionado, en la página **Conectarse a Regulatory Configuration Services** , seleccione el vínculo **Seleccione aquí para conectarse a Regulatory Configuration Services**. 
4. Seleccione **Abrir**. 
5. Seleccione **Cerrar**. 
6. Seleccione la versión deseada de la configuración de ER y seleccione en **Importar** para traerla a la instancia actual.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]