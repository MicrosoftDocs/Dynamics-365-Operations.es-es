---
title: Administrar el ciclo de vida de la configuración de los informes electrónicos (ER)
description: Este artículo describe cómo administrar el ciclo de vida de las configuraciones de informes electrónicos (ER) para la solución Dynamics 365 Finance.
author: NickSelin
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6a64908a167c09089a95f1d3faa825dcc63f064
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109094"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Administrar el ciclo de vida de la configuración de los informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Este artículo describe cómo administrar el ciclo de vida de las configuraciones de informes electrónicos (ER) para la solución Dynamics 365 Finance.

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

Puede individualmente [importar](tasks/er-import-configuration-lifecycle-services.md) diferentes [versiones](general-electronic-reporting.md#component-versioning) de una [configuración](general-electronic-reporting.md#Configuration) de ER a su instancia de Finance. Cuando se importa una nueva versión de una configuración de ER, el sistema controla el contenido de la versión preliminar de esta configuración:

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

## <a name="additional-resources"></a>Recursos adicionales

[Información general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Definir la dependencia que tienen las configuraciones de informes electrónicos de otros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

