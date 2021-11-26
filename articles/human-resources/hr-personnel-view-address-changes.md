---
title: Ver y administrar cambios de dirección
description: En este tema se explica cómo puede ver y administrar los cambios de dirección en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ed7ddb192b338f6373e8b53be710c961d918921f
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728842"
---
# <a name="view-and-manage-address-changes"></a>Ver y administrar cambios de dirección

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema explica cómo puede ver y administrar los cambios de dirección en la página **Editar datos personales** (que se abre desde el área de trabajo **Autoservicio para empleados**) o la página de detalles **Trabajador** en Dynamics 365 Human Resources.

Muchas organizaciones quieren que los empleados administren sus propios datos personales a través de una experiencia de autoservicio. Puede permitir que los usuarios actualicen su dirección en el espacio de trabajo **Autoservicio para empleados**. Puede supervisar estos cambios en el espacio de trabajo **Administración de personal**. Para utilizar esta función, debe especificar el número de días que desea ver los cambios en la página **Parámetros de Recursos Humanos**.

## <a name="configure-address-change-parameters"></a>Configurar los parámetros de cambio de dirección

Para configurar el número de días que desea que aparezcan los cambios de dirección en el espacio de trabajo **Administración de personal**, siga estos pasos:

1. En el panel de navegación, seleccione **Administración de personal**.
2. Seleccione **Vínculos**.
3. Seleccione **Parámetros de Recursos Humanos**.
4. En el campo **Número de días**, en **Cambio de dirección**, escriba el número de días que desea que aparezcan los cambios de dirección en el espacio de trabajo **Administración de personal**.
5. Cierre la página.

## <a name="create-or-change-an-employee-address"></a>Crear o cambiar la dirección de un empleado

Los empleados pueden actualizar su dirección en el espacio de trabajo **Autoservicio para empleados**. Siga estos pasos para crear o cambiar una dirección:

1. Seleccione la ventana **Autoservicio para empleados** en la página **Domicilio**.
2. Seleccione **Editar detalles personales**.
3. Para agregar una dirección, seleccione **Agregar**. Para actualizar una dirección existente, seleccione la dirección en la lista y después seleccione **Editar**.
4. Escriba un nombre o una descripción en **Nombre o descripción**.
5. Seleccione el cuadro desplegable **Propósito** y después seleccione el tipo de dirección.
6. Introduzca un valor en **País/región**.
7. Escriba el **Código postal**.
8. Escriba la **Calle**.
9. Escriba la **Ciudad**, la **Comunidad autónoma** y la **Provincia**. Normalmente, estos campos se configuran automáticamente a partir del campo **Código postal**.
10. Opcionalmente, seleccione el campo **Principal** para indicar una dirección principal. Solo se puede marcar una dirección como principal. Si ya hay otra dirección marcada como dirección principal, deberá confirmar que desea utilizar esta dirección como principal.
11. Opcionalmente, seleccione el campo **Privada** para indicar que la dirección es privada. Solo los usuarios con permiso explícito para ver información de direcciones privadas podrán ver esta dirección.
12. Seleccione **Aceptar**.

## <a name="create-or-change-a-worker-address"></a>Crear o cambiar la dirección de un trabajador

Puede actualizar una dirección en el espacio de trabajo **Administración de personal**. Siga estos pasos para crear o cambiar una dirección:

1. En el espacio de trabajo **Administración de personal**, seleccione **Vínculos** y, a continuación, seleccione **Trabajadores**.
2. Seleccione el trabajador y, a continuación, seleccione **Direcciones**.
3. Para agregar una dirección, seleccione **Agregar**. Para actualizar una dirección existente, seleccione la dirección en la lista y después seleccione **Editar**.
4. Escriba un nombre o una descripción en **Nombre o descripción**.
5. Seleccione el cuadro desplegable **Propósito** y después seleccione el tipo de dirección.
6. Introduzca un valor en **País/región**.
7. Escriba el **Código postal**.
8. Escriba la **Calle**.
9. Escriba la **Ciudad**, la **Comunidad autónoma** y la **Provincia**. Normalmente, estos campos se configuran automáticamente a partir del campo **Código postal**.
10. Opcionalmente, seleccione el campo **Principal** para indicar una dirección principal. Solo se puede marcar una dirección como principal. Si ya hay otra dirección marcada como dirección principal, deberá confirmar que desea utilizar esta dirección como principal.
11. Opcionalmente, seleccione el campo **Privada** para indicar que la dirección es privada. Solo los usuarios con permiso explícito para ver información de direcciones privadas podrán ver esta dirección.
12. Seleccione **Aceptar**.
 
## <a name="create-a-future-change-for-an-address"></a>Crear un cambio futuro para una dirección

En algunos casos, es posible que desee actualizar una dirección para cambiarla en el futuro. Por ejemplo, esto sería útil si un empleado se muda el día 15 del mes siguiente.

1. Abra la página **Administrar direcciones** seleccionando **Más opciones> Avanzadas** desde cualquier cuadrícula de direcciones.
2. Seleccione **Nueva** para crear una nueva dirección.
3. Escriba los detalles de la dirección.
4. Seleccione la ficha desplegable **General**.
5. En el campo **Fecha de vigencia**, seleccione la fecha en que la nueva dirección entrará en vigor.
6. En el campo **Fecha de vencimiento**, seleccione opcionalmente la fecha en que la dirección dejará de ser válida.
7. Cierre las páginas.

## <a name="view-and-monitor-address-changes"></a>Ver y supervisar cambios de dirección

El personal de Recursos Humanos puede ver y supervisar los cambios de dirección desde el espacio de trabajo **Administración de personal**. Para ver los cambios de dirección, seleccione la ventana **Administración de personal** de la página **Domicilio**. Los cambios de dirección se muestran en una ventana en la esquina superior derecha. El número mostrado sobre **Cambios de dirección** indica cuántos cambios de dirección se han producido en el número de días especificado en la página **Parámetros de Recursos Humanos**. 

Al seleccionar la ventana **Cambios de dirección**, aparece una nueva página que muestra los detalles de cambios de dirección. Opcionalmente, puede seleccionar **Incluir futuros cambios de dirección** en la esquina superior derecha para mostrar los cambios de dirección con una fecha futura.

> [!NOTE]
> Si desea recibir una alerta o un correo electrónico sobre estos cambios de dirección, puede crear una nueva regla de alerta en la pestaña **Opciones** del panel de acciones. Para obtener más información sobre las reglas de alerta, consulte [Crear reglas de alerta](../fin-ops-core/fin-ops/get-started/create-alerts.md).
>
> Si desea configurar un flujo de trabajo para los cambios de dirección, puede seleccionar la opción **Enviar externamente** en la regla de alerta y usar a continuación Power Automate para desencadenar el evento de negocio y configurar un flujo de trabajo. Para obtener más información, consulte [Alertas como eventos de negocio](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
