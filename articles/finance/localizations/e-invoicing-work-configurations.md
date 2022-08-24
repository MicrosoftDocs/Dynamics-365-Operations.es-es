---
title: Trabajar con configuraciones
description: Este artículo proporciona una descripción general del escenario principal para trabajar con configuraciones de informes electrónicos (ER) desde el espacio de trabajo de funciones de globalización.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d87559405d2490c314eb2c8b88268af0dc0dfaca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283067"
---
# <a name="work-with-configurations"></a>Trabajar con configuraciones

[!include [banner](../includes/banner.md)]

Las configuraciones de informes electrónicos (ER) son uno de los principales conjuntos de componentes de las funciones de facturación electrónica. Una configuración de ER contiene la configuración de la estructura de archivos y un conjunto de reglas de transformación para transformar datos de dos maneras:

- **Exportar configuración de formato ER** – Esta configuración transforma los datos de la estructura interna unificada (modelo ER) al formato de archivo electrónico.
- **Importar configuración de formato ER** – Esta configuración transforma los datos del formato de archivo electrónico a la estructura interna unificada (modelo ER).

Además de generar archivos electrónicos salientes en el formato predefinido, las configuraciones de ER se utilizan ampliamente para analizar los mensajes entrantes de servicios web externos como respuestas. Esta funcionalidad ayuda a crear una lógica configurable para obtener los resultados de la comunicación con canales externos, convertir esos resultados (códigos, mensajes y registros) en una estructura legible por el usuario y luego pasar esa información a la aplicación del cliente.

Para comenzar a utilizar las configuraciones de ER en su función de facturación electrónica, debe vincularlas a la función y hacer que estén disponibles en la pestaña **Configuraciones** para la versión actual de la función. Puede trabajar con una configuración de ER vinculada seleccionando **Agregar**, **Borrar**, **Editar**, o **Vista**.

Antes de que pueda agregar un enlace a una configuración de ER, la configuración debe existir en su repositorio del Regulatory Configuration Service (RCS). Para revisar las configuraciones de ER que están disponibles en su repositorio de RCS, siga estos pasos.

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Informe electrónico**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.

Para obtener información sobre cómo crear una nueva configuración de ER o importar una configuración de ER existente desde el repositorio global, consulte [Informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ajustar una configuración de ER vinculada, seleccione **Editar** en la pestaña **Configuraciones** para la función de facturación electrónica actual. El sistema crea automáticamente una versión de la configuración de ER. Si la versión actual no fue creada por el proveedor de configuración activo, el sistema crea una versión derivada que usa su proveedor de configuración. Si la versión actual fue creada por el proveedor de configuración activo, el sistema crea una nueva versión. En ambos casos, puede modificar la versión que se crea y luego realizar automáticamente todas las actualizaciones necesarias.
