---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 1: Creación de formato)'
description: Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1742582057cc912d8e6f90eb14e9e4cdcd193608
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684724"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>Informe electrónico Configurar el formato para contar y sumar (Parte 1: Creación de formato)

[!include [banner](../../includes/banner.md)]

Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obtenga acceso a la lista de configuraciones proporcionada por Microsoft
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que “Litware, Inc.” está disponible y marcado como activo.  
2. Seleccione "Litware, Inc." Inc.
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

