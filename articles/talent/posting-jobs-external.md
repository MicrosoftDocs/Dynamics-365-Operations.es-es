---
title: Registrar trabajos en sitios externos profesionales desde Attract
description: Este tema explica cómo usar Dynamics 365 for Talent - Attract para registrar trabajos en sitios de contratación externos
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 936ff85a4dabb715cb83b875a5c58c9fb7a0ac26
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739826"
---
# <a name="post-jobs-to-broadbean"></a>Publicar ofertas de empleo en Broadbean

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent: Attract ayuda a obtener el talento que necesita dejándole enviar sus trabajos directamente de Attract a Broadbean. Tras [crear un trabajo](./creating-jobs-attract.md) sólo tiene que hacer clic en un botón para poner el trabajo delante de todos los candidatos potenciales en Broadbean.

Enviar trabajos a Broadbean requiere una licencia adecuada de Broadbean. Broadbean proporciona diversos productos y planes. Para obtener más información acerca de licencias y precios de Broadbean, [póngase en contacto con Broadbean](https://www.broadbean.com/contact-us/).

Si es administrador y necesita obtener más información sobre cómo configurar la integración de Broadbean con Attract, consulte [Especificar valores para plataformas de trabajo externas](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Publicar ofertas de empleo en Broadbean

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
2. En la pestaña **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a Broadbean y, a continuación, seleccione **Ver**.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>Solución de problemas de registro de trabajos en Broadbean

Si está teniendo problemas registrando un trabajo en Broadbean, intente estos pasos.

1. Compruebe que las credenciales de Broadbean que ha especificado en Attract son válidas y correctas.
2. Si las credenciales son válidas y correctas, contacte con el [Soporte técnico de Broadbean](https://www.broadbean.com/resources/support/).
3. Si el problema continúa, contacte con el [Soporte técnico de Microsoft](./talent-support.md).

## <a name="see-also"></a>Consulte también

[Crear trabajos](./creating-jobs-attract.md)

[Especificar valores para plataformas de trabajo externas](./attract-admin-job-board-settings.md)
