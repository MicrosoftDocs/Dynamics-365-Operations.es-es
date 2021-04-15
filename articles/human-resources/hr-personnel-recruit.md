---
title: Contratar candidatos de trabajo
description: Este tema muestra cómo contratar candidatos en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9259cfa78d65f36da653c807a66e291b3cb01c63
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802536"
---
# <a name="recruit-job-candidates"></a>Contratar candidatos de trabajo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources le ayuda a administrar las solicitudes de contratación. También le ayuda a realizar una transición sin problemas de candidatos de puestos de trabajo a empleados. Si su organización usa una aplicación de contratación independiente, su proceso de contratación puede incluir los siguientes pasos:

- Introduzca su solicitud de contratación en Recursos Humanos.
- Reciba referencias de candidatos en Human Resources desde la aplicación de contratación.
- Completa el proceso de aprobación de candidatos en Human Resources.

Si no está usando una aplicación de contratación independiente, también puede administrar candidatos manualmente en Human Resources.

>[!NOTE]
>Si es administrador o desarrollador, y desea integrar Human Resources con una aplicación de contratación de terceros, consulte [Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md) y [Configurar las tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> También puede encontrar aplicaciones de integración de contratación en [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
> Para probar nuestra característica en vista previa para la integración con LinkedIn Talent Hub, consulte [Integrar con LinkedIn Talent Hub](hr-admin-integration-linkedin.md).

## <a name="enable-recruiting-requests"></a>Habilitar solicitudes de contratación

Si desea enviar solicitudes de contratación en Human Resources, debe habilitar primero la funcionalidad en **Parámetros compartidos de recursos humanos**.

1. En el espacio de trabajo **Administración de personal**, seleccione **Vínculos**.

2. En **Configuración**, seleccione **Parámetros compartidos de Recursos Humanos**.

3. En la pestaña **Contratación**, en **CONTRATACIÓN**, establezca **Habilitar solicitudes de contratación** en **Sí**.

## <a name="add-a-recruiting-request-location"></a>Agregar una ubicación de solicitud de contratación

Si su organización tiene varias ubicaciones, puede agregarlas para que los solicitantes puedan seleccionar una ubicación donde trabajará el nuevo empleado. La ubicación se incluirá en la publicación del trabajo.

1. En la barra de búsqueda, introduzca **ubicación de la solicitud de contratación**.

2. Seleccione **Nuevo**.

3. En el campo **Ubicación de la solicitud de contratación**, introduzca el nombre de la ubicación.

   ![Agregar una ubicación de solicitud de contratación](./media/hr-recruit-0a-add-location.png)

4. En la **Descripción**, escriba una descripción para la ubicación.

5. En **Ubicación**, seleccione **Agregar**. Si aparece la ventana emergente **Nueva dirección**, introduzca la dirección de la ubicación.

   ![Especificar dirección](./media/hr-recruit-0b-address.png)

6. En **Información del contacto**, introduzca la información del contacto de la ubicación.

7. Seleccione **Guardar**.

## <a name="add-a-recruiting-request"></a>Agregar una solicitud de contratación

Los responsables pueden enviar solicitudes de contratación en Human Resources. Si usa una solicitud de contratación independiente, al completar estos pasos se enviará una solicitud de contratación e iniciará el proceso de contratación en esa aplicación. De lo contrario, complete este procedimiento para comenzar el flujo de trabajo para su propio proceso de contratación interno.

1. Seleccione **Autoservicio para empleados**.

2. Seleccione la pestaña **Mi equipo**.

3. Seleccione **Solicitud de contratación**.

   ![Iniciar una solicitud de contratación](./media/hr-recruit-1-request-to-recruit.png)

4. Complete los campos **Descripción**, **Trabajo** y **Fecha de inicio estimada**.

   ![Completar la solicitud de contratación](./media/hr-recruit-2-request-to-recruit.png)

5. Seleccione **Continuar**. Aparece la solicitud de contratación para su puesto.

6. En **General**, seleccione un contratante el menú desplegable **Contratante** y, a continuación, seleccione una ubicación en el menú desplegable **Ubicación de la solicitud de contratación**.

7. En **Trabajo**, cambie cualquier información según sea necesario y, a continuación, seleccione **Crear detalles a partir del trabajo**.

   ![Crear detalles desde el trabajo](./media/hr-recruit-3-create-details-from-job.png)

   El resto de la solicitud de contratación se completará con la información predeterminada para el trabajo que ha introducido.

8. En **Descripción externa**, introduzca una descripción de trabajo externa.

9. En **Puestos**, seleccione **Agregar** y, a continuación, un puesto para esta solicitud de contratación.

   ![Agregar un puesto](./media/hr-recruit-4-select-position.png)

10. En **Aptitudes**, seleccione **Agregar** y, a continuación, una aptitud.

11. En **Requisitos educativos**, seleccione **Agregar** y, a continuación, seleccione valores en los menús desplegables **Aptitudes** y **Nivel de formación**.

   ![Agregar requisitos educativos](./media/hr-recruit-5-select-educational-requirements.png)

12. En **Comentario**, agregue comentarios según sea necesario.

13. En **Compensación**, seleccione un nivel en el menú desplegable **Nivel** y luego ajuste **Umbral inferior**, **Punto de control** y **Umbral superior** según sea necesario.

14. Cuando se complete su solicitud de contratación y esté listo para iniciar el proceso de contratación, seleccione **Activar** en la barra de menús.

   ![Activar solicitud de contratación](./media/hr-recruit-6-activate-recruit-request.png)

15. Seleccione **Guardar**.

## <a name="view-and-edit-your-recruiting-requests"></a>Ver y editar sus solicitudes de contratación

Si es un responsable y desea ver sus propias solicitudes:

1. Seleccione **Autoservicio para empleados**.

2. Seleccione la pestaña **Mi equipo**.

3. En **Información de mi equipo**, seleccione la pestaña **Solicitudes de contratación**.

   ![Seleccionar la pestaña Solicitudes de contratación](./media/hr-recruit-7-recruiting-requests.png)

4. Para ver o editar una solicitud de contratación, selecciónela en la cuadrícula.

Si es un profesional de recursos humanos y desea ver todas las solicitudes de contratación:

1. Seleccione **Administración de personal**.

2. Seleccione **Solicitudes de contratación**.

   ![Ver solicitudes de contratación en Administración de personal](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Para ver o editar una solicitud de contratación, selecciónela en la cuadrícula.

## <a name="add-or-edit-a-candidate-profile"></a>Agregar o editar un perfil de candidato

Si su organización se ha integrado con otra aplicación para administrar las solicitudes de contratación, las solicitudes de contratación se reenvían a esa aplicación. Luego, la aplicación de contratación devuelve la información del candidato a Recursos Humanos. De lo contrario, puede seguir sus propios procesos de contratación internos e introducir la información del candidato manualmente.

1. Seleccione **Administración de personal**.

2. Seleccione **Vínculos**.

3. En **Contratación**, seleccione **Candidatos**.

   ![Ver candidatos](./media/hr-recruit-9-candidates.png)

4. Para agregar un candidato, seleccione **Nuevo**. Para editar un candidato existente, selecciónelo en la lista y después seleccione **Editar**. Aparece el perfil del candidato.

5. En **Resumen del candidato**, introduzca o edite la información del candidato según sea necesario.

6. En **Solicitud de reclutamiento**, seleccione una solicitud de contratación a la que vincular al candidato. A continuación, complete los campos **Fecha de inicio estimada**, **Responsable de contratación**, **Puesto** y **Descripción** según sea apropiado.

   ![Vincular a la solicitud de contratación](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Complete toda la información en las siguientes áreas que desea incluir en el registro del candidato:
   - **Comentarios**
   - **Experiencia profesional**
   - **Información de contacto**
   - **Formación**
   - **Aptitudes**
   - **Certificados**
   - **Filtrados**

8. Seleccione **Guardar**.

## <a name="hire-a-candidate"></a>Contratar un candidato

Cuando esté listo para contratar a un candidato, siga este procedimiento para hacer la transición del candidato a empleado.

1. En el formulario del candidato, seleccione **Contratar**.

   ![Contratar un candidato](./media/hr-recruit-11-hire.png)

2. En el formulario **Contratar nuevo trabajador**, en **Detalles**, complete todos los campos.

   ![Introducir los detalles de la nueva contratación](./media/hr-recruit-12-hire-new-worker.png)

3. En **Detalles del puesto**, compruebe y cambie la información según sea necesario.

4. En **Listas de comprobación de incorporación**, seleccione las listas de comprobación de incorporación relevantes para este empleado.

5. Seleccione **Continuar** para crear el registro de empleado.

   >[!NOTE]
   >Dependiendo de los flujos de trabajo de su organización, el registro de candidato puede pasar por pasos de aprobación adicionales antes de convertirse en un registro de empleado.

## <a name="decide-not-to-hire-a-candidate"></a>Decide no contratar a un candidato

Si decide no contratar a un candidato, siga este procedimiento para eliminarlo del proceso de examen. 

1. En el formulario del candidato, seleccione **No contratar**.

   ![No contratar candidato](./media/hr-recruit-13-do-not-hire.png)

2. Seleccione un **Código de motivo** e incluya cualquier comentario.

3. Seleccione **Aceptar**.

## <a name="dismiss-a-candidate"></a>Descartar un candidato

Si es necesario, puede despedir a un candidato después de contratarlo. Por ejemplo, un candidato puede rechazar su oferta o no presentarse el primer día.

- En el formulario del candidato, seleccione **Despedir candidato**.

  ![Descartar candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Consulte también

[Configurar tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organizar los recursos](hr-personnel-departments-jobs-positions.md)<br>
[Configurar los componentes de un trabajo](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
