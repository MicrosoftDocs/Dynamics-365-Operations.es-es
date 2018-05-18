--- 
title: "Preparar modelos de datos para usar archivos de gestión documental en salidas de formato"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f99259056fab2d56d1ccf7487681c183551c64f
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="prepare-data-model-to-use-document-management-files-in-format-outputs"></a>Preparar modelos de datos para usar archivos de gestión documental en salidas de formato

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.

Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obtenga acceso a la lista de configuraciones proporcionada por Microsoft
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor “Litware, Inc.” está disponible y marcado como activo.  
2. Seleccione el proveedor "Litware, Inc.
3. Haga clic en Repositorios.
    * Si ya existe un repositorio tipo “Recursos de operaciones", omita los pasos restantes de la subtarea actual.  
4. Haga clic en Agregar para abrir el cuadro desplegable.
5. En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".
6. Haga clic en Crear repositorio.
7. Haga clic en Aceptar

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Obtenga las configuraciones del modelo de factura de Cliente proporcionadas por Microsoft
1. Haga clic en Mostrar filtros.
2. Aplique los filtros siguientes: Introduzca un valor de filtro de “Recursos de operaciones” en el campo ”Nombre” mediante el operador de filtro “comienza con”; introduzca un valor de filtro de "" en el campo “Descripción”, mediante el operador de filtro “comienza con”
3. Haga clic en Mostrar filtros.
4. Haga clic en Abrir.
5. En el árbol, seleccione “Modelo de factura del cliente”.
    * Seleccione la configuración del modelo “Modelo de factura del cliente” para importarla.  
6. Haga clic en Importar.
    * Haga clic en importar la versión 1 de la configuración seleccionada.  
7. Haga clic en Sí.
8. Cierre la página.
9. Cierre la página.
10. Haga clic en Configuraciones de informes.
11. En el árbol, seleccione “Modelo de factura del cliente”.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Cree el modelo derivado para admitir el acceso a los archivos de la gestión de documentos.
    * Usted creará su propia configuración del modelo de factura de Cliente derivándola de la configuración proporcionada por Microsoft. Use esta configuración para implementar el acceso a los archivos de gestión de documentos, y permita que estén disponibles para los documentos electrónicos que cree en base a este modelo.  
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, introduzca “Derivar de nombre: Modelo de factura de cliente, Microsoft”.
3. En el campo Nombre, introduzca "Modelo de factura de cliente (personalizado)".
    * Modelo de factura de cliente (personalizado)  
4. Haga clic en Crear configuración.


