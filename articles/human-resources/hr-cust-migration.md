---
title: Migración de clientes de Dynamics 365 Human Resources a la infraestructura de finanzas y operaciones
description: Este artículo describe la migración de clientes de Microsoft Dynamics 365 Human Resources a la infraestructura de finanzas y operaciones.
author: twheeloc
ms.date: 10/25/2022
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
ms.openlocfilehash: 4df9a68ea0128378224bf77bd66423fd2e13fa55
ms.sourcegitcommit: e5b290bac7e8f468167caa1a5607aac6eac9aaea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760372"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Migración de clientes de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

La migración de clientes es una "migración mediante lift-and-shift" (movimiento) de una base de datos de clientes a la infraestructura financiera y de operaciones. Para ello se utilizan herramientas de migración automatizada. El resultado es un nuevo entorno de finanzas y operaciones que utiliza la base de datos de Human Resources del cliente.

## <a name="prerequisites"></a>Requisitos previos

### <a name="user-access-and-permissions"></a>Acceso y permisos de usuario

- El usuario de Microsoft Dynamics Lifecycle Services debe tener el rol de **Administrador de la organización**.
- El usuario debe ser capaz de [crear proyectos de Azure DevOps](/azure/devops/organizations/projects/create-project) o utilizar uno de Azure DevOps ya existente.
- El usuario debe tener acceso a [crear un token de seguridad de acceso personal de Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) o debe tener un token que esté disponible para usarlo.

### <a name="dataverse-environment-backup-sandbox"></a>Copia de seguridad del entorno de Dataverse (espacio aislado)

 - Opcional pero recomendado: actualice el entorno de espacio aislado de Human Resources ya existente utilizando una copia del entorno de producción de Human Resources.
 - Cree un entorno de Dataverse usando el centro de administración de Power Platform.
 - Copie el entorno de Dataverse existente, que está vinculado a la aplicación de Human Resources independiente, al entorno que creó en el paso anterior.

> [!NOTE]
> Cuando agregue una base de datos, asegúrese de que la opción **Habilitar aplicaciones de Dynamics 365** esté configurada en **Sí**. Para obtener información detallada, consulte [Preparar un entorno de Power Platform](hr-cust-migration.md#prepare-a-power-platform-environment)

### <a name="dataverse-capacity"></a>Capacidad de Dataverse

1. Utilice la página **Resumen** del centro de administración de Power Platform para verificar que el [almacenamiento de Dataverse](/power-platform/admin/finance-operations-storage-capacity) tenga suficiente capacidad disponible para la copia del entorno.
2. Si no hay suficiente capacidad disponible, use la [guía para liberar espacio de almacenamiento](/power-platform/admin/free-storage-space) para reducir el consumo total. Los clientes también pueden [agregar capacidad de almacenamiento adicional](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Proceso de migración de clientes

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Crear un proyecto de Lifecycle Services para la migración de Human Resources

El primer paso es crear un nuevo proyecto de implementación de finanzas y operaciones en Lifecycle Services. El cliente tendrá un proyecto ya existente de Lifecycle Services para Human Resources. Los entornos de Human Resources ya existentes se migrarán al nuevo proyecto de implementación de finanzas y operaciones.

Para crear un proyecto nuevo, siga estos pasos.

1. Inicie sesión en Lifecycle Services como administrador global o usuario de la cuenta de servicio designado.
2. En la página principal de Lifecycle Services, seleccione **Crear/nuevo (+)**.
3. Seleccione aplicaciones de finanzas y operaciones como producto.
4. En el campo **Objetivo del proyecto**, seleccione **Implementación**.
5. Escriba el nombre y la descripción de un proyecto.
6. En el campo **Tipo personalizado de proyecto**, seleccione **Migración de Microsoft Dynamics 365 Human Resources**.
7. Seleccione la casilla de verificación para aceptar los términos y condiciones.
8. Seleccione **Crear**.

Una vez que haya creado un nuevo proyecto de Lifecycle Services, siga estos pasos para instalarlo y configurarlo.

1. Seleccione **Incorporación de proyecto** para completar la incorporación del proyecto. Para obtener más información, consulte [Incorporación de proyecto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Seleccione la misma región que sus entornos actuales. Esta selección no afectará la migración.
    - Para sistemas heredados, seleccione **Otros**.

2. Complete la configuración del proyecto. Como parte de este paso, debe configurar la biblioteca en línea de SharePoint, además de conexiones de Azure y Azure DevOps si son necesarias. Para obtener más información, consulte [Manual del usuario de Lifecycle Services (LCS)](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> Los clientes pueden utilizar un proyecto de Azure DevOps ya existente y el token de seguridad de acceso personal asociado. Si se utiliza un proyecto ya existente, las configuraciones que están relacionadas con el proyecto están disponibles automáticamente y se pueden revisar para verificar su precisión.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migrar un entorno de espacio aislado de Human Resources

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Prepararse para migrar el entorno de espacio aislado

Una vez que se haya creado un nuevo proyecto de Lifecycle Services y se haya completado el proceso de incorporación del proyecto, estará listo para migrar su primer entorno. Antes de comenzar este proceso, le recomendamos que actualice el entorno de espacio aislado que desea migrar desde su entorno de producción en la infraestructura independiente.

#### <a name="prepare-a-power-platform-environment"></a>Preparar un entorno de Power Platform

> [!NOTE]
> Este paso solo se aplica a la migración del entorno de espacio aislado. Cuando migra el entorno de producción, el entorno del centro de administración de Power Platform ya existente que está asociado al entorno de producción se transferirá. Cuando agregue una base de datos, asegúrese de que el botón **Habilitar aplicaciones de Dynamics 365** esté configurado en **Sí**. 

- En el centro de administración de Power Platform, [cree un entorno con una base de datos](/power-platform/admin/create-environment#create-an-environment-with-a-database) para usarlo para la migración del espacio aislado, o seleccione un entorno ya existente.
- [Copie un entorno](/power-platform/admin/copy-environment) para actualizar el entorno de Power Platform que se utiliza para la asignación.

#### <a name="migrate-the-sandbox-environment"></a>Migrar el entorno de espacio aislado

1. Inicie sesión en Lifecycle Services como administrador global o usuario de la cuenta de servicio designado.

    > [!NOTE]
    > Recomendamos que use una cuenta de usuario con nombre. El usuario conectado debe tener el rol de seguridad **Propietario de proyecto** o **Administrador de entornos** en el proyecto de Lifecycle Services para Human Resources.

2. Abra el proyecto de migración de Human Resources recién creado.
3. Revise y complete las fases apropiadas de la metodología de migración y la incorporación del proyecto.
4. En el panel de información del proyecto, en el panel **Valor predeterminado: prueba de aceptación estándar**, seleccione **Migrar HR**.
5. En el panel **Seleccionar entorno para migrar**, seleccione el proyecto de Lifecycle Services apropiado y el entorno de Human Resources de origen (desde su aplicación de Human Resources independiente de origen).
6. Habilite **Asignar a un nuevo entorno de Power Platform** y seleccione el entorno de Power Platform apropiado. A continuación, seleccione **Siguiente**.
7. Complete el asistente para **Configuración de implementación (finanzas y operaciones – espacio aislado)** para confirmar los detalles y la aprobación del cliente, y luego seleccione **Implementar**.

El estado del entorno mostrará el progreso. El estado cambiará de **Cargando** a **Implementando** y a **Implementado**.

> [!NOTE]
> El panel de producción no estará disponible hasta que se complete la lista de comprobación de preparación del proyecto para su puesta en marcha. Para obtener más información, consulte [Prepararse para la publicación](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Consideraciones y supuestos

Existe un entorno de espacio aislado de Human Resources en un proyecto de Lifecycle Services del inquilino que tiene las siguientes características:

- El entorno de espacio aislado de Human Resources no está vinculado a un entorno combinado ya existente. Solo puede haber una migración en curso a la vez para un entorno de Human Resources determinado.
- La cantidad de entornos de espacio aislado que se permiten a la vez se basa en la licencia de Human Resources. Si se han adquirido suficientes licencias para el inquilino, se enumerarán entornos de espacio aislado adicionales en el panel **Entornos** del proyecto.
- Las migraciones deben realizarse a entornos del mismo tipo. En otras palabras, solo se pueden realizar migraciones de espacio aislado a espacio aislado o de producción a producción.

    > [!NOTE]
    > Solo se tienen en cuenta los tipos de entorno de Human Resources cuando se determina el estado de producción o de espacio aislado. Si los entornos están categorizados incorrectamente (es decir, un entorno de producción está marcado como entorno de espacio aislado o un entorno de espacio aislado está marcado como un entorno de producción), comuníquese con Soporte.

- Si la migración no se realiza correctamente, se mostrará un mensaje de error y se visualizará un botón **Quitar**. Utilice este botón para eliminar la migración errónea. Después podrá volver a migrar el entorno.

#### <a name="validate-the-sandbox-migration"></a>Validar la migración del espacio aislado

Una vez que el proceso de migración de espacio aislado se haya completado con éxito, cree un plan de prueba detallado para verificar y aprobar todos los procesos de negocio.

Antes de comenzar la prueba, valide los siguientes detalles:

- Confirme que se puede acceder al entorno migrado en la dirección URL que se genera.
- Confirme que los usuarios pueden acceder al espacio aislado migrado.
- Confirme que el entorno de Dataverse que está asociado al entorno de espacio aislado migrado es accesible.
- Revise distintos datos para confirmar que los datos más actualizados estén disponibles.
- Complete los procesos de negocio críticos para la validación.
- Confirme que sus directivas de seguridad sean aplicables.
- Confirme que los trabajos por lotes se desencadenen como se esperaba.

No tendrá acceso de escritorio remoto al espacio aislado migrado. Puede usar capacidades y herramientas de autoservicio para realizar las siguientes acciones para sus entornos de espacio aislado de nivel 2 o superior:

- Acceder a la [base de datos de Azure SQL](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Acceder a los [archivos de registro](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Usar [herramientas de rendimiento](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- [Activar o desactivar el modo de mantenimiento](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Reiniciar [servicios](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Configurar [Regression Suite Automation Tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Para obtener más información, consulte [Preguntas más frecuentes para la implementación del autoservicio](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migrar un entorno de producción de Human Resources

Una vez que haya terminado de migrar y validar un entorno de espacio aislado, siga estos pasos para migrar el entorno de producción.

#### <a name="prerequisites"></a>Requisitos previos

- El estimador de suscripciones debe haberse completado.
- La [valoración de preparación](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) en vivo debe haberse completado.

#### <a name="migrate-the-production-environment"></a>Migrar el entorno de producción

1. Inicie sesión en Lifecycle Services como administrador global o usuario de la cuenta de servicio designado.

    > [!NOTE]
    > Recomendamos que use una cuenta de usuario con nombre. El usuario conectado debe tener el rol de seguridad **Propietario de proyecto** o **Administrador de entornos** en el proyecto de Lifecycle Services.

2. Abra el proyecto de migración de Human Resources nuevo.
3. Revise y complete las fases apropiadas de la metodología de migración y la incorporación del proyecto.
4. En el panel de información del proyecto, en el panel **Producción**, seleccione **Migrar HR**.
5. En el panel **Seleccionar entorno para migrar**, seleccione el proyecto de Lifecycle Services apropiado y el entorno de Human Resources de origen (desde su aplicación de Human Resources independiente de origen). A continuación, seleccione **Siguiente**.
6. Complete el asistente para **Configuración de implementación (finanzas y operaciones – espacio aislado)** para confirmar los detalles y la aprobación del cliente, y luego seleccione **Implementar**.

El estado del entorno mostrará el progreso de la implementación. El estado cambiará de **Cargando** a **Implementando** y a **Implementado**.

#### <a name="post-migration-considerations"></a>Consideraciones posteriores a la migración

- Aplique las últimas [actualizaciones de calidad](/fin-ops-core/fin-ops/get-started/quality-updates) a sus entornos.
- Si usa [tablas virtuales](hr-admin-integration-common-data-service-virtual-entities.md), vuelva a configurar los puntos de conexión.
- Vuelva a configurar la integración de doble escritura. Evalúe qué entidades deben habilitarse.
- Considere el uso de tablas virtuales para reemplazar la doble escritura para la integración.

#### <a name="dual-write-integration"></a>Integración de doble escritura

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Configurar la integración de doble escritura de Microsoft Power Platform

1. Vaya al Centro de administración de Power Platform y seleccione **Entornos** en el panel de navegación izquierdo.
2. Seleccione el entorno previamente copiado o actualizado y confirme que el estado es **Listo**.
3. Vaya a Lifecycle Services y confirme que el estado del proyecto de migración sea **Implementado**.
4. En el entorno migrado, seleccione **Detalles completos** para revisar detalles adicionales y [configurar una aplicación de doble escritura](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. En el panel **Configuración de la aplicación de doble escritura**, seleccione la casilla de verificación para aceptar asignar y sincronizar datos entre bases de datos, y luego seleccione **Configurar**.
6. Cuando un cuadro de mensaje le notifique que la configuración de doble escritura se realizó correctamente, seleccione **Aceptar**.
7. Puede supervisar el progreso de la configuración en los detalles.
8. Una vez completada la configuración, seleccione **Vincular al entorno de Power Platform** para sincronizar las entidades de datos disponibles.
9. Cuando el estado indique que los entornos se han vinculado correctamente, vaya al centro de administración de Power Platform para revisar y seleccionar las entidades de datos apropiadas.
10. En el panel izquierdo, seleccione **Aplicaciones de Dynamics 365 \> Recursos**.
11. Confirme que el estado de la aplicación de Human Resources de doble escritura es **Habilitado**.
12. Seleccione la aplicación de Human Resources de doble escritura y luego seleccione **Instalar**.
13. En el panel **Instalar aplicación de doble escritura Dynamics 365 Human Resources**, seleccione el entorno apropiado para instalar en él el paquete.
14. Seleccione la casilla de verificación para aceptar los términos del servicio y luego seleccione **Instalar**.
15. En el entorno de la aplicación Dynamics 365, el estado será **Instalando** mientras que la instalación está en curso. Se actualizará a **Instalado** cuando se haya completado la instalación.

##### <a name="review-and-apply-a-dual-write-solution"></a>Revisar y aplicar una solución de doble escritura

1. En el nuevo entorno de finanzas y operaciones, vaya a **Administración de datos \> Doble escritura**.
2. Seleccione **Aplicar solución**.
3. En el panel, seleccione **Soluciones de Dynamics instaladas**, **Asignaciones de entidades centrales de aplicaciones de doble escritura** y **Asignaciones de Dynamics 365 Human Resources**. Luego seleccione **Aplicar**. Un mensaje confirmará que se está aplicando la solución. Una vez que la solución se haya aplicado con éxito, se mostrarán todas las asignaciones de tablas disponibles.
4. Revise las asignaciones de tablas disponibles para seleccionar y ejecutar la integración mediante doble escritura.
5. Cuando ejecute la integración de doble escritura por primera vez para asignaciones de tablas, seleccione la casilla de verificación **Sincronización inicial**. Si hay una integración existente del entorno de Human Resources de origen, no es necesario que seleccione la casilla de verificación **Sincronización inicial** cuando ejecute la integración de asignaciones de tablas.

#### <a name="recommended-practices"></a>Prácticas recomendadas

Esta sección describe recomendaciones para migrar desde la infraestructura independiente hasta la infraestructura de operaciones y finanzas.

- Le recomendamos que trabaje con su socio de Microsoft Dynamics para obtener ayuda con la migración de su entorno de Human Resources.
- Planifique el tiempo adecuado para realizar pruebas de aceptación de usuario (UAT) completas en el entorno migrado de espacio aislado.
- Planifique y documente los pasos detallados para migrar integraciones al entorno migrado.
- Cree una lista de verificación detallada para revisar el proceso de transición de su migración.
- Planifique una cantidad adecuada de tiempo de inactividad de su negocio mientras realiza la migración.
- Recomendamos enfáticamente que los clientes calificados para FastTrack trabajen con su arquitecto de soluciones FastTrack para obtener ayuda para supervisar el proceso de migración.
- Recomendamos encarecidamente que actualice su entorno de espacio aislado en la infraestructura independiente antes de realizar la primera migración. Esta actualización debe incluir su entorno de Dataverse conectado al entorno de espacio aislado al que planea migrar.
- Recomendamos encarecidamente que use una cuenta de servicio cuando implemente, migre y cree su proyecto de Lifecycle Services.
- Planee actualizar el entorno de espacio aislado para la validación de UAT en la última versión de disponibilidad general (GA). Para obtener más información, consulte [Consideraciones](hr-infrastructure-merge.md#considerations).
