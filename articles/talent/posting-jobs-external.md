---
title: Registrar trabajos en sitios externos profesionales desde Attract
description: Este tema explica cómo usar Dynamics 365 for Talent - Attract para registrar trabajos en sitios de contratación externos
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2019
ms.locfileid: "993677"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Registrar trabajos en sitios externos profesionales desde Attract

[!include [banner](../includes/banner.md)]

Usted quiere presentar sus vacantes a tantos candidatos cualificados como sea posible. Los sitios de contratación como Broadbean se lleva a cabo este objetivo. Microsoft Dynamics 365 Talent: Attract ahora le permite registrar trabajos en Broadbean y Microsoft proporciona constantemente nuevas ofertas en esta área.

## <a name="post-jobs-to-broadbean"></a>Registrar trabajos en Broadbean

Antes de poder registrar trabajos en Broadbean debe configurar la integración con Broadbean.

> [!NOTE]
> - Para registrar trabajos en los sitios externos, debe tener el [Complemento de contratación completo](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Esta característica está actualmente en vista previa. Si desea probarlo, debe [activarlo en la configuración de administrador de Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Configurar integración de Broadbean

1. Iniciar sesión en Attract como administrador.
2. Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha de la página y a continuación seleccione **Centro de administración**.
3. En la pestaña **Configuración de oportunidades de trabajo** , en la sección **Integración de Broadbean**, active la integración.
4. Póngase en contacto con Broadbean y introduzca su información en **Nombre de usuario, identificador de cliente, token de cifrado**.

> [!WARNING]
> Sus credenciales de Broadbean son importantes y confidenciales. Por lo tanto, almacénelas y compártalas de forma responsable. Cualquiera que tenga un rol de administrador en Attract puede ver estas credenciales.

> [!NOTE]
> Microsoft y Attract no están involucradas en crear y mantener estos valores. Es su responsabilidad mantenerlas actualizadas en Attract y trabajar con Broadbean para resolver los problemas relacionados con sus credenciales.

### <a name="post-a-job-to-broadbean"></a>Registrar un trabajo en Broadbean

Una vez Broadbean está activado, los reclutadores y los administradores pueden registrar un trabajo. Debe tener una URL de solicitud para el trabajo.

1. En Attract, abra el trabajo que desee registrar en Broadbean.
2. En la sección **Registros**, seleccione el botón **Registrar ahora** que corresponde a Broadbean.
3. Siga las instrucciones en la ventana de Broadbean.

Attract pasa la siguiente información a Broadbean:

- Id. de solicitud
- Cargo laboral
- Descripción del trabajo
- Ubicación de trabajo
- URL de la solicitud
- Información del contratante

Una vez que Broadbean complete con éxito correctamente el registro, la sección **Registros** del trabajo en Attract muestra el estado de Broadbean como **Registrado**.

> [!NOTE]
> - Broadbean requiere el campo **Sector**. Actualmente este cambo está establecido **TI** de forma predeterminada. Sin embargo, puede cambiar el valor al sector correcto en la ventana para la oferta de empleo de Broadbean.
> - Broadbean necesitará algo de tiempo para terminar de registrar su trabajo en todas las bolsas de empleo que haya seleccionado. Por lo tanto, puede haber un retraso leve antes de que Attract proporcione una actualización del estado del empleo.

### <a name="view-a-broadbean-job-posting"></a>Ver un registro de oferta de empleo en Broadbean

Después de registrar un trabajo en Broadbean, podrá verlo desde Attract.

1. En Attract, abra el trabajo que desee ver en Broadbean.
2. En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Ver**.

El registro de empleo de la Broadbean aparece en una ventana nueva.

### <a name="update-a-broadbean-job-posting"></a>Actualizar un registro de oferta de empleo en Broadbean

Puede actualizar una oferta de empleo en Broadbean de dos maneras.

1. En Attract, abra el trabajo que desee actualizar.
2. En la sección **Registros**, seleccione el botón **Actualizar registro** que corresponde a Broadbean.
3. Edite el registro en la ventana de Broadbean.

O bien

1. En Attract, abra el trabajo que desee ver en Broadbean.
2. En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Ver**.
3. En la ventana de Broadbean, editar los detalles del trabajo y, a continuación registre de nuevo el trabajo. Los detalles del trabajo en Attract no se modifican.

### <a name="remove-a-broadbean-job-posting"></a>Eliminar un registro de oferta de empleo en Broadbean

Puede quitar una oferta de trabajo de Broadbean según sea necesario.

1. En Attract, abra el trabajo que desee quitar.
2. En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Eliminar registro**.

Una vez que Broadbean quite el trabajo, el artículo de Broadbean en Attract tendrá un botón **Registrar ahora**. La presencia de este botón indica que el trabajo se ha quitado y se puede volver a registrar.

### <a name="troubleshoot-the-broadbean-integration"></a>Solución de problemas de la integración con Broadbean

Si está teniendo problemas registrando un trabajo en Broadbean, intente estos pasos.

1. Compruebe que las credenciales de Broadbean que ha especificado en Attract son válidas y correctas.
2. Si las credenciales son válidas y correctas, contacte con el [Soporte técnico de Broadbean](https://www.broadbean.com/resources/support/).
3. Si el problema continúa, contacte con el [Soporte técnico de Microsoft](./talent-support.md).
