---
title: Trabajar con grupos de publicación
description: En este tema se describe la característica de grupos de publicación de Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b623573f598f6b21291cafe95fa04e6777cffe11
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244848"
---
# <a name="work-with-publish-groups"></a>Trabajar con grupos de publicación


[!include [banner](includes/banner.md)]

En este tema se describe la característica de grupos de publicación de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los sitios web de comercio electrónico se actualizan constantemente con nuevos contenidos durante todo el año. Las actualizaciones a menudo se publican por lotes en torno a eventos de gran actividad de comercio electrónico, como los días festivos, las campañas de marketing estacionales o los lanzamientos promocionales. Estas actualizaciones suelen requerir que grupos de contenidos del sitio web (por ejemplo, páginas, imágenes, fragmentos y plantillas) se organicen, validen y publiquen simultáneamente en una sola acción.

La capacidad de agrupar elementos en conjuntos lógicos que publican elementos juntos, donde cada conjunto tiene su propio ciclo de vida, ofrece muchas ventajas a los autores de sitios. En Commerce, estos conjuntos lógicos se conocen como grupos de publicación. Permiten a los autores de sitios hacer un seguimiento de conjuntos de actualizaciones como sus propias entidades configurables, comprobables y publicables.

Los autores pueden obtener una vista previa de las actualizaciones en un grupo de publicación por etapas sin que esto afecte al sitio que está en marcha ni a otros grupos de publicación independientes. Luego, los autores pueden programar la acción de publicación para publicar simultáneamente todos los elementos del grupo de publicación en el sitio en activo. La capacidad de agrupar, previsualizar y programar actualizaciones para la publicación es importante para muchas empresas de nivel empresarial que generan considerables ingresos anuales en torno a los hitos de actualización del sitio basados en eventos.

Las empresas pueden incurrir en costes por despliegues de contenido lentos o invalidados que no funcionan correctamente. Los grupos de publicación ayudan a garantizar que los lanzamientos se organicen, validen y publiquen a tiempo. Ya sean grandes o pequeños, los grupos de publicación proporcionan un valioso conjunto de herramientas que ayuda a los autores a organizar y simplificar las tareas de actualización continua del sitio.

## <a name="when-to-use-publish-groups"></a>Cuándo usar los grupos de publicación

Puede usar grupos de publicación siempre que deba almacenar provisionalmente y publicar varios documentos juntos. Por ejemplo, si su sitio web actualiza el contenido cada temporada, puede crear grupos de publicación para estos movimientos de marketing estacionales. Su grupo de publicación "Actualización estacional de otoño" puede contener nuevas imágenes estacionales, fragmentos con mensajes de marketing estacionales, páginas que incluyen colecciones de productos estacionales u otras actualizaciones estacionales del sitio web.

Una ventaja de los grupos de publicación es que permiten organizar varias actualizaciones en paralelo. Por ejemplo, poco después de la actualización para el grupo de publicación "Actualización estacional de otoño", podría haber una actualización de contenido para un fin de semana festivo específico. En este caso, puede almacenar provisionalmente el contenido para el grupo de publicación "Actualización estacional de otoño" al mismo tiempo que organiza el contenido para un grupo de publicación "Actualización de vacaciones de otoño" posterior. Cada grupo de publicación contiene su propio conjunto único de páginas, imágenes, fragmentos, plantillas, etc. Puede organizar, previsualizar y validar estos dos grupos de publicación de forma independiente pero en una escala de tiempo simultánea. Cada grupo de publicación se puede programar para que se publique en su sitio en fechas y horas específicas.

## <a name="turn-on-the-publish-groups-feature"></a>Activar la característica de grupos de publicación

La característica de grupos de publicación es opcional y debe activarse para el sitio.

Para activar la característica de grupos de publicación para el sitio en las herramientas de creación de Commerce, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo
1. En **Valor de configuración del sitio**, seleccione **Características**.
1. Establezca la opción **Grupos de publicación** en **Activada**.

## <a name="create-a-publish-group"></a>Crear un grupo de publicación

Para crear un grupo de publicación para el sitio en las herramientas de creación de Commerce, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Grupos de publicación**.
1. En la barra de comandos superior, seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear grupo de publicación**, bajo de **Nombre del grupo de publicación**, escriba un nombre descriptivo. A continuación seleccione **Aceptar**.

## <a name="set-the-publish-group-authoring-context"></a>Establecer el contexto de creación del grupo de publicación

En Commerce, el contexto de creación predeterminado es el contexto del sitio en activo. El contexto de creación del sitio en activo es la vista predeterminada donde puede ver y realizar cambios directamente en su sitio web sin utilizar un grupo de publicación. Representa las últimas actualizaciones directas a la versión publicada de su sitio. Si el control de contexto en **Grupos de publicación** en el panel de navegación izquierdo muestra el nombre **Sitio en activo**, está trabajando en el contexto de creación de sitio en activo. **Sitio en activo** es el nombre predeterminado del control de contexto. De lo contrario, el control de contexto muestra el nombre de un grupo de publicación.

Para trabajar en un grupo de publicación, debe cambiar al contexto de creación del grupo de publicación. Para establecer el contexto del grupo de publicación, siga uno de estos pasos.

- En el panel de navegación izquierdo, seleccione el control de contexto directamente debajo de **Grupos de publicación** y luego seleccione el nombre del grupo de publicación en la lista de opciones que aparece. El control de contexto cambia de nombre y muestra el nombre del grupo de publicación.
- En el panel de navegación izquierdo, seleccione **Grupos de publicación** y, a continuación, bajo **Grupos de publicación**, seleccione el nombre del grupo de publicación. El control de contexto cambia de nombre y muestra el nombre del grupo de publicación.

Después de establecer el contexto de creación de grupo de publicación, estará trabajando en ese contexto de grupo de publicación cuando obtenga una vista previa y edite el contenido del sitio.

Para volver al contexto de creación de sitio en activo predeterminado, seleccione el control de contexto y, a continuación, seleccione **Sitio en activo**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Agregar páginas u otros elementos a un grupo de publicación

Después de seleccionar un contexto de creación de grupo de publicación y cuando el control de contexto en el panel de navegación izquierdo muestre su nombre, podrá crear contenido tal como lo hace en el contexto predeterminado del sitio en activo. También puede agregar páginas existentes u otros elementos de otros grupos de publicación, o desde el contexto del sitio en activo.

Para copiar páginas existentes a un grupo de publicación, siga estos pasos.

1. Seleccione el contexto de creación para copiar y luego, en el panel de navegación izquierdo, seleccione **Páginas**.
1. Seleccione la página que desea agregar a un grupo de publicación.
1. En la barra de comandos, seleccione **Copiar al grupo de publicación**.
1. En el cuadro de diálogo **Seleccionar un grupo de publicación**, seleccione el grupo de publicación al que desea agregar la página y, a continuación, seleccione **Aceptar**.

Puede utilizar los mismos pasos básicos para crear páginas de productos personalizadas, direcciones URL, plantillas, diseños, fragmentos y activos de biblioteca de medios, o para agregar elementos existentes de estos tipos a un grupo de publicación.

## <a name="validate-a-publish-group"></a>Validar un grupo de publicación

Para asegurarse de que se satisfagan todas las dependencias del contenido del grupo de publicación y que se pasen todas las validaciones, puede ejecutar la validación para identificar cualquier problema que deba abordarse antes de programar una acción de publicación.

Para validar su grupo de publicación antes de programarlo, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Grupos de publicación**.
1. Seleccione el grupo de publicación que desea validar.
1. En la barra de comandos, seleccione **Validar**.

La validación se ejecuta en todo el contenido del grupo de publicación. Cualquier problema que impida una acción de publicación correcta se muestra en un cuadro de notificación que aparece en la esquina superior derecha.

> [!NOTE]
> La validación siempre se ejecuta automáticamente cuando se programa un grupo de publicación. Sin embargo, el botón **Validar** de la barra de comandos es útil porque ayuda a identificar los problemas que debe solucionar antes de intentar programar un grupo de publicación para que se active.

## <a name="schedule-a-publish-group-to-go-live"></a>Programar un grupo de publicación para que se active

Para programar un grupo de publicación para que se active en su sitio, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Grupos de publicación**.
1. En **Grupos de publicación**, seleccione el grupo de publicación que desea programar.
1. En la barra de comandos, seleccione **Editar programación**. Aparece el cuadro **Editar programación**.
1. Seleccione la fecha y la hora en que se debe activar el grupo de publicación y, a continuación, seleccione **Aceptar**.

Para cancelar la programación de un grupo de publicación, siga los mismos pasos, pero active **Cancelar programación de grupo de publicación** en el cuadro de diálogo **Editar programación**.

> [!NOTE]
> Los grupos de publicación muy grandes pueden tardar hasta un minuto o dos en publicarse cuando llegue la hora programada. Tenga en cuenta que una acción de publicación no es instantánea y que los grupos de publicación más pequeños se publicarán más rápido.

## <a name="publish-groups-faq"></a>Preguntas frecuentes sobre los grupos de publicación

**¿Cuántos elementos puede haber en un grupo de publicación?**

Actualmente, hay un límite de 2000 elementos por grupo de publicación. Tenga en cuenta que los grupos de publicación muy grandes pueden tardar varios minutos en publicarse cuando llegue la hora programada.

**¿Los grupos de publicación son como "ramas" de código en la terminología de desarrollo de software?**

Sí y no. Los grupos de publicación pueden considerarse como versiones bifurcadas del sitio. En ese sentido, actúan como ramas. Sin embargo, no existe el concepto de fusión a nivel de elementos individuales. El último elemento publicado solo sobrescribe lo que existía anteriormente, y la acción de publicación más reciente siempre reemplaza a las acciones de publicación anteriores.

**¿Puedo programar dos grupos de publicación para que se publiquen a la vez?**

N. º Por razones de rendimiento y para evitar conflictos, el sistema le obligará a escalonar los grupos de publicación programados con una diferencia mínima de cinco minutos.

**¿Puedo usar grupos de publicación para programar elementos administrativos omnicanal, como descuentos y actualizaciones de productos?**

Actualmente, la característica de grupos de publicación solo admite contenido de sitio web. Sin embargo, Microsoft es consciente de que la integración con escenarios de comercialización administrativos podría ser valiosa para la coordinación y automatización de los lanzamientos de campañas omnicanal.

## <a name="additional-resources"></a>Recursos adicionales

[Métodos para agregar contenido](add-manage-content.md)

[Glosario del modelo de página](page-elements-overview.md)

[Estados y ciclo de vida de documentos](document-states-overview.md)

[Habilitar y usar el uso compartido entre canales](cross-channel-sharing.md)

[Trabajar con módulos](work-with-modules.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Personalizar navegación del sitio](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]