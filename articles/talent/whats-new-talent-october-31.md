---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (31 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4851c62a19bb562c7f5f578aecbae99cfcdb982f
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897382"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-31-2018"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (31 de octubre de 2018)

**Compilación 8.1.2031**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="create-links-from-talent-to-finance"></a>Crear enlaces de Talent a Finance
Esta nueva funcionalidad de navegación le permite establecer vínculos con Talent desde Finance, dándole una exploración directa en las páginas de Finance. Cuando se configuren los vínculos, puede especificar el grupo y el nombre del vínculo, dónde el vínculo debe salir en Talent y la página de destino que se abre en Finance.

#### <a name="coming-soon"></a>Próximamente
El contexto del campo se agregará en el futuro para permitir navegación directa en los correspondientes registros de Finance. Por ejemplo, puede usar **Vínculo al campo** para proporcionar el contexto para navegar directamente a un empleado o un puesto concreto en Finance.

### <a name="configure-target-systems"></a>Configurar sistemas de destino

En Talent, los administradores del sistema pueden definir vínculos que emergerán a través del espacio de trabajo de administración del sistema. Parte de la configuración la constituyen los entornos de Finance donde desea navegar como destino del vínculo. Esto se hace asignando al sistema de destino un nombre y proporcionando la dirección URL del entorno de Finance. A continuación se indica un ejemplo de una dirección URL de Finance que se proporcionaría: https://devax00124aos.cloud.test.dynamics.com/. Una vez configurados los sistemas de destino, puede definir sus vínculos.

### <a name="configure-links"></a>Configurar vínculos

Cada vínculo que se crea tendrá la siguiente información definida.

- Vínculo - nombre del vínculo, que se usará para la identificación únicamente.

- Habilitar este vínculo - configurado en **Sí** si desea visualizar el vínculo para los usuarios de Talent.

- Nombre para mostrar - permite definir el nombre que aparecerá como un vínculo en Finance. Estos datos no es se convierten actualmente.

- Vínculo de superficie en el formulario - permite seleccionar la página donde quisiera mostrar el vínculo.

- Grupo - no se requieren grupos, pero si desea organizar sus vínculos mediante grupos, seleccione un grupo existente o cree uno nuevo con el campo **Grupo**.

- Sistema de destino - seleccione el sistema de destino que se creó, usando la opción **Configurar el sistema de destino**. Este será el entorno de Finance que se utilizará para navegar usando el vínculo.

- Usar la compañía actual de usuario - Seleccione **Sí** si desea usar el contexto de la empresa actual del usuario al navegar en Finance. Si se selecciona **No**, se puede seleccionar la empresa que se utilizará.

- Elemento de menú de destino - permite especificar el elemento de menú de Finance que el vínculo debe usar al navegar. Están disponibles los elementos de menú a los que puede navegar directamente. Para encontrar el elemento de menú necesario, abra Finance y la página que es el destino de navegación. Copie el elemento de menú desde la URL. Por ejemplo, si desea que el vínculo lo lleve a la lista de empleados de Finance and Operations, especifique el valor que aparece después de "&mi" en la dirección URL. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. El elemento de menú para navegar a la página de lista de empleados de este ejemplo es: HcmWorkerListPage_Employees.

- Vínculo al origen de datos - seleccione el origen de los datos al que hace referencia el vínculo. La mayoría de los orígenes más habituales como **Trabajador** y **Posición** están disponibles.

- Vínculo al campo - (pronto disponible) Esta selección del campo permitirá la exploración directa desde un único registro de Talent a un único registro de Finance.

### <a name="access-to-links"></a>Acceso a vínculos

Los administradores del sistema verán los vínculos recién creadaos en las páginas definidas incluso si la opción **Habilitar este vínculo** se establece en **No**. Puede utilizarse para probar vínculos antes de sacarlos y asignarlos a otros empleados. El resto de los roles solo verán los vínculos configurados después de que la opción **Habilitar este vínculo** se establezca en **Sí**. Los empleados con acceso a las páginas en las que se emergen los vínculos tendrán acceso a los vínculos.

Los usuarios también pueden tener derechos de seguridad en Finance definidos para obtener acceso a las páginas de Finance and Operations. Si no los tienen, se abre un cuadro de diálogo al utilizar el vínculo.


## <a name="other-changesfixes"></a>Otros cambios/correcciones

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Los puestos con una fecha de inicio futura no se pueden asignar a un nuevo empleado

Se han realizado cambios para permitir asignaciones de empleados a puestos futuros. Los puestos que tienen fechas iniciales en el futuro se pueden seleccionar y la asignación de empleado se realizar al guardar o al finalizar el flujo de trabajo (si se habilita el flujo de trabajo).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>No se puede asignar un puesto existente a un empleado nuevo

Se han realizado cambios por los que ahora se puede realizar una nueva asignación de empleado a puestos existentes.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>La fecha de antigüedad o la ubicación de la oficina desaparece cuando la fecha de inicio del empleo está en el pasado y se guarda el registro

Se han realizado cambios para corregir la visibilidad de **Fecha de antigüedad** y **Ubicación de la oficina** al guardar los cambios para los últimos empleados.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>No se pueden especificar los datos de los empleos del futuro en la página del trabajador

Los datos de empleo para los empleos futuros se han deshabilitado en la página principal del trabajador. Los datos de empleo se pueden especificar en las páginas **Administrador de fechas**. Se realizarán cambios adicionales en versiones futuras para habilitar especificar datos de empleo directamente durante el proceso de flujo de trabajo.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Agregar ValidFrom y ValidTo a HcmPersonalContactPersonEntity

Se ha actualizado la entidad del marco de gestión de datos HcmPersonalContactPersonEntity (DMF) para incluir las fechas “válido a partir “y “válido hasta" para habilitar determinadas escenarios de integración de prestación. 

## <a name="known-issue"></a>Problema conocido
- **Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan. 
- **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
