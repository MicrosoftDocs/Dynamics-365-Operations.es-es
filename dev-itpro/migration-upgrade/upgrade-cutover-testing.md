---
title: "Prueba de transferencia tras actualización"
description: "Este tema explica cómo probar las tareas que aparecen después de que apague AX 2012 pero antes de que active Dynamics 365 for Finance and Operations, Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: es-es
ms.lasthandoff: 06/15/2017

---

# Prueba de transferencia de sistema tras la actualización
<a id="upgrade-cutover-testing" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Transferencia de sistema* es el término usamos para el proceso final de poner en funcionamiento un nuevo sistema. Este proceso de transferencia de sistema está compuesto de las tareas que aparecen después de desactivar Microsoft Dynamics AX 2012 y antes de que se active Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. El propósito de la prueba de la transferencia de sistema de la actualización es practicar el proceso de transferencia de sistema, para ayudar a garantizar una experiencia suave para todo el mundo implicado durante la transferencia de sistema para empezar a funcionar.

Existen dos secuencias de trabajo principales durante una transferencia de sistema:

- **Secuencia de trabajo técnico**: esta secuencia de trabajo incluye el proceso de ejecución de la actualización de datos. Su empresa impondrá un límite de tiempo de inactividad permitido. Durante este tiempo de inactividad, ni AX 2012 ni Finance and Operations estarán disponibles. Es posible que esta secuencia de trabajo tenga que ajustar el procedimiento de actualización de datos para cumplir el límite de tiempo de inactividad de la empresa.
- **Secuencia de trabajo funcional**: esta secuencia de trabajo incluye las tareas de configuración que se realizan después de completar la actualización de datos. Todas estas tareas deben ser documentadas y cuantificadas, y debe asignarse un recurso, ya que la secuencia de trabajo funcional y la de trabajo técnico deben caber en el límite de tiempo de inactividad de la empresa.

La ilustración siguiente muestra el proceso general para que la transferencia de sistema funcione como aparecerá en el entorno de producción.

![Proceso de transferencia de sistema](./media/cutover_1.png)

Este proceso de transferencia de sistema se diferencia de una actualización de datos básica en un entorno de espacio aislado de las siguientes formas:

- La base de datos de AX 2012 no se copia, únicamente se hace una copia de seguridad y, a continuación, la base de datos original se modifica. Este planteamiento es más rápido, y la copia de seguridad proporciona la posibilidad de recuperación, si se necesita volver atrás.
- Dado que el entorno de producción para Finance and Operations restringe el acceso, las tareas que se han ejecutado anteriormente en la instancia de espacio aislado de Application Object Server (AOS) son ahora realizadas por el equipo de Microsoft DSE. Estas tareas incluyen la descarga e importación del archivo de bacpac, y la ejecución del paquete MajorversionDataUpgrade.zip.
- Hemos añadido las tareas siguientes:

    - Realizar una prueba de humo.
    - Realizar las tareas de configuración de la aplicación. Este paso puede ser grande, según la funcionalidad que se usa. Durante este paso, el equipo funcional configura nuevas funciones de la aplicación de modo que esté lista para usarse en el sistema actualizado.
    - Permitir volver a acceder a los usuarios. Notifique a la base de usuarios que la actualización está completa y que pueden utilizar el sistema de nuevo.

## Secuencia de trabajo técnico
<a id="technical-workstream" class="xliff"></a>

La secuencia de trabajo técnico implica a varios miembros del equipo técnico: el administrador de la base de datos (DBA), el administrador del sistema AX 2012, administradores de servidor, y los desarrolladores que están familiarizados con AX 2012 y con Finance and Operations. Este tema explicará qué tareas implican a qué roles.

Durante la prueba de transferencia de sistema, el equipo técnico está centrado en la prueba de rendimiento y fiabilidad del proceso de actualización de datos, para asegurarse de que cumpla con el límite de tiempo de inactividad de la empresa. Muchos elementos de hardware y de software están involucradas en este proceso. Algunos de estos elementos son locales, mientras que otros se encuentran en la nube de Microsoft. Además, muchos elementos de código de aplicación personalizado y de código estándar están implicados. El resultado de esta prueba debe ser tener confianza en el proceso de transferencia de sistema para su entorno.

### Desactivar instancias de AOS de AX 2012
<a id="turn-off-the-ax-2012-aos-instances" class="xliff"></a>

Esta tarea implica al administrador del sistema AX 2012 y a los administradores del servidor.

Se deben validar las siguientes áreas:

- **Trabajos por lotes que se están ejecutando en el momento de la transferencia del sistema**: un trabajo por lotes de larga ejecución que ya se empezó a ejecutarse impedirá que el sistema se detenga. Planifique con tiempo, de modo que pueda detener las instancias de AOS en el momento deseado. Es posible que tenga que programar los lotes para que se completen antes de que apagar el AX 2012.
- **Sistemas integrados**: puede tener otros sistemas integrados con el entorno de AX 2012. Debe tener cuenta estos sistemas en el plan para desactivar AX 2012. Por ejemplo, puede que tenga que apagar los sistemas integrados antes de apagar el propio AX 2012, de modo que cualquier transacción pendiente se pueda completar. Los requisitos para sistemas integrados varían enormemente de una empresa a otra. Por lo tanto, su equipo de expertos debe planificar este escenario de forma independiente.

### Cree una copia de seguridad de la base de datos de AX 2012.
<a id="create-a-backup-of-the-ax-2012-database" class="xliff"></a>

Esta tarea implica al DBA. La copia de seguridad se utilizará si se requiere una regresión. También se usará como punto de referencia que debe retenerse por un período y mostrar el estado del sistema en el momento de la transferencia de sistema.

Se deben validar las siguientes áreas:

- Conozca los plazos de tiempo concretos para el proceso de copia de seguridad.
- Ajuste las opciones de seguridad que se utilizan (por ejemplo, con compresión o sin compresión), para ayudar a garantizar la copia de seguridad más rápida posible.

### Exporte la base de datos a bacpac
<a id="export-the-database-to-bacpac" class="xliff"></a>

Esta tarea implica al DBA. El resultado de esta tarea es el archivo de exportación que se cargará en Microsoft Azure para el nuevo sistema.

Se deben validar las siguientes áreas:

- Conozca los plazos de tiempo concretos para el proceso de copia de seguridad.
- Optimice el proceso de exportación para ayudar a garantizar la experiencia más rápida posible. La optimización puede requerir las siguientes tareas:

    - Medir recursos del sistema durante la exportación, como CPU, E/S de disco y memoria.
    - Si se encuentran cuellos de botella de recursos, cree un plan para mitigarlos. Normalmente, se mitigarán estos cuellos de botella asignando más recursos.

### Cargar el archivo bacpac al almacenamiento de Azure.
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

Esta tarea implica al DBA o a los administradores del servidor. Durante la tarea, el archivo bacpac se traslada a Azure.

Se deben validar las siguientes áreas:

- Seleccione el equipo que se usará para la carga, y asegúrese de que la herramienta del explorador de Azure Storage está configurada y preparada para su uso.
- Obtenga los controles de tiempo concretos para el proceso de carga midiéndolo varias veces. Los tiempos de carga variarán en función de la velocidad de su conexión a Internet y de la ubicación geográfica del centro de datos de Azure en relación con su ubicación.

### Descargue e importe el archivo bacpac a la base de datos Azure SQL.
<a id="download-and-import-the-bacpac-file-to-the-azure-sql-database" class="xliff"></a>

Cuando esta tarea aparece durante el lanzamiento, la realiza el equipo de Microsoft DSE. Sin embargo, durante la prueba de la transferencia de sistema, implica al DBA. El resultado de esta tarea es el archivo de exportación que se cargará en Azure para el nuevo sistema.

Se deben validar las siguientes áreas:

- Conozca los plazos de tiempo concretos para el proceso de importación.
- Optimice el proceso de exportación para ayudar a garantizar la experiencia más rápida posible. La optimización puede requerir las siguientes tareas:

    - Mida los recursos del sistema durante la exportación. A continuación se incluyen algunos ejemplos:

        - **En el equipo de AOS:** CPU, E/S de disco y memoria
        - **En la instancia de la base de datos Azure SQL:** rendimiento de la base de datos SQL (DTU). Puede controlar el DTU de Azure SQL desde Microsoft SQL Server Management Studio en el equipo de AOS mirando la vista de sistema de sys.dm_resource_stats.

    - Si se encuentran cuellos de botella de recursos, cree un plan para mitigarlos. Normalmente, se mitigarán estos cuellos de botella asignando más recursos. Dado que este equipo está alojado en Microsoft, debe enviar una solicitud a Microsoft para aumentar los recursos si identifica que son un cuello de botella.

### Ejecute el paquete MajorVersiondataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

Cuando esta tarea aparece durante el lanzamiento, la realiza el equipo de Microsoft DSE. Sin embargo, durante la prueba de la transferencia de sistema, implica a los desarrolladores. Durante esta tarea, la antigua estructura de la base de datos se transforma a la estructura del nuevo sistema.

El proceso de sincronización de la base de datos se ejecuta como parte de este tarea. La sincronización de la base de datos puede llevar una cantidad de tiempo significativa en algunos casos, como cuando un índice de clúster ha cambiado en una tabla, porque esta operación es una operación cara en SQL.

Se recomienda que primero realice su análisis y proceso de depuración en un entorno de desarrollo. En un entorno de espacio aislado, las opciones de depuración y de análisis están más limitadas. El objetivo es tener pocos o ningún problema que se deba solucionar al hacer la prueba de transferencia de sistema.

Se deben validar las siguientes áreas:

- Conozca los plazos de tiempo concretos para el proceso de importación.
- Optimice el proceso para ayudar a garantizar la experiencia más rápida. La optimización puede requerir las siguientes tareas:

    - Controle el rendimiento de los scripts de actualización individuales a través de la tabla ReleaseUpdateScriptsExecution.
    - Ajuste los scripts para optimizar el rendimiento. Esta tarea puede requerir que personalice el código X++ del script para optimizarlo para su conjunto de datos.
    - Supervise el DTU de Azure SQL mediante la supervisión de Microsoft Dynamics Lifecycle Services (LCS) o la vista de sistema de sys.dm_resources_stats en Management Studio. Si los recursos están al límite, puede que tenga que solicitar un mayor nivel de base de datos al equipo de Microsoft DSE.

### Regresión a AX 2012
<a id="roll-back-to-ax-2012" class="xliff"></a>

El objetivo de este tarea es restablecer la base de datos mediante la copia de seguridad que se realizó al desactivar AX 2012 y después volver a activar AX 2012. También puede ser necesario restablecer el estado de los sistemas integrados. Sin embargo, dado que los sistemas integrados varían de una empresa a otra, debe planificar este escenario independientemente, en función de las circunstancias específicas. Aunque sea poco probable que tenga que hacer una regresión, es muy importante que tenga un proceso probado en caso de que lo necesite.

## Secuencia de trabajo funcional
<a id="functional-workstream" class="xliff"></a>

Tras la actualización de datos, se requerirán diversas tareas de configuración en el nuevo entorno. El objetivo de esta secuencia de trabajo es documentar y cuantificar todas las tareas de configuración y asignar un recurso a cada tarea para ayudar a garantizar que estas tareas se puedan realizar junto con la secuencia de trabajo técnico durante la ventana de tiempo de inactividad.

Normalmente, las tareas funcionales implican cambiar la configuración de parámetros específicos del sistema u otros datos de configuración. Estas tareas se identifican a través de la aprobación de la prueba funcional completa, que es una actividad independiente de la prueba de transferencia de sistema. Cuando una tarea de este tipo se identifica, debe revisarse junto con el recurso funcional y su desarrollador.

Cambios grandes pueden requerir la escritura de un nuevo script de actualización de datos personalizado para actualizar los datos durante el proceso de actualización de datos. Sin embargo, el recurso funcional puede ejecutar manualmente cambios más pequeños a través del nuevo sistema tras la actualización de datos.

Los cambios grandes que tienen nuevos scripts de actualización de datos deben someterse a prueba. Por lo tanto, una o más iteraciones adicionales del paquete MajorVersionDataUpgrade.zip tendrán que ejecutarse. Es importante que sopese el coste de ejecutar de nuevo el paquete con el coste de la entrada manual de datos.

Para cada cambio manual, debe agregarse una tarea al documento de plan de transferencia de sistema. Esta tarea debe mostrar los detalles siguientes:

-   ¿Qué es la tarea, y qué debe hacer?
-   ¿Quién debe hacerla?
-   ¿Cuánto tiempo tarda?

