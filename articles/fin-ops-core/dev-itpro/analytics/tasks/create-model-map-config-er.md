---
title: Crear configuraciones de asignación de modelo de informes electrónicos (ER)
description: Use este procedimiento para diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c52f5d23f6c1cdad346a8a5e94535a4cba19057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562889"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>Crear configuraciones de asignación de modelo de informes electrónicos (ER)

[!include [banner](../../includes/banner.md)]

Use este procedimiento para diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes. En este procedimiento, creará una configuración para la empresa de ejemplo Litware, Inc. 

Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.

Estos pasos se pueden completar mediante cualquier conjunto de datos. Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo. Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  
2. Haga clic en Configuraciones de informes.
3. Haga clic en Mostrar filtros.
4. En el campo "Nombre" escriba el valor de filtro "Intrastat" y use el operador de filtro "empieza por".
    * Aplicar este filtro para buscar la configuración del modelo de datos de "Intrastat". Este modelo puede existir en el árbol de las configuraciones. Si es así, omita subtarea la siguiente.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Obtenga la configuración de modelo de Intrastat proporcionada por Microsoft
1. Cierre la página.
2. Cierre la página.
3. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
4. En la lista, busque y seleccione el registro deseado.
    * Seleccione el mosaico del proveedor de Microsoft.  
5. Haga clic en Repositorios.
    * Haga clic en Repositorios en el icono de proveedor de Microsoft.  
6. Haga clic en Mostrar filtros.
7. En el campo "Escribir el nombre" escriba el valor de filtro "recursos" y use el operador de filtro "contiene". 
8. Haga clic en Abrir.
9. En el árbol, seleccione 'Intrastat model'.
10. Haga clic en Importar.
11. Haga clic en Sí.
    * Se ha importado la configuración del modelo de ER que contiene el modelo de datos que usará para explorar cómo la nueva funcionalidad de ER se puede usar.  
12. Cierre la página.
13. Cierre la página.
14. Haga clic en Configuraciones de informes.

## <a name="add-a-new-model-mapping-configuration"></a>Agregar una nueva configuración de asignación de modelo
1. En el árbol, seleccione 'Intrastat model'.
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nuevo, especifique "Asignación de modelo según el modelo de datos Intrastat".
4. En el campo Nombre, escriba "Asignación de muestra de Intrastat".
    * Asignación de muestra de Intrastat  
5. Haga clic en Crear configuración.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]