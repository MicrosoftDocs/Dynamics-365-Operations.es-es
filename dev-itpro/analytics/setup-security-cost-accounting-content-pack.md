---
title: "Seguridad Configuración para el contenido de Power BI de análisis de la contabilidad de costes"
description: "Este tema explica cómo puede extender la seguridad de nivel de acceso en fila- seguridad de nivel de la contabilidad de costes en BI de la potencia de Microsoft. Esta función permite garantizar que los usuarios consultan solo datos de Power BI que se les conceden acceso."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Seguridad Configuración para el contenido de Power BI de análisis de la contabilidad de costes

Este tema explica cómo puede extender la seguridad de nivel de acceso en fila- seguridad de nivel de la contabilidad de costes en BI de la potencia de Microsoft. Esta función permite garantizar que los usuarios consultan solo datos de Power BI que se les conceden acceso.

<a name="overview"></a>Visión general
--------

** Análisis de la contabilidad de costes ** las aplicaciones para contenido de Power BI de Microsoft accionan seguridad de nivel fila- de BI para limitar el acceso de usuario. La seguridad se basa en la jerarquía organizativa del nivel de acceso que se configuran en los parámetros de contabilidad de costes. Para obtener más información sobre ** análisis de la contabilidad de costes ** accione el contenido de BI, consulte [] contenido de Power BI de análisis de la contabilidad de costes (contabilidad de costes - analysis-content-pack.md).

## <a name="setup"></a>Configuración
Para propagar seguridad de nivel de acceso para el accionar BI, el propietario de contenido de Power BI debe seguir estos pasos. ** Nota: ** El usuario que publica ** análisis de la contabilidad de costes ** el contenido de Power BI se convierte automáticamente en el propietario. Sólo un propietario puede configurar la seguridad en BI de la potencia. Además, hasta que un propietario agregue a otros usuarios en PowerBI.com para nadie, a menos que el propietario pueda ver los datos en ** análisis de la contabilidad de costes ** accione el contenido de BI.

1.  Publicar el archivo de definición para el accionar BI.
2.  Iniciar sesión en PowerBI.com.
3.  Encuentre el conjunto de datos para ** análisis de la contabilidad de costes accionan ** el contenido de BI.
4.  Abrir la página de seguridad. 

    [![que abre la página] de seguridad (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png) (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)]

5.  ** Controlador de objeto de coste ** el rol se crea ya. Agregar a otros miembros que forman parte de la jerarquía organizativa del nivel de acceso de la contabilidad de costes. 

    [] miembros de la adición![(https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png) (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)]

Los usuarios que se agregan ** controlador de objeto de coste ** al rol sólo verán los datos que se les permite ver, según la definición de la jerarquía organizativa del nivel de acceso de la contabilidad de costes. ** Nota: ** la seguridad de nivel Fila- se aplica a los mosaicos y informa en Microsoft Dynamics 365 para las operaciones que se insertan de Power BI.

## <a name="updating-security"></a>Actualizar seguridad
Si las actualizaciones se crean a la seguridad de nivel de acceso en contabilidad de costes, y desea que el BI de la potencia para reflejar las actualizaciones, debe actualizar la entidad que el almacén para ** análisis de la contabilidad de costes acciona ** el contenido de BI. Una vez completado el almacén de la entidad actualizado de Dynamics 365 para las operaciones, deberá actualizar artefactos en PowerBI.com. Para obtener más información relativa a cómo realizar una actualización de la tienda de la entidad, consulte [actualizar la entidad almacenada power-bi-integration-entity-store.md#update-entity-store] (). El propietario ** análisis de la contabilidad de costes ** de contenido de Power BI debe también hacer un almacén de la entidad actualizado si se concede a los nuevos usuarios el acceso a la jerarquía organizativa. Además, el propietario debe agregar a los nuevos usuarios ** sobre el controlador del objeto ** al rol en PowerBI.com, para aplicar la seguridad de nivel fila- para ellos.

## <a name="disabling-security"></a>Deshabilitar seguridad
Asumimos que la organización desea restringir el acceso a los datos. Si, por algún motivo, se deshabilitarán los parámetros de seguridad al ejecutar la contabilidad de costes, el propietario debe agregar usuarios ** contable de coste ** en la función de BI de la potencia en su lugar. Si cambia seguridad de una comunidad habilitado un estado de los deshabilitado, es recomendable quitar usuarios ** sobre el controlador del objeto ** del rol. Y viceversa si vuelve a permitir seguridad. Los usuarios pueden pertenecer a ambos roles. El acceso común es la Unión de ambos roles. En el caso de ** análisis de la contabilidad de costes ** accione el contenido de BI, los usuarios que obtienen acceso común tener acceso a datos sin restricción. Si su objetivo es aplicar restringido acceso, los usuarios deben asignarse sólo ** sobre el controlador del objeto ** al rol. Estos actualizaciones de seguridad de nivel fila- tienen efecto inmediatamente. Los usuarios afectados deben actualizar sus exploradores.

## <a name="additional-resources"></a>Recursos adicionales
Para obtener más información acerca de la seguridad de nivel fila- de Power BI, consulte [administrar la seguridad en su modelo en el BI] de la potencia (https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


