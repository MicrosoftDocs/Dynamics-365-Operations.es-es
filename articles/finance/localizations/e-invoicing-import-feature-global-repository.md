---
title: Importar características del repositorio global
description: Este artículo explica cómo importar características de globalización del repositorio global.
author: gionoder
ms.date: 02/11/2022
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
ms.openlocfilehash: 5a72673e17c5653d43b60d3348d5518e09c40a15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278323"
---
# <a name="import-features-from-the-global-repository"></a>Importar características del repositorio global

[!include [banner](../includes/banner.md)]

El repositorio global contiene características de facturación electrónica que se comparten con su proveedor de configuración. Todas las características de facturación electrónica proporcionadas por Microsoft se comparten con todas las empresas. Tiene acceso automáticamente a todas las características de facturación electrónica que Microsoft lanza y publica en el repositorio global.

Para empezar a trabajar con las características de facturación electrónica que se comparten con su proveedor de configuración, impórtelas en su instancia de Regulatory Configuration Service (RCS) desde el repositorio global. Luego, revise los detalles de la característica, como las configuraciones de Informes electrónicos (ER) y las canalizaciones de procesamiento.

## <a name="import-a-feature-from-the-global-repository"></a>Importar una característica del repositorio global

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. Seleccione **Importar** para abrir la búsqueda **Importar característica del repositorio global**.
4. Para explorar las características de Facturación electrónica en el repositorio global que están disponibles para un proveedor de configuración específico, sincronice la instancia RCS de su organización seleccionando **Sincronizar**. Una vez completada la sincronización, se actualiza la lista de características de Facturación electrónica disponibles desde el repositorio global. Esta actualización puede tardar unos minutos.
5. Seleccione la característica que desea importar y luego seleccione **Importar**.

Para ver la característica de Facturación electrónica, asegúrese de que el proveedor de configuración correcto está seleccionado. De forma predeterminada, las características que creó el proveedor de configuración activo se filtran automáticamente. Puede ajustar el filtro para ver características creadas por otros proveedores, como el proveedor de configuración de Microsoft.

Ahora puede trabajar con la característica importada. Puede revisar sus detalles y crear una nueva característica utilizando la característica importada como plantilla.

> [!NOTE]
> Puede modificar una característica solo si la creó el proveedor de configuración que está actualmente activo. Puede crear una nueva entidad utilizando la características original como base. A continuación, puede realizar los cambios necesarios o configurar los parámetros.

Cuando Microsoft u otra empresa que comparte características de globalización con su empresa actualice las características que ha importado, puede buscar versiones actualizadas seleccionando **Buscar actualizaciones de características** en la sección **Configuración relacionadas** del espacio de trabajo **Características de globalización**.

Si ve que hay actualizaciones para una característica que usa como plantilla, puede importar una nueva versión después de sincronizar la lista de características publicadas en el repositorio global.
