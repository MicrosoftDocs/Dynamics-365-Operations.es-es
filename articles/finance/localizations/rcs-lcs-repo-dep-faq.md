---
title: 'Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)'
description: Este tema proporciona información sobre la eliminación del almacenamiento de Microsoft Dynamics Lifecycle Services (LCS) que está prevista como parte del despliegue del repositorio global de Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 68f1ed6a6d6bb0d15a81539da7f483ad71a4d696
ms.sourcegitcommit: 477efa4cb138f41d4f68bcd82552af3473bcc3d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2021
ms.locfileid: "7715239"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

El uso de Microsoft Dynamics Lifecycle Services (LCS) como repositorio de almacenamiento para las configuraciones de informes electrónicos (ER) se está desactivando. Esta desactivación implicará los siguientes cambios:

- Las configuraciones producidas por Microsoft que se utilizan en las aplicaciones de Microsoft Dynamics 365 ya no se publicarán en la biblioteca de activos compartidos en LCS. En su lugar, se publicarán solo a través del repositorio RCS Global. Sin embargo, las configuraciones para Dynamics AX 2012 seguirán publicándose en la biblioteca de activos compartidos en LCS hasta que finalice el ciclo de vida de soporte para AX 2012.
- La funcionalidad que permite subir configuraciones a la biblioteca de activos del proyecto en LCS desde las aplicaciones de Finance and Operations, y desde RCS, será desactivada. Sin embargo, podrá seguir utilizando el navegador en LCS para cargar configuraciones en la biblioteca de activos del proyecto. Por lo tanto, podrá seguir añadiendo configuraciones a LCS para que puedan incluirse en los paquetes de soluciones.
- La importación de configuraciones desde LCS seguirá estando disponible y seguirá siendo compatible con las aplicaciones de Finance and Operations, y en RCS, durante algún tiempo. Sin embargo, la funcionalidad se desactivará antes o después. (La fecha exacta de desactivación se anunciará más adelante)

## <a name="deprecation-notice"></a>Aviso de desactivación

La eliminación del uso de LCS como almacenamiento se comunicó en [Características eliminadas o obsoletas en Dynamics 365 Finance - Aviso de desactivación de LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). La fecha de desactivación prevista es el 1 de abril de 2022.

## <a name="key-features"></a>Funciones principales

- Utilizar RCS para crear y editar configuraciones de ER y funciones de globalización.
- Envíe las configuraciones directamente desde el diseñador RCS a una aplicación conectada, como un entorno de Dynamics 365 Finance, para que pueda realizar y probar cambios rápidamente en sus configuraciones.
- Almacene, comparta y gestione de forma centralizada el ciclo de vida de las configuraciones de ER y las funciones de globalización a través del almacenamiento centralizado del repositorio global.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Orientación para acciones puntuales y continuas

Esta sección describe un conjunto de pasos que deben completarse una vez. También describe los pasos que deben completarse de forma continua después.

### <a name="one-time-action"></a>Acción única

Importe todas las configuraciones requeridas desde LCS a RCS, y luego publíquelas desde RCS al repositorio Global. Si está utilizando bibliotecas de activos específicas del proyecto para almacenar configuraciones derivadas en LCS, los siguientes pasos deben completarse mientras LCS sigue siendo accesible.

1. Si una instancia de RCS no está ya disponible, aprovisione una. Para más información, consulte [la descripción general de RCS](rcs-overview.md).
2. En la instancia de RCS aprovisionada, para cada proyecto LCS en la biblioteca de activos que incluye configuraciones ER derivadas, registre el repositorio LCS apropiado.
3. Importe las configuraciones ER de los repositorios LCS a RCS. Para más información, consulte [Importar configuraciones desde LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Si el repositorio Global no se proporciona automáticamente, regístrelo en RCS.
5. Suba todas las configuraciones derivadas de la instancia RCS actual al repositorio Global. Utilice la función **Paquetes de configuración** para ayudar con la carga. Para más información, consulte [Carga del repositorio global de RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Hacia el futuro

Utilice los diseñadores visuales en RCS para los siguientes propósitos:

- Amplíe las plantillas proporcionadas por Microsoft.
- Cree nuevas configuraciones que requiera su organización.
- Personalice las funciones de globalización para la facturación electrónica y el servicio de cálculo de impuestos.

Utilice el repositorio de globalización para los siguientes propósitos:

- Acceda a las funciones de globalización y configuraciones producidas por Microsoft.
- Cargue las configuraciones que creó o extendió al repositorio global para el almacenamiento y compártalas en los entornos de aplicaciones de Dynamics 365 de su organización o con organizaciones externas. Para más información, consulte [Crear la configuración de ER en RCS y subirla al repositorio global](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>¿Significa este cambio que LCS no puede utilizarse como almacén central de configuraciones?

Sí. La funcionalidad que permite subir configuraciones a la biblioteca de activos del proyecto en LCS desde las aplicaciones de Finance and Operations se desactivará. Sin embargo, puede seguir utilizando el navegador en LCS para cargar configuraciones en la biblioteca de activos del proyecto según sus necesidades.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Pensé que RCS era un repositorio de reemplazo para importar archivos de plantillas globales. No pensé que se utilizara para almacenar configuraciones. ¿Cuál es la correcta?

RCS es un servicio de diseño para crear y editar configuraciones de ER. RCS tiene su propio repositorio que se conoce como el repositorio Global. Este repositorio se utiliza para almacenar las configuraciones que se crean en RCS. Una vez que el uso de LCS como almacenamiento quede obsoleto, el repositorio Global será la única fuente de configuraciones de Microsoft. Debe completar una acción única para importar todas las configuraciones que necesite de LCS a RCS y luego publicarlas desde RCS al repositorio Global.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Sin LCS, ¿cuál es la forma sugerida de almacenar las configuraciones para poder gestionar y transferir fácilmente las configuraciones de "prueba" y "producción"?

RCS utiliza el concepto de *aplicación conectada*. Una aplicación conectada forma una conexión entre RCS y cualquier instancia de las aplicaciones de Finance and Operations. Dado que RCS puede utilizarse para editar configuraciones, la aplicación conectada puede utilizarse para enviar las configuraciones directamente desde el diseñador a los entornos de aplicaciones de Finance and Operations. Por lo tanto, puede cambiar y probar rápidamente sus configuraciones en lugar de tener que pasar por el almacenamiento a nivel de proyecto de LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>¿Hay algún ejemplo que muestre la configuración y la gestión?

No hay ejemplos, pero puede completar los pasos anteriores en este tema para migrar sus configuraciones al repositorio RCS Global.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>¿Es RCS un requisito previo para configurar los informes electrónicos?

Sí. RCS incluye capacidades que admiten la configuración de funciones de globalización que utilizan los servicios de globalización, como la facturación electrónica y el servicio de cálculo de impuestos. Sin embargo, el servicio tiene la misma funcionalidad de diseñador visual que le permite ampliar o crear nuevas configuraciones de ER. RCS también proporciona gestión del ciclo de vida tanto para las configuraciones de ER como para las funciones de globalización.

### <a name="which-regions-can-rcs-be-deployed-in"></a>¿En qué regiones se puede implementar RCS?

RCS está disponible en las siguientes regiones de Azure:

- Estados Unidos
- India
- Francia
- Europa

Para obtener más información sobre el soporte del producto, consulte [Descripción general de los servicios de Dynamics Globalization](globalization-services-overview.md). Para obtener más información sobre la compatibilidad geográfica, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/rcs/D365Productavailabilityguide).

### <a name="whats-the-cost-of-using-rcs"></a>¿Cuál es el coste de usar RCS?

RCS y el repositorio de globalización se proporcionan de forma gratuita como parte de las licencias de aplicaciones existentes de Finance and Operations. No hay costos separados asociados con el uso del servicio de diseño RCS o con el almacenamiento de configuraciones en el repositorio global. Actualmente no hay límite en el número de configuraciones o aplicaciones conectadas.
