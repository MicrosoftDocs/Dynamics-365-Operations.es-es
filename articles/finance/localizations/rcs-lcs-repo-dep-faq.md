---
title: 'Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)'
description: Este tema proporciona información sobre la eliminación del almacenamiento de Microsoft Dynamics Lifecycle Services (LCS) que está prevista como parte del despliegue del repositorio global de Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
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
ms.openlocfilehash: abaeb34db1d209fa8e5cc83a98c333f42e91f2d2
ms.sourcegitcommit: 7cda434becd198c1cd405e001289777ae7a24fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6127928"
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

- Puede utilizar RCS para crear y editar configuraciones. A continuación, puede enviar esas configuraciones directamente desde el diseñador a una aplicación conectada. Por lo tanto, puede cambiar y probar rápidamente sus configuraciones.
- El repositorio Global es el almacenamiento centralizado de todas las configuraciones de ER.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Orientación para acciones puntuales y continuas

Esta sección describe un conjunto de pasos que deben completarse una vez. También describe los pasos que deben completarse de forma continua después.

### <a name="one-time-action"></a>Acción única

Importe todas las configuraciones requeridas desde LCS a RCS, y luego publíquelas desde RCS al repositorio Global. Si está utilizando bibliotecas de activos específicas del proyecto para almacenar configuraciones derivadas en LCS, los siguientes pasos deben completarse mientras LCS sigue siendo accesible.

1. Si una instancia de RCS no está ya disponible, aprovisione una. Para más información, consulte [la descripción general de RCS](rcs-overview.md).
2. En la instancia de RCS aprovisionada, para cada proyecto LCS en la biblioteca de activos que incluye configuraciones ER derivadas, registre el repositorio LCS apropiado.
3. Importe las configuraciones ER de los repositorios LCS a RCS. Para más información, consulte [Importar configuraciones desde LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Si el repositorio Global no se proporciona automáticamente, regístrelo en RCS.
5. Suba todas las configuraciones derivadas de la instancia RCS actual al repositorio Global. Utilice los **paquetes de configuración que permiten al usuario cargar todas las configuraciones a GR en una sola operación** para ayudar a la carga. Para más información, consulte [Carga del repositorio global de RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Hacia el futuro

Utilice los diseñadores visuales en RCS para crear todas las nuevas configuraciones. A continuación, cargue las configuraciones en el repositorio global para su almacenamiento. Para más información, consulte [Crear la configuración de ER en RCS y subirla al repositorio global](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>¿Significa este cambio que LCS no puede utilizarse como almacén central de configuraciones?

Sí. La funcionalidad que permite subir configuraciones a la biblioteca de activos del proyecto en LCS desde las aplicaciones de Finance and Operations se desactivará. Sin embargo, puede seguir utilizando el navegador en LCS para cargar configuraciones en la biblioteca de activos del proyecto según sus necesidades.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Pensé que RCS era un repositorio de reemplazo para importar archivos de plantillas globales. No pensé que se utilizara para almacenar configuraciones. ¿Cuál es la correcta?

RCS es un servicio de diseño para crear y editar configuraciones de ER. RCS tiene su propio repositorio que se conoce como el repositorio Global. Este repositorio se utiliza para almacenar las configuraciones que se crean en RCS. Una vez que el uso de LCS como almacenamiento quede obsoleto, el repositorio Global será la única fuente de configuraciones de Microsoft. Debe completar una acción única para importar todas las configuraciones que necesite de LCS a RCS y luego publicarlas desde RCS al repositorio Global.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Sin LCS, ¿cuál es la forma sugerida de almacenar las configuraciones para poder gestionar y transferir fácilmente las configuraciones de "prueba" y "producción"?

RCS utiliza el concepto de *aplicación conectada*. Una aplicación conectada forma una conexión entre RCS y cualquier instancia de las aplicaciones de Finance and Operations. Dado que RCS puede utilizarse para editar configuraciones, la aplicación conectada puede utilizarse para enviar las configuraciones directamente desde el diseñador a los entornos de aplicaciones de Finance and Operations. Por lo tanto, puede cambiar y probar rápidamente sus configuraciones en lugar de tener que pasar por el almacenamiento a nivel de proyecto de LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>¿Hay algún ejemplo que muestre la configuración y la gestión?

No hay ejemplos, pero puede completar los pasos anteriores en este tema para migrar sus configuraciones al repositorio RCS Global.
