---
title: Información general de la fusión de infraestructura de Dynamics 365 Human Resources
description: Este artículo describe la fusión de infraestructura de Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e68b28bfde35b51605aa0b653265da6261b69a90
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819252"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Fusión de infraestructura de Dynamics 365 Human Resources 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Human Resources 365

Microsoft Dynamics 365 Human Resources proporciona herramientas que ayudan a los equipos de recursos humanos a aumentar la agilidad organizacional, transformar la experiencia de los empleados y optimizar los programas de recursos humanos para crear un lugar de trabajo donde las personas y la empresa puedan prosperar. Para obtener más información acerca de Dynamics 365 Human Resources, consulte [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transforme la experiencia de los empleados.** Retenga a los mejores trabajadores capacitando a los gerentes y empleados a través de experiencias de autoservicio conectadas que impulsan el compromiso y el crecimiento.
- **Optimice los programas de recursos humanos.** Ayude a reducir los costes operativos y cree programas de administración de bajas y ausencias, tiempo, beneficios y compensaciones centrados en las personas.
- **Aumente la agilidad de la organización.** Permita que RR. HH. opere con la destreza que requiere el negocio mediante el uso de Dataverse y Microsoft Power Platform para centralizar los datos de las personas y ampliar fácilmente Dynamics 365 Human Resources.
- **Obtenga conocimientos de los recursos.** Tome decisiones basadas en datos a través de la capacidad de analizar y visualizar datos de personas en paneles enriquecidos que están disponibles en cualquier dispositivo.

## <a name="human-resources-infrastructure-merge"></a>Fusión de la infraestructura de Human Resources

Dynamics 365 Human Resources es una aplicación independiente que utiliza actualmente una infraestructura diferente a la de otras aplicaciones de finanzas y operaciones, como Dynamics 365 Finance o Dynamics 365 Supply Chain Management. La fusión de infraestructura introduce Dynamics 365 Human Resources en la misma infraestructura que otras aplicaciones de finanzas y operaciones.

Para obtener más información sobre la combinación de infraestructuras de Human Resources, consulte [Fusión de ofertas de recursos humanos](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Para obtener respuestas a las preguntas más frecuentes, consulte [Preguntas frecuentes sobre la fusión de la infraestructura de Human Resources](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Migración de clientes y fusión de clientes

En la fusión de infraestructuras, todas las capacidades de la aplicación de Human Resources están disponibles en los entornos de finanzas y operaciones. Los clientes pueden migrar sus entornos de Human Resources utilizando las herramientas de migración que están disponibles en Microsoft Dynamics Lifecycle Services. Opcionalmente, también pueden fusionar sus datos con su entorno financiero y de operaciones ya existente. 

La migración de clientes y la fusión de clientes difieren de la siguiente manera:

- **Migración de clientes**: las herramientas de migración automatizada se utilizan para realizar una "migración mediante lift-and-shift" (movimiento) de la base de datos del cliente desde la infraestructura de Human Resources a la infraestructura de finanzas y operaciones. El resultado es un nuevo entorno de finanzas y operaciones que utiliza la base de datos de Human Resources del cliente. 
- **Fusión de clientes**: Microsoft no requiere este paso adicional. Se hace a discreción del cliente y en la propia escala de tiempo del cliente. Durante este paso, los datos del cliente se trasladan a un entorno ya existente, como un entorno de Finance o Project Operations. Es en su mayoría manual y se puede hacer mediante el uso de entidades de datos del marco de administración de datos (DMF). 

## <a name="planning-a-human-resources-environment-migration"></a>Planificación de una migración de un entorno de Human Resources

Como parte de la fusión de la infraestructura, todos los clientes deberán migrar sus entornos de Human Resources desde la infraestructura independiente. Para ayudar en este proceso, le recomendamos que utilice las herramientas de migración automatizada de Lifecycle Services para mover sus entornos actuales a la nueva infraestructura. 

Las siguientes secciones brindan más detalles sobre cómo usar las herramientas de Lifecycle Services para migrar un entorno de Human Resources independiente. 

Los clientes que planean una migración pueden tener las siguientes expectativas:

- Todos los clientes deberán migrar un entorno de espacio aislado antes de migrar el entorno de producción. 
- Las herramientas de migración solo permiten la migración de espacio aislado a espacio aislado y la de producción a producción. Por lo tanto, su tipo de entorno determinará qué entorno se puede migrar adecuadamente. 
- Los clientes pueden migrar tantos espacios aislados como sean necesarios antes de migrar su entorno de producción, siempre que haya disponible un espacio de espacio aislado de destino. Los clientes también pueden eliminar un espacio aislado migrado y volver a migrar varias veces. 
- Si falla una migración de espacio aislado o si desea comenzar de nuevo, puede eliminar un entorno en la infraestructura de finanzas y operaciones y volver a migrar el mismo entorno.
- La URL de su entorno de Human Resources será diferente después de la migración.
- Planifique una cantidad adecuada de tiempo de inactividad para la migración del entorno de producción. El plazo estimado para completar el proceso de migración automatizado es de tres a cuatro horas. El plazo variará, según los datos de su organización. Debe validar la cantidad de tiempo que se requiere durante la migración de los entornos de espacio aislado y dejar tiempo para cualquier tarea manual adicional que deba completarse.

> [!IMPORTANT] 
> Cuando un entorno de producción se migra correctamente a la infraestructura de finanzas y operaciones, el entorno de producción independiente de origen se elimina automáticamente. No debe eliminar el entorno de producción migrado. 

El proceso de migración es en su mayoría automático. Sin embargo, sus usuarios empresariales deberán completar algunos pasos manuales y la validación después de la migración.

Se deben completar los siguientes pasos manuales:

- Crear un proyecto de Lifecycle Services nuevo para la migración.
- Revise cualquier integración de su antiguo entorno en el nuevo entorno apuntando la integración a la nueva URL/puntos de conexión, en función de cada configuración de integración.
- Actualice el almacén de datos para informes de Power BI incrustados.
- Actualice la lista de entidades de datos desde el área de trabajo DMF.
- Vincule Lifecycle Services para obtener ayuda.
- Cree calendarios fiscales.

Durante el proceso automático, las siguientes acciones se completan y deben validarse:

- Datos:

    - Configuraciones
    - Roles de seguridad (incluidos roles personalizados)
    - Flujos de trabajo (incluidas notificaciones)
    - Personalizaciones y vistas guardadas
    - Transacciones
    - Campos personalizados
    - Archivos adjuntos
    - Alertas

- Administración de datos: traer la propia base de datos (BYOD).
- Administración de características: características habilitadas o deshabilitadas.
- Power Apps incrustadas.
- Entorno asociado a un centro de administración de Power Platform (solo producción).
- Trabajos por lotes.
- Se crea un libro mayor vacío para cada entidad jurídica. Se establecen el tipo de cambio predeterminado y la divisa de contabilidad de cada libro mayor.
- Se crea automáticamente un nuevo plan de cuentas y se vincula a la página **Libro mayor** de cada entidad jurídica. Las dimensiones financieras que están configuradas en su entorno de Human Resources se agregarán automáticamente a una nueva estructura de cuenta y se vincularán al libro mayor. 

> [!NOTE]
> Se requiere un libro mayor en la infraestructura de finanzas y operaciones como parte del producto de Dynamics 365 Finance. El controlador de dimensiones personalizados que existía en la aplicación independiente de Dynamics 365 Human Resources no está disponible. La infraestructura fusionada de Human Resources depende de la lógica de finanzas para mostrar las dimensiones financieras en el módulo de **Human Resources**. Para obtener más información sobre el plan de cuentas y las dimensiones financieras, consulte [aquí](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Consideraciones

- La migración a los entornos siempre se realizará en la última versión generalmente disponible (GA). Según su plan de prueba y migración, si su validación de migración para entornos de espacio aislado estaba en una versión diferente, le recomendamos que valide una migración de espacio aislado en la misma versión que su entorno de producción. 
- Durante la migración, los entornos migrados se colocarán en la misma región que los entornos de Human Resources independientes de origen.

## <a name="licensing"></a>Licencias

No hay cambios en las licencias para Dynamics 365 Human Resources en las siguientes áreas: 

- **Requisito mínimo de compra de licencia**
- **Licencias para un entorno de producción y espacio aislado**: si tiene licencias independientes de Human Resources que otorgan un entorno de producción y un entorno de espacio aislado, la misma cantidad de licencias estará disponible en la infraestructura de finanzas y operaciones, sin coste adicional.
- **Licencias adicionales de espacio aislado**: si ha adquirido licencias de espacio aislado adicionales para la aplicación independiente de Human Resources, la misma cantidad de licencias de espacio aislado estará disponible para un entorno de prueba de aceptación estándar (espacio aislado) en la infraestructura de finanzas y operaciones, sin coste adicional. 
