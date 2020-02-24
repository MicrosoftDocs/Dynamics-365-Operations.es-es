---
title: Administrar características
description: Aprenda a activar o desactivar nuevas funciones en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010437"
---
# <a name="manage-features"></a>Administrar características

Como parte de nuestro desarrollo continuo de nuevas capacidades de Microsoft Dynamics 365 Human Resources, deseamos que los clientes experimenten las nuevas características lo más rápidamente posible. Ofrecemos características en versión preliminar, que están casi preparadas para la disponibilidad general y han pasado por un amplio proceso de pruebas. Simplemente estamos buscando una ronda final de comentarios de clientes y de validación antes de estén disponibles de forma general.

Para obtener más información sobre características nuevas en Human Resources, consulte [Novedades en Human Resources](hr-admin-whats-new.md) y [Plan de lanzamiento de Dynamics 365 and Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

El espacio de trabajo **Administración de características** proporciona una lista de características entregadas en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación. Para obtener más información acerca de la administración de características, consulte [Visión general de la Administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días. Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar. En cuanto vea características nuevas en el espacio de trabajo **Administración de características**, puede activarlas. Algunas características pueden estar activadas de forma predeterminada.

Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción. El espacio de trabajo **Administración de características** indica cuando una característica de versión preliminar pasará a ser obligatoria. Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación. No pueden desactivar características obligatorias. Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.

## <a name="enable-or-disable-preview-features"></a>Habilitar o deshabilitar las funciones de vista previa

Para obtener acceso a características de vista previa, primero debe permitirlas en el entorno. Habilitar o deshabilitar las características de vista previa es específica del entorno.

> [!IMPORTANT]
> Las características de vista previa solo están disponibles en entornos de **Espacio aislado**. Cuando activa una característica en versión preliminar, lo hace para todos los usuarios de la organización que se encuentran en dicho entorno. Cuando desactiva una característica en versión preliminar, la deshabilita y hace que no sea accesible para los usuarios. Las funciones de vista previa tienen compatibilidad limitada en Human Resources. Es posible que apliquen menos medidas de privacidad y de seguridad, y no se incluyen en el contrato de nivel de servicio (SLA) de Human Resources. No debe utilizar características de vista preliminar para procesar datos personales (es decir, toda información que pueda identificarle), o para procesar otros datos sujetos a requisitos de conformidad legales o administrativos.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione la ventana **Gestión de funciones**.

3. Para habilitar una característica en versión preliminar, selecciónela de la lista y luego seleccione **Habilitar**. Para deshabilitar una característica en versión preliminar, selecciónela de la lista y luego seleccione **Deshabilitar**.

## <a name="preview-feature-benefits-management"></a>Característica de vista previa: administración de prestaciones

La administración de beneficios le brinda una solución flexible que admite una amplia variedad de opciones de beneficios, junto con una experiencia de los empleados fácil de usar que muestra sus ofertas. Para obtener más información sobre la configuración y el uso de la administración de beneficios, consulte [Resumen de gestión de beneficios](hr-benefits-management-overview.md).

La gestión de beneficios reemplaza la funcionalidad en el espacio de trabajo **Beneficios**. Cuando habilita la función de vista previa de administración de Beneficios, ya no puede acceder a los siguientes formularios en el espacio de trabajo **Beneficios**:

- **Prestaciones**
- **Elementos de beneficio**
- **Índices de cálculo de la contribución**
- **Resultados de la inscripción a beneficios**
- **Resultados de la expiración y la extensión de los beneficios**
- **Tipos de reglas de directiva de idoneidad de beneficio**
- **Directivas de idoneidad para prestaciones**
- **Eventos de idoneidad**

Puede ver la información en estos formularios en modo de solo lectura. Si desea editar la información, primero debe deshabilitar la función de vista previa de administración de Beneficios.

### <a name="benefits-management-known-issues"></a>Problemas conocidos de la gestión de beneficios

#### <a name="life-events"></a>Eventos de vida

Al procesar eventos de la vida, el usuario recibirá un error:

La fecha de inicio de la cobertura debe estar entre *comienzo del período del plan* y *fin del período del plan*. 

El evento de la vida continuará procesándose como se esperaba.

#### <a name="eligibility-processing"></a>Procesamiento de idoneidad

Al ejecutar la idoneidad para las prestaciones que usan un importe de cobertura de salario a 1-5X, % de salario e importe fijo, debe establecer la fecha de Detalles de la prestación para la Fecha inicial del empleado en **Historial del empleo**, con las horas trabajadas, la frecuencia de pago y el importe del salario para prestaciones anuales. Si existe una compensación fija para el trabajador, ingrese las horas trabajadas junto con la frecuencia de pago, y se calculará el monto del salario anual. Si el empleado es asalariado, no necesita introducir las horas trabajadas. Recomendamos que al crear nuevos trabajadores, ingrese primero una compensación fija. Para actualizar el registro de detalles de prestaciones: navegue a **Trabajador > Historial del trabajador > Detalles del empleo**. Ajuste la fecha a la fecha de comienzo del empleado.

#### <a name="employee-self-service"></a>Autoservicio para empleados

Los empleados pueden seleccionar un plan para el que no están calificados y consultar. Por ejemplo: un trabajador no tiene dependientes, pero puede seleccionar un plan médico con una opción de cobertura familiar.

El importe del empleado no se calcula al actualizar el importe de la cobertura del seguro de vida. Por ejemplo, cuando a un empleado se le ofrece un plan de seguro de vida, puede seleccionar hasta 50 000 USD en cobertura a un costo de 0,36 USD por 1000 USD de cobertura.  Cuando el empleado actualiza el monto de la cobertura, el costo asociado del empleado permanece en cero.

Para un plan de prestaciones que solo permite una única selección de ese tipo de plan, el usuario recibirá un error si intenta renunciar a un plan después de seleccionarlo. Por ejemplo, un usuario selecciona un plan médico y lo coloca en su carrito. El usuario luego selecciona **Renunciar** para otro plan médico El usuario recibirá un error.

## <a name="preview-features-in-leave-and-absence"></a>Características de vista previa para permisos y ausencias

Las características en versión preliminar para permisos y ausencias son:

- **Calendario de bajas y ausencias**: los parámetros de bajas y ausencias se moverán de **Parámetros de recursos humanos** a una nueva pantalla llamada **Parámetros de bajas y ausencias**. La nueva pantalla incluye una nueva pestaña **Calendario**. Esta vista previa solo habilita un subconjunto de los parámetros. Puede acceder a la nueva pantalla desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**. Los calendarios incluyen:
  - **Calendario de la empresa**: muestra todas las solicitudes de tiempo libre de los empleados. Las personas con el rol **Recursos humanos** pueden acceder a este calendario desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**.
  - **Calendario del equipo gerente**: muestra todas las solicitudes de tiempo libre de informes directos. Los gerentes pueden acceder al calendario desde la pestaña **Mi equipo** en Autoservicio de empleados, en **Bajas y ausencias**. 

- **Calendarios de bajas y ausencias por vacaciones** : los tipos de baja incluyen una nueva opción **vacaciones**, utilizada junto con el calendario laboral. Los días definidos por vacaciones y cierres ahora se designan como **Vacaciones** cuando se generan días hábiles. Cuando se procesan las acumulaciones, se realizan ajustes a los empleados asignados al calendario para contabilizar los días festivos que caen en un día hábil.

- **Auditoría de acumulación de bajas**: una nueva pantalla le permite revisar cuándo se han procesado y eliminado las acumulaciones, tanto por parte de todos los empleados como de los empleados individuales. Puede acceder a esta nueva pantalla desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**.

- **Eliminación de bajas acumuladas**: ahora puede eliminar registros de acumulación para planes de bajas específicos. Puede acceder a esta nueva opción desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**. Para empleados individuales, esta opción aparece en la agrupación **Bajas y ausencias** en el perfil del empleado. 

- **Redondeo de acumulación de bajas**: las nuevas opciones de **tipo de baja** definen qué tipo de redondeo debe usar la acumulación, más la precisión decimal del redondeo durante el proceso de acumulación. Cuando se procesan las acumulaciones, el redondeo y la precisión se aplican a los registros de acumulación. 

- **Configurar múltiples tipos de bajas en un solo plan de bajas**: una nueva columna en el programa de acumulación de bajas para los tipos de vacaciones le permite definir varios tipos de bajas en un plan de bajas y ausencias con diferentes programaciones de acumulación. El anterior campo **Tipo de baja** se ha eliminado. En la inscripción de empleados, los saldos para los tipos de licencia ahora se muestran en una tabla en lugar de en la parte superior de la pantalla.

  > [!IMPORTANT]
  > Después de habilitar esta función, no puede desactivarla.

- **Usar la equivalencia de tiempo completo (FTE) de un empleado para la acumulación**: una nueva columna en el programa de acumulación de bajas permite utilizar FTE para la acumulación. Cuando se procesan las acumulaciones, la aplicación utiliza la posición principal del empleado y el FTE definido para determinar el monto acumulado prorrateado.

  > [!NOTE]
  > Esta función solo está disponible si habilita **Configurar múltiples tipos de bajas por plan de baja**. 

## <a name="feedback"></a>Realimentación

Queremos conocer su experiencia con las características en versión preliminar. Recomendamos que publique con regularidad sus comentarios en los sitios siguientes cuando use estas características u otras:

- [Comunidad](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Este sitio es un gran recurso en el que los usuarios pueden discutir los casos de uso, hacer preguntas, y obtener ayuda de la comunidad.
- Infórmenos sobre las características que desea ver en el producto, así como los cambios que crea que deberíamos realizar en las características existentes. Sugiera ideas de productos en [Ideas de recursos humanos](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
No incluya los datos personales (información que podría identificarle) en los envíos de comentarios o de revisión del producto. La información que se obtiene se puede analizar más, pero no se usará para responder a solicitudes, de acuerdo con las leyes aplicables de privacidad. La información personal obtenida por separado en estos programas está sujeta a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Consulte también

- [Novedades de Human Resources](hr-admin-whats-new.md)
- [Plan de la versión de Dynamics 365 y Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)