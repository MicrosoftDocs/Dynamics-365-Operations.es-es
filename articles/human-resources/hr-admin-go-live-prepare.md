---
title: Prepararse para poner en marcha Human Resources
description: Esta página proporciona orientación sobre cómo prepararse para la puesta en marcha con Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dcec7963bdf70f848249bb2ca5e2208e09f49548
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054797"
---
# <a name="prepare-for-human-resources-go-live"></a>Prepararse para poner en marcha Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]

En este tema se explica cómo prepararse para la puesta en marcha con un proyecto de Dynamics 365 Human Resources mediante Microsoft Dynamics Lifecycle Services (LCS). 

Este gráfico muestra las fases del proceso de puesta en marcha. 

![Proceso de puesta en marcha](./media/hr-admin-go-live-prepare-process.png)

En la tabla siguiente se enumeran todos los pasos del proceso y se especifican la duración esperada y quién es responsable de la acción.

| Fase | Acción | Duración/Cuándo | Quién | Notas |
| --- | --- | --- | --- |--- |
| 1 | Actualizar la fecha de puesta en marcha en LCS | Con un adelanto mínimo de 2-3 | Partner/Cliente | Las fechas de los hitos deben mantenerse actualizadas de forma continua. |
| 2 | Completar y enviar la lista de comprobación | Después de que se haya completado la prueba de aceptación de usuarios (UAT). | Partner/Cliente | Siga las instrucciones proporcionadas en [Evaluación de la puesta en marcha de FastTrack](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Evaluación de proyectos (FastTrack) | Arquitecto de FastTrack* | El arquitecto asesora después de que se reciba la lista de comprobación y continúa con la revisión hasta que se aclaren las preguntas y se implementen las mitigaciones, si corresponde. |
| 4 | Taller de proyectos (FastTrack) | Arquitecto de FastTrack* | |
| 5 | Importaciones de paquetes de datos | Depende del proyecto | Partner/Cliente | Siga las instrucciones de [Visión general de la administración de datos](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).|
| 6 | Preparado para producción | Una vez que se hayan completado todos los pasos anteriores | Partner/Cliente | El partner/cliente puede tomar el control del entorno de producción.|
| 7 | Actividades de transferencia | Depende del proyecto | Partner/Cliente | |
| 8 | Puesta en marcha | Depende del proyecto | Cliente  | |

> [!IMPORTANT]
> * Los pasos 3 y 4 solo se completan para los clientes aptos para FastTrack.

## <a name="completing-the-lcs-methodology"></a>Completar la metodología LCS

Un hito importante en cada proyecto de implementación es la transferencia al entorno de producción. El proceso de completar un paso tiene dos partes: 

- Realizar el trabajo real, como un análisis de idoneidad/lagunas o una prueba de aceptación de usuarios (UAT). 
- Marque el paso correspondiente en la metodología LCS como completado. 

Es recomendable completar los pasos de la metodología a medida que se avanza en la implementación. No espere hasta el último minuto. Lo mejor para el cliente es tener una implementación sólida. 

## <a name="uat-for-your-solution"></a>UAT para su solución

Durante la fase de UAT, debe probar todos los procesos comerciales que ha implementado y cualquier personalización que haya realizado en un entorno de espacio aislado en el proyecto de implementación. Para ayudar a garantizar una puesta en marcha exitosa, debe considerar lo siguiente al completar la fase UAT: 

- Recomendamos que su proceso de UAT comience con un entorno limpio y fresco donde los datos de su configuración GOLD se copien en el entorno antes del inicio del proceso de UAT. Le recomendamos que utilice el entorno de producción como su entorno GOLD hasta la puesta en marcha, momento en el que el entorno se convierte en producción.
- Los casos de prueba cubren todo el ámbito de los requisitos. 
- Pruebe a utilizar datos migrados. Estos deben incluir datos como de trabajadores, trabajos y puestos. También incluya los saldos iniciales, como la acumulación de bajas y ausencias. Por último, incluya transacciones abiertas, como inscripciones a las prestaciones actuales. Realice pruebas con todo tipo de datos, aunque el conjunto de datos no esté finalizado. 
- Pruebe a utilizar los roles de seguridad correctos (roles predeterminados y roles personalizados) que se asignan a los usuarios. 
- Asegúrese de que la solución cumpla con los requisitos reglamentarios específicos de la empresa y la industria. 
- Documente todas las funciones y obtenga la aprobación y el visto bueno del cliente. 

## <a name="mock-go-live"></a>Simulación de la puesta en marcha

Antes de la puesta en marcha, debe realizar una simulación de la puesta en marcha para probar los pasos necesarios para la transición de sus sistemas heredados al nuevo sistema. Debe realizar su simulación de la puesta en marcha en un entorno de espacio aislado e incluir todos los pasos en su plan de transición.

- Le recomendamos que utilice el entorno de producción como entorno de configuración GOLD hasta la puesta en marcha.
- Asegúrese de contar con un sólido proceso de gobernanza para proteger el entorno de producción de transacciones accidentales o actualizaciones antes de la puesta en marcha.
- Cuando esté listo para realizar UAT o la puesta en marcha simulada, actualice el entorno de espacio aislado desde el entorno de producción. Para más información, consulte [Copiar una instancia](hr-admin-setup-copy-instance.md).
- Pruebe cada paso de su plan de transición en el entorno de espacio aislado y luego valide el entorno de espacio aislado realizando verificaciones al azar o realizando pruebas de sus scripts de UAT en el entorno.
  - Las pruebas deben incluir todas las migraciones de datos, incluidas las transformaciones necesarias para la puesta en marcha.
  - El proceso debe incluir un corte de práctica de cualquier sistema heredado.
  - Asegúrese de incluir cualquier paso de transición de integración o pasos del sistema externo en su transición simulada.
- Si encuentra algún problema durante la transición simulada, es posible que se requiera una segunda transición simulada. Por esta razón, le recomendamos que planifique dos transiciones simuladas en su plan de proyecto.

## <a name="fasttrack-go-live-assessment"></a>Evaluación de puesta en marcha de FastTrack

Los clientes aptos para FastTrack que estén trabajando con un arquitecto de soluciones FastTrack completarán una revisión de la puesta en marcha con Microsoft FastTrack. Para obtener más información, consulte  [Microsoft FastTrack](/dynamics365/fasttrack/). 

Aproximadamente ocho semanas antes de la puesta en marcha, el equipo de FastTrack le pedirá que rellene un [Lista de comprobación de puesta en marcha](https://go.microsoft.com/fwlink/?linkid=2146013).

El director del proyecto o un miembro clave del proyecto debe completar la lista de comprobación de puesta en marcha durante la fase previa a la puesta en marcha del proyecto. Por lo general, la lista de comprobación se completa de cuatro a seis semanas antes de la fecha de puesta en marcha propuesta, cuando la UAT se ha completado (o casi). 

Cuando haya completado la lista de comprobación de puesta en marcha, envíela por correo electrónico a su arquitecto de soluciones FastTrack. Incluya siempre en el correo electrónico una parte interesada esencial del cliente y el partner de implementación. 

Después de enviar la lista de comprobación, su arquitecto de soluciones FastTrack revisará el proyecto y proporcionará una evaluación que describa los riesgos potenciales, las prácticas recomendadas y las recomendaciones para implementar correctamente el proyecto. En algunos casos, el arquitecto de la solución puede resaltar los factores de riesgo y solicitar un plan de mitigación. 

## <a name="see-also"></a>Consulte también

[Preguntas frecuentes sobre la publicación](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
