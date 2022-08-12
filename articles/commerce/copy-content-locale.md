---
title: Copiar contenido a otra configuración regional
description: Este artículo describe cómo copiar contenido existente a otra configuración regional dentro de un sitio en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126457"
---
# <a name="copy-content-to-another-locale"></a>Copiar contenido a otra configuración regional

[!include[banner](../includes/banner.md)]

Este artículo describe cómo copiar contenido existente a otra configuración regional dentro de un sitio en el generador de sitios de Microsoft Dynamics 365 Commerce.

Cuando crea contenido en el generador de sitios de Commerce, siempre se asocia con un identificador de configuración regional, como "en-us". Puede copiar páginas y activos individuales a una configuración regional diferente dentro del mismo sitio de comercio electrónico cambiando la configuración regional cuando edita un elemento de contenido y luego creando una nueva variante del elemento. En algunos casos, como cuando está lanzando una configuración regional completamente nueva en su escaparate, tiene sentido duplicar todos los elementos de contenido en una configuración regional existente en la nueva configuración regional. Si la nueva configuración regional tiene el mismo idioma base que una de las configuraciones regionales existentes, puede usar la configuración regional existente como configuración regional de origen para la operación de copia de configuración regional. (Por ejemplo, las configuraciones regionales "en-us" y "en-au" usan el idioma inglés). De esta manera, ayuda a reducir el esfuerzo que se requiere para localizar el contenido en la nueva configuración regional.

Los siguientes procedimientos explican cómo agregar una nueva configuración regional a un canal existente, copiar todos los elementos de contenido de una configuración regional existente a una nueva configuración regional y supervisar el estado de una operación de copia de configuración regional.

## <a name="add-a-new-locale"></a>Agregar una nueva configuración regional

Para agregar una nueva configuración regional en el generador de sitios de Commerce, siga estos pasos.

1. En el generador de sitios de Commerce, vaya al sitio.
1. En el panel de navegación izquierdo, seleccione **Configuración del sitio** y después seleccione **Canales**.
1. En **Canal**, seleccione el canal al que desea agregar la nueva configuración regional.
1. En el cuadro de diálogo del canal que aparece a la derecha, seleccione **Agregar una configuración regional**.
1. En el cuadro de diálogo **Agregar una configuración regional**, en el campo **Configuración regional para soporte técnico**, seleccione una configuración regional.
1. Confirme que el valor de **Dominio** es correcto.
1. En **Ruta**, ingrese una ruta URL única (por ejemplo, **es-us** o **english-us**).
1. Seleccione **Aceptar**.
1. Cierre el cuadro de diálogo del canal.
1. En **Canal**, confirme que la nueva configuración regional aparece junto al canal correcto.
1. Seleccione **Guardar y publicar**.

> [!NOTE]
> Antes de que la nueva configuración regional pueda configurarse en el generador de sitios, debe agregarse al canal de tienda en línea asociado en Commerce Headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Copiar todos los elementos de contenido en una nueva configuración regional

Para copiar todos los elementos de contenido en una nueva configuración regional en el generador de sitios de Commerce, siga estos pasos.

1. En el generador de sitios de Commerce, vaya al sitio.
1. En el panel de navegación izquierdo, seleccione **Configuración del sitio** y después seleccione **Canales**.
1. En la barra de comandos, seleccione **Crear copia de configuración regional desde**.
1. En el cuadro de diálogo **Crear copia local** que aparece a la derecha, en **Sitio de origen**, confirme que se ha seleccionado el sitio correcto.
1. En el campo **Canal de origen**, seleccione el canal de origen.
1. En el campo **Canal de destino**, seleccione el mismo canal de origen.
1. En el campo **Configuración regional del origen**, seleccione la configuración regional del origen.
1. En el campo **Configuración regional del destino**, seleccione la nueva configuración regional.
1. Seleccione **Copiar configuración regional**. Una notificación confirma que se ha iniciado la operación de copia de configuración regional.

> [!NOTE]
> También puede copiar contenido entre diferentes canales.

## <a name="monitor-the-status-of-the-locale-copy"></a>Supervisar el estado de la copia de configuración regional

Para supervisar el estado de una operación de copia de configuración regional, siga estos pasos.

1. En el generador de sitios de Commerce, vaya al sitio.
1. En el panel de navegación izquierdo, seleccione **Configuración del sitio** y después seleccione **Trabajos**.
1. En **Trabajos actuales**, seleccione el trabajo a supervisar. Los detalles del trabajo se muestran en el cuadro de diálogo que aparece a la derecha.
