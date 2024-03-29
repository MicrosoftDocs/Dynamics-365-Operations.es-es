---
title: Estados y ciclo de vida de documentos
description: En este artículo se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: intro-internal
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 350b3236eec6ad6520025bf44b22f12366f1e266
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269926"
---
# <a name="document-states-and-lifecycle"></a>Estados y ciclo de vida de documentos

[!include [banner](includes/banner.md)]

En este artículo se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descripciones de estado de documento

El artículo [Elementos de página](page-elements-overview.md) muestra diversos tipos de documentos en el sistema de gestión de contenidos (CMS). Estos tipos de documento pueden tener varios estados en la herramienta de creación. Los estados de documentos ayudan a evitar conflictos de datos y a aplicar el control de versiones. Determinan quién puede cambiar los documentos, cuándo se pueden cambiar los documentos y cuándo se pueden ver los cambios por otras personas.

En la tabla siguiente se muestran los posibles estados de documentos de elementos de página en Commerce.

| Estado del documento      | Acción generador de sitios        | Descripción                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Comprado         | Seleccione **Editar**.           | El documento correspondiente se le ha retirado. Mientras un documento está en este estado, no puede ser modificado por otros usuarios autenticados del sistema y cualquier cambio que realice en el documento será visible solo para usted. |
| Guardado               | Seleccione **Guardar**.           | Los cambios que se han realizado en un documento desprotegido se guardan en la base de datos, pero el documento aún no se ha registrado ni publicado. Los cambios guardados no son visibles para otros usuarios del sistema autenticados hasta que el autor selecciona **Finalizar edición**. No están visibles para usuarios externos hasta que se publica el artículo. |
| Desprotección descartada | Seleccione **Descartar ediciones**.  | Todos los cambios en el documento desprotegido se descartan y el elemento vuelve a la última versión que se registró. |
| Entrada registrada          | Seleccione **Finalizar edición**. | El documento editado está registrado. Todos los cambios son visibles para otros usuarios del sistema autenticados, y esos usuarios pueden editar el documento. Cada protección crea un registro de versión de documento en el historial del artículo. |
| Publicadas           | Seleccione **Publicar**.        | El documento se publica y los cambios se envían a su sitio en vivo y los usuarios externos pueden descubrirlos. Los elementos solo se pueden publicar si se registraron primero seleccionando **Finalizar edición**. |

## <a name="additional-resources"></a>Recursos adicionales

[Métodos para agregar contenido](add-manage-content.md)

[Glosario del modelo de página](page-elements-overview.md)

[Trabajar con grupos de publicación](publish-groups.md)

[Habilitar y usar el uso compartido entre canales](cross-channel-sharing.md)

[Trabajar con módulos](work-with-modules.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Personalizar navegación del sitio](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
