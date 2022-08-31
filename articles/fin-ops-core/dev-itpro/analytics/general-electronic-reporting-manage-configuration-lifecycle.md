---
title: Administrar el ciclo de vida de la configuración de los informes electrónicos (ER)
description: Este artículo describe cómo administrar el ciclo de vida de las configuraciones de informes electrónicos (ER) para la solución Dynamics 365 Finance.
author: kfend
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 0209679c9882d87edab68d043fba9e7b3400a2a2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337203"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Administrar el ciclo de vida de la configuración de los informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Este artículo describe cómo administrar el ciclo de vida de las [configuraciones](general-electronic-reporting.md#Configuration) de [informes electrónicos](general-electronic-reporting.md) (ER) para la solución Dynamics 365 Finance.

## <a name="overview"></a>Información general

Informes electrónico (ER) es un motor que ofrece asistencia con documentos electrónicos específicos de país y necesarios reglamentarios. En general, ER asume la capacidad de realizar las actividades siguientes para un único documento electrónico. Para obtener más información, consulte [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md).

- Diseñar una plantilla para un documento electrónico:

    - Identificar los orígenes necesarios de datos que se pueden presentar en el documento:

        - Datos subyacentes, como tablas de datos, entidades de datos y clases.
        - Propiedades específicas de proceso, como fecha y tiempo de ejecución, y zona horaria.
        - Parámetros de entrada del usuario, especificados por el usuario final en el tiempo de ejecución.

    - Defina los elementos de documento necesarios y su topología para especificar un formato de documento final.
    - Configure el flujo deseado de datos de orígenes de datos seleccionados a los elementos de documentos definidos (mediante la vinculación de orígenes de datos a los componentes de formato de documento) y especifique la lógica del control del proceso.

- Haga que una plantilla esté disponible para que se pueda usar en otras instancias:

    - Transforme una plantilla de documento que se creó en una configuración de ER y exportar la configuración de la instancia actual de la aplicación como paquete XML que se puede almacenar de forma local o en Lifecycle Services (LCS).
    - Transforme una configuración de ER en una plantilla de documento de la aplicación.
    - Importe un paquete XML que se almacena de forma local o en LCS en la instancia.

- Personalizar la plantilla de un documento electrónico:

    - Lleve una plantilla de LCS a la instancia actual como configuración de ER.
    - Diseñe una versión personalizada de una configuración de ER y guarde una referencia a la versión de base.

- Integrar una plantilla con un proceso empresarial determinado, de manera que esté disponible en la aplicación:

    - Configure los parámetros de modo que la aplicación empiece a usar una configuración de ER, refiriéndose a esa configuración en un parámetro relacionado con procesos. Por ejemplo, consulte la configuración de ER en un método de pago Proveedores específico para generar un mensaje de pago electrónico para procesar facturas.

- Usar una plantilla en un proceso empresarial específico:

    - Permite ejecutar una configuración de ER en un proceso empresarial específico. Por ejemplo, para generar un mensaje de pago electrónico para procesar facturas cuando se selecciona un método de pago que hace referencia a la configuración de ER de pagos.

## <a name="concepts"></a>Conceptos
Los roles siguientes y las actividades relacionadas se asocian con el ciclo de vida de la configuración de ER.

| Función                                       | Actividades                                                      | Descripción |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consultor funcional de informes electrónicos | Permite crear y gestionar componentes de ER (modelos y formatos).           | Una persona de negocios que diseña modelos de datos específicos de dominio de ER, diseña las plantillas necesarias para documentos electrónicos y los vincula según corresponda. |
| Desarrollador de informes electrónicos             | Permite crear y administrar asignaciones de modelo de datos.                          | Un especialista que selecciona los orígenes de datos de Finance necesarios y los vincula a los modelos de datos específicos de dominio de ER. |
| Supervisor contable                      | Permite configurar los valores relacionados con proceso que hacen referencia a artefactos de ER. | Por ejemplo, un rol **Supervisor contable** que permite los ajustes de una configuración de ER para usarla en un método de pago Proveedores concreto para generar un mensaje de pago electrónico para procesar facturas. |
| Funcionario de pagos de proveedores            | Use artefactos de ER en un proceso empresarial específico.                | Por ejemplo, un rol **Funcionario de pagos de proveedores** que permite que los mensajes de pago electrónico se generan para procesar facturas, en función del formato de ER que se configura para un método de pago específico. |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desarrollo de la configuración de ER
Para los siguientes motivos relacionados con ER, se recomienda diseñar las configuraciones de ER en el entorno de desarrollo, como una instancia independiente de finanzas y operaciones:

- Los usuarios con los roles de **Desarrollador de notificación electrónica** o **Consultor de funciones de notificación electrónica** pueden editar las configuraciones y ejecutarlas con fines de prueba. Este escenario puede provocar llamadas de métodos de clases y de tablas que pueden dañar los datos empresariales y el rendimiento de la instancia.
- Las llamadas de métodos de clases y de tablas como orígenes de datos de ER de las configuraciones de ER no están restringidas por puntos de entrada y contenido registrado de la empresa. Por lo tanto, los usuarios con los roles de **Desarrollador de notificación electrónica** o **Consultor de funciones de notificación electrónica** pueden obtener acceso a los datos confidenciales de la empresa.

Las configuraciones de ER que se diseñan en el entorno de desarrollo se pueden [cargar](#data-persistence-consideration) en el entorno de prueba para la evaluación de la configuración (integración adecuada de proceso, corrección de resultados y rendimiento) y el control de calidad, como la corrección de los derechos de acceso del rol y la segregación de controles. Las características que permiten el intercambio de configuración de ER pueden usarse para este propósito. Las configuraciones de ER probadas se pueden cargar en LCS para compartirlas con los suscriptores del servicio o se pueden [importar](#data-persistence-consideration) al entorno de producción para el uso interno.

![Ciclo de vida de la configuración de ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Consideración de la persistencia de datos

Puede individualmente [importar](tasks/er-import-configuration-lifecycle-services.md) diferentes versiones de una [configuración](general-electronic-reporting.md#Configuration) de ER a su instancia de Finance. Cuando se importa una nueva versión de una configuración de ER, el sistema controla el contenido de la versión preliminar de esta configuración:

- Cuando la versión importada es inferior a la versión más alta de esta configuración en la instancia de Finance actual, el contenido de la versión preliminar de esta configuración permanece sin cambios.
- Cuando la versión importada es superior a cualquier otra versión de esta configuración en la instancia de Finance actual, el contenido de la versión importada se copia en la versión preliminar de esta configuración para permitirle continuar editando la última versión completa.

Si esta configuración es propiedad del [proveedor](general-electronic-reporting.md#Provider) de la configuración que está actualmente activada, la versión preliminar de esta configuración está visible para usted en la ficha desplegable **Versiones** de la página **Configuraciones** (**Administración de la organización** > **Informes electrónicos** > **Configuraciones**). Puede seleccionar la versión preliminar de la configuración y [modificar](er-quick-start2-customize-report.md#ConfigureDerivedFormat) su contenido utilizando el diseñador de ER relevante. Cuando haya editado la versión en borrador de una configuración de ER, su contenido ya no coincide con el contenido de la versión más alta de esta configuración en la instancia de Finance actual. Para evitar la pérdida de sus cambios, el sistema muestra un error de que la importación no puede continuar porque la versión de esta configuración es superior a la versión más alta de esta configuración en la instancia de Finance actual. Cuando esto sucede, por ejemplo con la configuración de formato **X**, se muestra el error de que la **versión de formato 'X' no está completa**.

Para deshacer los cambios que introdujo en la versión preliminar, seleccione la versión más alta completada o compartida de su configuración de ER en Finanzas en la ficha desplegable **Versiones** y, a continuación, seleccione la opción **Obtener esta versión**. El contenido de la versión seleccionada se copia a la versión preliminar.

## <a name="applicability-consideration"></a>Consideración de aplicabilidad

Cuando diseña una nueva versión de una configuración de ER, puede definir su [dependencia](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) en otros componentes de software. Este paso se considera un requisito previo para controlar la descarga desde la versión de esta configuración de un repositorio de ER o un archivo XML externo y para cualquier uso futuro de la versión. Cuando intenta importar una nueva versión de una configuración de ER, el sistema usa los requisitos previos configurados para controlar si la versión se puede importar.

En algunos casos, es posible que necesite que el sistema ignore los requisitos previos configurados cuando importe nuevas versiones de configuraciones de ER. Para que el sistema ignore los requisitos previos durante la importación, siga estos pasos.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Omitir actualizaciones de productos y comprobación de requisitos previos de la versión durante la importación** en **Sí**.

    > [!NOTE]
    > Este parámetro es específico del usuario y específico de la compañía.

## <a name="dependencies-on-other-components"></a>Dependencias de otros componentes

Las configuraciones de ER se pueden configurar como [dependientes](er-download-configurations-global-repo.md#import-filtered-configurations) de otras configuraciones. Por ejemplo, puede [importar](er-download-configurations-global-repo.md) una configuración de [modelo de datos](er-overview-components.md#data-model-component) de ER del repositorio global en sus [Microsoft Regulatory Configuration Services (RCS)](../../../finance/localizations/rcs-overview.md) o instancia de Dynamics 365 Finance y, a continuación, crear una nueva configuración de [formato](er-overview-components.md#format-component) de ER [derivada](er-quick-start2-customize-report.md#DeriveProvidedFormat) de la configuración del modelo de datos de ER importada. La configuración del formato de ER derivado dependerá de la configuración del modelo de datos de ER base.

![Configuración de formato ER derivada en la página Configuraciones.](./media/ger-configuration-lifecycle-img1.png)

Cuando haya terminado de diseñar el formato, puede cambiar el estado de su versión inicial de la configuración del formato ER de **Borrador** a **Terminado**. A continuación, puede compartir la versión completa de la configuración del formato ER [publicándola](../../../finance/localizations/rcs-global-repo-upload.md) en el repositorio global. A continuación, puede acceder al repositorio global desde cualquier instancia en la nube de RCS o Finance. Luego puede importar cualquier versión de configuración de ER que sea aplicable a la aplicación desde el repositorio global a esa aplicación.

![Configuración de formato ER publicada en la página Repositorio de configuración.](./media/ger-configuration-lifecycle-img2.png)

En función de la dependencia de la configuración, cuando selecciona la configuración del formato ER en el repositorio global para importarla a una instancia de RCS o Finance recientemente implementada, la configuración del modelo de datos base de ER se encuentra automáticamente en el repositorio global y se importa junto con el formato ER seleccionado. configuración como la configuración base.

También puede exportar su versión de configuración de formato ER fuera de su RCS actual o instancia de Finanzas y almacenarla localmente como un archivo XML.

![Exportación de una versión de la configuración de formato de ER como XML en la página Configuración.](./media/ger-configuration-lifecycle-img3.png)

En versiones de Finance **anteriores a la versión 10.0.29**, cuando intente importar la versión de configuración del formato de ER desde ese archivo XML o desde cualquier repositorio que no sea el repositorio global en una instancia de RCS o Finance recientemente implementada que aún no contiene ninguna configuración de ER, se generará la siguiente excepción para informar que no se puede obtener una configuración base:

> Referencias no resueltas restantes<br>
No se puede establecer la referencia del objeto '\<imported configuration name\>' a la "base" del objeto (\<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Importación de la versión de configuración del formato de ER en la página Repositorio de configuración.](./media/ger-configuration-lifecycle-img4.gif)

En la versión **10.0.29 y posteriores**, cuando intente realizar la misma importación de configuración, si no se puede encontrar una configuración base en la instancia de la aplicación actual o en el repositorio de origen que está utilizando actualmente (si corresponde), el marco de ER intentará encontrar automáticamente el nombre de la configuración base que falta en la memoria caché del repositorio global. A continuación, presentará el nombre y el identificador único global (GUID) de la configuración base que falta en el texto de la excepción que se genera.

> Referencias no resueltas restantes<br>
No se puede establecer la referencia del objeto '\<imported configuration name\>' a la "base" del objeto (\<name of the missed base configuration\> \<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Excepción en la página del repositorio de configuración cuando no se puede encontrar la configuración base.](./media/ger-configuration-lifecycle-img5.png)

Puede usar el nombre provisto para encontrar la configuración base y luego importarla manualmente.

> [!NOTE]
> Esta nueva opción funciona solo cuando al menos un usuario ya ha iniciado sesión en el repositorio global mediante la página [Repositorios de configuración](er-download-configurations-global-repo.md#open-configurations-repository) o uno de los campos de [búsqueda](er-extended-format-lookup.md) del repositorio global en la instancia de Finance actual y cuando el contenido del repositorio global se ha almacenado en caché.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Definir la dependencia que tienen las configuraciones de informes electrónicos de otros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

