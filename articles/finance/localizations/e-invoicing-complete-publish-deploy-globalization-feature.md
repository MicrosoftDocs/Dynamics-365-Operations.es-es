---
title: Completar, publicar e implementar una característica de globalización
description: Este artículo proporciona información acerca del ciclo de vida de las características de globalización.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 469fd66a5eaa779ea28ecfe4a29dd34d3ef748f5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846537"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Completar, publicar e implementar una característica de globalización

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Versiones de características de Facturación electrónica

Las características de facturación electrónica tienen versiones. Cuando se crea una nueva versión, el número de versión se incrementa automáticamente.

Las versiones de la característica de facturación electrónica siguen un ciclo de vida que tiene hasta tres estados:

- **Borrador**: si una versión de característica tiene este estado, puede editar sus atributos de configuración y sus artefactos (por ejemplo, configuraciones de formato de archivo).
- **Completo**. este estado indica que ha terminado de editar la versión de la característica y no tiene la intención de realizar más actualizaciones. Cunado una versión de característica tiene este estado, ya no podrá editarlo ni tampoco a ninguno de sus componentes.
- **Publicado**: este estado indica que la versión de la característica se ha publicado en el repositorio global asociado a su organización. Cunado una versión de característica tiene este estado, ya no podrá editarlo ni tampoco a ninguno de sus componentes.

Puede especificar una fecha **Válido desde** para una nueva versión de una característica de facturación electrónica. De esta manera, puede definir una versión predeterminada que se puede usar o que se puede sobrescribir cuando la característica se implementa en el entorno del servicio.

Para cambiar el estado de una versión de característica de facturación electrónica, siga estos pasos.

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En el lado izquierdo de la página **Características de facturación electrónica**, seleccione la característica de facturación electrónica.
4. En la pestaña **Versiones** del lado derecho de la página, seleccione la versión.
5. Seleccione **Cambiar estado** y luego seleccione **Completo** (si el estado actual es **Borrador**) o **Publicado** (si el estado actual es **Completo**).
6. En el cuadro de mensaje, seleccione **Sí** para confirmar la solicitud.

El cambio manual del estado **Completo** a **Publicado** es opcional. Las versiones de la característica de facturación electrónica se actualizan automáticamente al estado **Publicado** cuando se implementan en el entorno de servicio.

Puede realizar un seguimiento del estado en la columna **Estado de la versión de la característica** en la pestaña **Versiones**.

## <a name="deploy-feature-versions"></a>Implementar versiones de características

En RCS, utilice el comando **Implementar** para publicar una versión de la característica de facturación electrónica en el entorno de servicio de destino o en la aplicación conectada.

1. En el lado izquierdo de la página **Características de facturación electrónica**, seleccione la característica de facturación electrónica.
2. En la pestaña **Versiones** del lado derecho de la página, seleccione la versión de la característica de facturación electrónica que desea implementar en el entorno de servicio o la aplicación conectada. La versión seleccionada debe tener un estado de **Completo** o **Publicado**.
3. Seleccione **Implementar** y luego seleccione una o ambas de las siguientes opciones para definir el destino de la implementación:

    - **Aplicación conectada**: la configuración proporcionada por la configuración de la aplicación está escrita en la instancia de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management que estaba asociada asociada anteriormente con ella.
    - **Entorno de servicio**: la versión de la característica de facturación electrónica se implementa en el entorno de servicio. La facturación electrónica está lista para recibir y procesar documentos electrónicos enviados por Finance o Supply Chain Management.

> [!NOTE]
> Por lo general, cambiará los parámetros de la característica de Informes electrónicos (ER) que debe implementarse en el entorno de servicio. Los cambios en la aplicación conectada serán inusuales. Debe implementar nuevas versiones en la aplicación conectada solo cuando cambie los parámetros correspondientes de su aplicación.

Para determinar si una versión específica de una característica de facturación electrónica se implementa en un entorno específico, revise la información en la pestaña **Entornos**.

## <a name="remove-feature-versions"></a>Eliminar versiones de características

En RCS, puede seleccionar **Cancelar** para eliminar una versión específica de la característica de facturación electrónica de un entorno de servicio, si estaba implementada ahí.

> [!IMPORTANT]
> El botón **Cancelar** solo funciona para entornos de servicio. No elimina nada de la aplicación conectada para la característica de facturación electrónica.

## <a name="rebase-electronic-invoicing-features"></a>Nueva base de características de facturación electrónica

Cuando una característica de facturación electrónica se deriva de otra, puede seleccionar **Nueva base** para actualizar la característica derivada con los cambios que se han realizado en la característica (primaria) original.

Para la nueva base de una versión derivada de una característica que creó, siga estos pasos.

1. Obtenga la última versión de la característica importándola desde el repositorio global. Para obtener más información, consulte [Importar característica del repositorio global](e-invoicing-import-feature-global-repository.md).
2. En la lista de características, seleccione la característica para cambiar de base.
3. En la pestaña **Versiones**, seleccione **Nuevo** para crear una versión de borrador.
4. Seleccione **Cambiar de basee**.
5. En el cuadro de diálogo **Cambiar de base**, seleccione la versión de la característica a cambiar de base.
6. Seleccione **Aceptar**.
7. Revise los componentes de la característica y realice los cambios necesarios.
8. Seleccione **Cambiar Estado** para completar la característica cambiada de base. Cuando se completa el cambio de base, puede realizar acciones adicionales.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Obtener una versión específica de las características de facturación electrónica

Cuando crea una nueva versión de una característica de facturación electrónica, el sistema crea una copia de la última versión de la característica. Para usar una versión anterior de la característica como base para una nueva versión, seleccione la versión y luego seleccione **Obtener este comando de versión**. Se crea una nueva versión de borrador de la característica que es una copia de la versión seleccionada.
