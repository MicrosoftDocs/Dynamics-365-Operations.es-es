---
title: 'Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 1: Preparación del modelo de datos)'
description: En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b82b1719990caeb1b383ab806a3e09a4c4a6e41a
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026143"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 1: Preparación del modelo de datos)

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


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
Usted creará su propia configuración del modelo de factura de Cliente derivándola de la configuración proporcionada por Microsoft. Use esta configuración para implementar el acceso a los archivos de gestión de documentos, y permita que estén disponibles para los documentos electrónicos que cree en base a este modelo.  
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, introduzca “Derivar de nombre: Modelo de factura de cliente, Microsoft”.
3. En el campo Nombre, introduzca "Modelo de factura de cliente (personalizado)".
    * Modelo de factura de cliente (personalizado)  
4. Haga clic en Crear configuración.

