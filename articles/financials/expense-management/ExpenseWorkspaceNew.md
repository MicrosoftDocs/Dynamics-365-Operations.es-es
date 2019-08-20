---
title: Informes de gastos reinventados
description: Este tema proporciona información sobre la experiencia reajustada y reinventada para la entrada del informe de gastos en Microsoft Dynamics 365 for Finance and Operations. La nueva experiencia simplifica el proceso de completar informes de gastos y reduce el tiempo requerido.
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 320984fc6be231c941df17abb7246e92f6aa4b9a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841066"
---
# <a name="expense-reports-reimagined"></a>Informes de gastos reinventados

[!include[banner](../includes/banner.md)]

La entrada del informe de gastos se ha rediseñado para simplificar el proceso de completar informes de gastos y reducir el tiempo requerido. Estos son los componentes principales de la nueva experiencia de gastos:

- Un nuevo espacio de trabajo de gestión de gastos que permite a su delegado el acceso a los gastos.
- Una nueva experiencia de relación de recepción para mejorar la presentación de recepciones a nivel de encabezado y para simplificar el proceso de adjuntar recibos a las líneas de gastos.
- Una nueva cuadrícula de sólo lectura que permite ver muchas más líneas de gastos y columnas de datos adicionales. Ahora puede ver todas las líneas detalladas y divididas, así como los gastos principales.
- Un panel simplificado para editar los gastos.
- Rediseño de los mensajes de error, advertencia, y directiva para ayudar a garantizar que tiene el contexto correcto para comprender cuál es el problema y cómo resolverlo. Microsoft ha quitado muchos mensajes que aparecían antes de que los usuarios tuvieran una oportunidad de completar sus tareas y de abordar los problemas, como el mensaje incompleto del detalle.
- Una nueva página para especificar qué campos son obligatorios para su organización, que campos son opcionales, y qué campos no deberían capturarse. Esta página ayudará a reducir el número de campos que los usuarios deben liquidar.
- Un nuevo aspecto y funcionamiento para los informes de gastos, de modo que ya no parezcan diseñados para el personal de contabilidad.

Para activar la nueva experiencia, utilice el espacio de trabajo **Administración de características** para activar la función **Informes de gastos reimaginados** . Al activar esta característica ocurren las acciones siguientes:

- El espacio de trabajo existente de gastos se reemplaza con el nuevo espacio de trabajo.
- Un nuevo elemento de menú para la visibilidad del campo de gastos se agrega.
- No se quita ningún elemento existente del menú de informes de gastos (la página ya existente) ni campos del informe de gastos.
- Los flujos de trabajo y la aprobación aún le llevan a la página existente de los informes de gastos.

## <a name="getting-started-video-for-new-users"></a>Vídeo de iniciación para nuevos usuarios

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Y7gO]

El vídeo [Experiencia de gastos en Dynamics 365 for Finance and Operations](https://youtu.be/Ocy-MsTvEE0) (aparece más arriba) está incluido en la  [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibles en YouTube.

## <a name="new-features"></a>Nuevas características

| Característica nueva | Descripción |
|---|----|
| Visibilidad del campo de gastos | Una nueva página de configuración le permite especificar los campos que se deben deshabilitar para una organización, los campos que deben ser necesarios y qué campos son recomendables. |
| Campos obligatorios | La nueva configuración simple permite crear algunos campos obligatorios sin tener que usar el marco de directiva. |
| Campos opcionales | Una segunda página para los campos opcionales se agrega. De esta manera, los empleados no sentirán como si debieran establecer los campos, pero acceder a los campos sigue siendo fácil. |
| Agregar recibos no adjuntados | La capacidad de agregar recibos no adjuntados al informe de gastos estará más visible del espacio de trabajo y en el informe de gastos. |
| Mensajería mejorada | Hay una mejor visibilidad en las líneas de gastos que tengan advertencias o errores. |
| Reducción en los mensajes en la barra de mensajes| El número de mensajes del registro de información ha disminuido, y se ha realizado un esfuerzo para evitar que aparezcan los mensajes duplicados en muchos casos. |
| Acciones comunes agrupadas juntas | La interfaz se ha limpiado con la adición de las nuevas acciones en los botones de la mayoría de las acciones comunes de nivel de línea y la adición de puntos suspensivos (...) para la cabecera y otros acciones menos frecuentes. |
| Nuevo espacio de trabajo para aumentar la visibilidad | Un nuevo espacio de trabajo unifica las funciones y los vínculos que permiten a los usuarios pasar a las distintas áreas. |
| Agregue los gastos y los recibos existentes durante la creación de gastos | Cuando se crean informes de gastos, puede agregar todos los gastos seleccionado y recibos. |
| Calculadora del tipo de cambio | Se agrega una calculadora del tipo de cambio que permite calcular el tipo de cambio para las transacciones de gastos menores en transacciones multidivisa. |
| Guardar y agregar nuevas líneas de gastos | Los botones **Guardar** y **Nuevo** están disponibles cuando se especifican los nuevos gastos, para ayudarle a introducir rápidamente líneas de gastos. |
| Una mejor visibilidad en las líneas detalladas y divididas | Las líneas detalladas y divididas se agregan directamente a la lista de gastos, para aumentar la visibilidad y ayudarle a determinar fácilmente si hay errores de directivas u otros errores. |
| Muestra los recibos durante el detallado | Los recibos pueden mostrarse durante el detallado. |

La versión inicial se centra en los escenarios de la entrada de gastos. Cualquier escenario de revisión o aprobación de informe de gastos seguirá usando la página existente de la entrada de gastos.

Las siguientes características están presentes en la página existente pero aún no están presentes en la nueva página. Estas características serán reintroducidas durante varias versiones siguientes:

- Aprobaciones
- Aprobación de los proveedores y la capacidad para editar la contabilidad
- Varios puntos de entrada
- Integración de la solicitud de viaje
- Visibilidad de la entidad de datos para el campo de gastos
- Entrada de gastos de dietas
- Flujo de trabajo de nivel de línea
- Soporte para aprobador provisional
- Detalles avanzados
