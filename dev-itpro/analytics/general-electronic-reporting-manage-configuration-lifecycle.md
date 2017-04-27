---
title: "Administrar el ciclo de vida de las configuraciones de la notificación electrónica"
description: "En este tema se describe cómo administrar el ciclo de vida de las configuraciones de informes electrónicos (ER) para la solución de Microsoft Dynamics 365 for Operations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Administrar el ciclo de vida de las configuraciones de la notificación electrónica

[!include[banner](../includes/banner.md)]


En este tema se describe cómo administrar el ciclo de vida de las configuraciones de informes electrónicos (ER) para la solución de Microsoft Dynamics 365 for Operations.

<a name="overview"></a>Visión general
--------

El Informe electrónico (ER) es un motor que ofrece asistencia con documentos electrónicos reglamentarios y específicos del país en Microsoft Dynamics 365 for Operations. En general, ER asume la capacidad de realizar las actividades siguientes para un único documento electrónico. Para obtener más información, consulte [Visión general de los informes electrónicos](general-electronic-reporting.md).

-   Diseñar una plantilla para un documento electrónico:
    -   Identificar los orígenes necesarios de datos que se pueden presentar en el documento:
        -   Datos subyacentes de Dynamics 365 for Operations, como tablas de datos, entidades de datos y clases.
        -   Propiedades específicas de proceso, como fecha y tiempo de ejecución, y zona horaria.
        -   Parámetros de entrada del usuario, especificados por el usuario final en el tiempo de ejecución.
    -   Defina los elementos de documento necesarios y su topología para especificar un formato de documento final.
    -   Configure el flujo deseado de datos de orígenes de datos seleccionados a los elementos de documentos definidos (mediante la vinculación de orígenes de datos a los componentes de formato de documento) y especifique la lógica del control del proceso.
-   Haga que una plantilla esté disponible para que se pueda usar en otras instancias de Dynamics 365 for Operations:
    -   Transforme una plantilla de documento que se creó en Dynamics 365 for Operations en una configuración de ER y exporte la configuración de la instancia actual de Dynamics 365 for Operations como paquete XML que se puede almacenar de forma local o en LCS.
    -   Transforme una configuración de ER en una plantilla de documento de Dynamics 365 for Operations.
    -   Importe un paquete XML que se almacena de forma local o en LCS en la instancia de Dynamics 365 for Operations actual.
-   Personalizar la plantilla de un documento electrónico:
    -   Lleve una plantilla de LCS a la instancia de Dynamics 365 for Operations actual como configuración de ER.
    -   Diseñe una versión personalizada de una configuración de ER y guarde una referencia a la versión de base.
-   Integre una plantilla con un proceso empresarial determinado, de manera que esté disponible en Dynamics 365 for Operations:
    -   Configure los parámetros de modo que Dynamics 365 for Operations empiece a usar una configuración de ER, refiriéndose a esa configuración en un parámetro relacionado con procesos. Por ejemplo, consulte la configuración de ER en un método de pago Proveedores específico para generar un mensaje de pago electrónico para procesar facturas.
-   Usar una plantilla en un proceso empresarial específico:
    -   Permite ejecutar una configuración de ER en un proceso empresarial específico. Por ejemplo, para generar un mensaje de pago electrónico para procesar facturas cuando se selecciona un método de pago que hace referencia a la configuración de ER de pagos.

## <a name="concepts"></a>Conceptos
Los roles siguientes y las actividades relacionadas se asocian con el ciclo de vida de la configuración de ER.

| Función                                       | Actividades                                                      | Descripción                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consultor funcional de informes electrónicos | Permite crear y gestionar componentes de ER (modelos y formatos).           | Una persona de negocios que diseña modelos de datos específicos de dominio de ER, diseña las plantillas necesarias para documentos electrónicos y los vincula según corresponda.                                                                           |
| Desarrollador de informes electrónicos             | Permite crear y administrar asignaciones de modelo de datos.                          | Un especialista de Dynamics 365 for Operations que selecciona los orígenes de datos de Dynamics 365 for Operations necesarios y los vincula a los modelos de datos específicos de dominio de ER.                                                                 |
| Supervisor contable                      | Permite configurar los valores relacionados con proceso que hacen referencia a artefactos de ER. | Por ejemplo, un rol **Supervisor contable** que permite los ajustes de una configuración de ER para usarla en un método de pago Proveedores concreto para generar un mensaje de pago electrónico para procesar facturas. |
| Funcionario de pagos de proveedores            | Use artefactos de ER en un proceso empresarial específico.                | Por ejemplo, un rol **Funcionario de pagos de proveedores** que permite que los mensajes de pago electrónico se generan para procesar facturas, en función del formato de ER que se configura para un método de pago específico.           |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desarrollo de la configuración de ER
Para los siguientes motivos relacionados con ER, se recomienda diseñar las configuraciones de ER en el entorno de desarrollo, como una instancia independiente de Dynamics 365 for Operations:

-   Los usuarios con los roles de **Desarrollador de notificación electrónica** o **Consultor de funciones de notificación electrónica** pueden editar las configuraciones y ejecutarlas con fines de prueba. Este escenario puede provocar llamadas de métodos de clases y de tablas que pueden dañar los datos empresariales y el rendimiento de la instancia de Dynamics 365 for Operations.
-   Las llamadas de métodos de clases y de tablas como orígenes de datos de ER de las configuraciones de ER no están restringidas por puntos de entrada de Dynamics 365 for Operations ni por el contenido registrado de la empresa. Por lo tanto, los usuarios con los roles de **Desarrollador de notificación electrónica** o **Consultor de funciones de notificación electrónica** pueden obtener acceso a los datos confidenciales de la empresa.

Las configuraciones de ER que se diseñan en el entorno de desarrollo se pueden cargar en el entorno de prueba para la evaluación de la configuración (integración adecuada de proceso, corrección de resultados y rendimiento) y el control de calidad, como la corrección de los derechos de acceso del rol y la segregación de controles. Las características que permiten el intercambio de configuración de ER pueden usarse para este propósito. Finalmente, las configuraciones de ER probadas se pueden cargar al LCS, donde se pueden compartir con los suscriptores del servicio o al entorno de producción para el uso interno, tal como se muestran en la siguiente ilustración. ![Ciclo de vida de la configuración de ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Consulte también
--------

[Visión general de los informes electrónicos](general-electronic-reporting.md)




