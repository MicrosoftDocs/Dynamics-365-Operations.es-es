---
title: Publicar trabajos en LinkedIn desde Attract
description: Este tema explica cómo usar Dynamics 365 Talent - Attract para registrar trabajos en LinkedIn.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 782a2e5de6edf0e85c4d32a0910f5f3c01981a01
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462439"
---
# <a name="post-jobs-to-linkedin-from-attract"></a>Publicar trabajos en LinkedIn desde Attract

[!include [banner](includes/banner.md)]

LinkedIn es la mayor red profesional conectada, que da acceso al talento superior del mundo. Microsoft Dynamics 365 Talent: Attract ayuda a obtener el talento que necesita dejándole enviar sus trabajos directamente de Attract a LinkedIn.

Attract le permite enviar listas limitadas a LinkedIn sin gasto extra alguno. Estas listas solo están disponibles a través de socios de software de LinkedIn como Attract. No aparecen en el panel **Carreras** en la página de LinkedIn de la empresa, ya que ahí sólo aparecen listas pagadas. Sin embargo, se muestran donde los candidatos potenciales pueden ver todos los trabajos disponibles. Las listas limitadas también se muestran en búsquedas de trabajo de LinkedIn.

Tras [crear un trabajo](./creating-jobs-attract.md) en Attract, sólo tiene que seleccionar un botón para poner el trabajo delante de millares de candidatos potenciales en LinkedIn.

En la tabla siguiente se muestran las acciones que puede realizar en LinkedIn, en función de su rol de usuario.

| Función | Acciones que puede realizar |
|---|---|
| Administrador | Registrar, volver a registrar y anular un registro |
| Responsable de contratación | Solo lectura |
| Contratante | Registrar, volver a registrar y anular un registro |
| Entrevistador | Sin acceso |
| Sólo lectura | Solo lectura |

Para obtener más información sobre roles de usuario en Attract, consulte [Seguridad y gestión de roles en Attract](./security-attract.md).

Si es un administrador y necesita obtener más información sobre cómo configurar la integración de LinkedIn con Attract, consulte [Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

Los trabajos que se registran en LinkedIn aparecen en el sitio de LinkedIn activo. LinkedIn no tiene un entorno de prueba para registrar trabajos. Por lo tanto, asegúrese de que no registra accidentalmente trabajos de prueba.

## <a name="post-jobs-to-linkedin"></a>Publicar ofertas de empleo en LinkedIn

1. En Attract, abra el trabajo que desee registrar en LinkedIn.
2. En la pestaña **Registros**, seleccione el botón **Registrar ahora** que corresponde a LinkedIn.

    [![Registrar trabajo de Attract en LinkedIn](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)

3. En el cuadro de diálogo **Crear una dirección web para operaciones del tipo "aplicar ahora"**, seleccione una opción en **Los candidatos pueden realizar la solicitud mediante**. Es recomendable seleccionar **Enlace en Attract**.
4. Seleccione **Listo**.
5. En el cuadro de mensaje **Enviar para registro**, seleccione **confirmar**.

Una vez que LinkedIn complete con éxito correctamente el registro, la sección **Registros** del trabajo en Attract muestra el estado de LinkedIn como **Registrado**. El trabajo puede tardar hasta 48 horas en aparecer en LinkedIn.

Cuando los candidatos interesados seleccionan **Ver** junto a la lista, verán los detalles completos del trabajo, junto con su información acerca de cómo solicitarlo.

Todos los registros de trabajo que se realizan con Attract son listas limitadas. Para obtener más información sobre las listas limitadas en LinkedIn, consulte [Listas limitadas y registros de trabajos premium para el ajuste de trabajo](https://www.linkedin.com/help/recruiter/answer/79049).

Si está teniendo problemas para registrar trabajos en LinkedIn consulte [Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

## <a name="see-also"></a>Consulte también

[Integración de Attract con preguntas frecuentes de LinkedIn](./attract-linkedin-faq.md)

[Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Crear, aprobar y registrar trabajos en Attract](./creating-jobs-attract.md)

[Conseguir candidatos con LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Solucionar problemas de integración con LinkedIn](./attract-troubleshoot-linkedin.md)
