--- 
title: "Crear el formato de recuento y suma para informes electrónicos (ER)"
description: "Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: efdb64fa157af0d96c2ff0e5de3db5a98190bc68
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-formate-for-counting-and-summing-for-electronic-reporting-er"></a>Crear el formato de recuento y suma para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.

Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obtenga acceso a la lista de configuraciones proporcionada por Microsoft
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor “Litware, Inc.” está disponible y marcado como activo.  
2. Seleccione el proveedor "Litware, Inc.
3. Haga clic en Repositorios.
    * Si ya existe un repositorio del tipo "Recursos de Operations", omita los pasos restantes de la subtarea actual.  
4. Haga clic en Agregar para abrir el cuadro desplegable.
5. En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".
6. Haga clic en Crear repositorio.
7. Haga clic en Aceptar

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Obtenga las configuraciones de Intrastat proporcionadas por Microsoft
1. Haga clic en Abrir.
2. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".
3. Haga clic en Importar.
    * Haga clic en Importar para la versión 1.1 de la configuración seleccionada.  
4. Haga clic en Sí.
5. Cierre la página.
6. Cierre la página.
7. Haga clic en Configuraciones de informes.
8. En el árbol, expanda "Intrastat modelo".
9. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".


