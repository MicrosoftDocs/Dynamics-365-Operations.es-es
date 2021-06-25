---
title: Introducir aptitudes
description: Las obras y los gerentes pueden introducir aptitudes en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193986"
---
# <a name="enter-skills"></a>Introducir aptitudes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede especificar aptitudes objetivo o aptitudes reales para trabajadores, candidatos o contactos en Dynamics 365 Human Resources. Una aptitud objetivo es una aptitud una persona tiene previsto lograr. Una aptitud real es una aptitud que una persona tiene actualmente.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Cree un flujo de trabajo para aprobar automáticamente las aptitudes

Para introducir aptitudes sin requerir aprobación, debe crear un flujo de trabajo para aprobar automáticamente las aptitudes.

> [!NOTE]
> Las aptitudes ingresadas por los trabajadores siempre requieren la aprobación del gerente. Este flujo de trabajo solo aprueba automáticamente las aptitudes introducidas por los gerentes en nombre de sus trabajadores.

1. En el espacio de trabajo **Administración de personal**, seleccione **Vínculos**.

2. En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.

3. Seleccione **Nuevo**.

4. En el panel **Crear flujo de trabajo**, seleccione **Aptitudes del trabajador**.

   [![Seleccione el flujo de trabajo de aptitudes del trabajador](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. En el diálogo **¿Abrir este archivo?**, seleccione **Abrir**. Cuando se le solicite, introduzca sus credenciales.

6. En el editor de flujo de trabajo, seleccione el elemento de flujo de trabajo **Aprobar aptitudes** y arrástrelo al lienzo.

   [![Seleccione el elemento de flujo de trabajo Aprobar aptitudes](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Conecte el elemento **Comienzo** al elemento **Aprobar aptitudes 1**, y luego conecte el elemento **Aprobar aptitudes 1** al elemento **Final**. Es posible que deba desplazarse hacia abajo para ver el elemento **Final**. Puede arrastrarlo más cerca de los otros elementos.

   [![Conectar elementos del flujo de trabajo](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Haga doble clic en el elemento de flujo de trabajo **Aprobar aptitudes 1** y, a continuación, haga clic con el botón derecho en el elemento **Paso 1**. Haga clic con el botón secundario en el elemento **Paso 1** y, a continuación, seleccione **Propiedades**.

9. En la ventana **Propiedades**, seleccione **Condición** en la barra de navegación de la izquierda.

10. Seleccione **Ejecutar este paso únicamente si se cumplen las condiciones siguientes**.

11. Seleccione **Agregar condición**. Tras **Dónde**, seleccione **Aptitudes de autoservicio de los empleados** y luego seleccione **Aptitudes de autoservicio de los empleados.**. Tras **es**, seleccione **campo** y luego seleccione **Relación de usuario a persona.**.

    [![Especificar condición](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Seleccione **Asignación** en la barra de navegación de la izquierda.

13. En la pestaña **Tipo de asignación**, seleccione **Jerarquía**.

14. En la pestaña **Selección de jerarquía**, en el campo **Tipo de jerarquía:**, seleccione **Jerarquía gerencial**.

    [![Especificar jerarquía gerencial](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Seleccione **Cerrar**, seleccione **Flujo de trabajo** en la ruta de navegación del lienzo y, a continuación, seleccione **Guardar y cerrar**.

Para obtener más información sobre crear flujos de trabajo, consulte [Visión general del sistema de flujos de trabajo](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Introducir aptitudes para un trabajador

1. Seleccione un trabajador.

2. En la barra de acciones de la página **Trabajador**, seleccione **Persona** y luego seleccione **Aptitudes**.

3. En la página **Aptitudes**, complete los siguientes campos para cada aptitud:

   - **Aptitud**: seleccione una aptitud.
   - **Tipo de nivel**: seleccione **Actual** para una aptitud que el trabajador ya tiene, o seleccione **Objetivo** para una aptitud en la que el trabajador está trabajando.
   - **Nivel**: seleccione un nivel para la aptitud del trabajador.
   - **Fecha de nivel**: seleccione una fecha en la herramienta calendario.
   - **Examinador**: si corresponde, seleccione un examinador de la lista. Puede filtrar su búsqueda.
   - **Años de experiencia**: introduzca los años de experiencia.
   - **Verificado**: si se verifica la habilidad, marque la casilla.
   - **Verificada por**: introduzca el nombre del verificador.

4. Cuando haya terminado de introducir habilidades, seleccione **Guardar**.

## <a name="see-also"></a>Consulte también

[Configurar aptitudes](hr-develop-skills.md)<br>
[Asignar aptitudes](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]