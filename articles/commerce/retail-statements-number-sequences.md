---
title: Configurar secuencias numéricas para extractos comerciales
description: Este artículo describe cómo configurar las secuencias numéricas que se requieren para extractos comerciales en Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 5c4eb872ec2151a9f4ac5462ad43dd03a6705487
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880012"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Configurar secuencias numéricas para extractos comerciales

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artículo describe cómo configurar las secuencias numéricas que se requieren para extractos comerciales en Microsoft Dynamics 365 Commerce.

Se utilizan dos tipos de extractos comerciales en Dynamics 365 Commerce: 

- Los **extractos transaccionales** están pensados para crear y publicar con una alta frecuencia. Se utilizan para contabilizar todas las transacciones no financieras en la tienda con la sede de Dynamics 365 Commerce. 
- Los **informes financieros** están pensados para crear y publicar una vez por día hábil. Incluyen solo los turnos cerrados de las tiendas minoristas que se cargaron en la sede de Commerce a través del trabajo P.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Configurar una secuencia numérica para registro de extractos

Una vez que haya completado la configuración de una tienda minorista, en la sede de Commerce, debe configurar una secuencia numérica única que se usará para los extractos durante el proceso de creación de extractos.

Para configurar una secuencia numérica para la publicación de extractos en la sede Commerce, siga estos pasos.

1. Vaya a **Administración de la organización \> Secuencias numéricas \> Secuencias numéricas**.
1. Seleccione **Nuevo \> Secuencia numérica** para crear un nuevo registro.
1. En la ficha desplegable **Identificación**, en el campo **Código de secuencia numérica**, ingrese un código de secuencia numérica.
1. En el campo **Número de secuencia numérica**, especifique un nombre.
1. En la ficha desplegable **Parámetros del ámbito**, en el campo **Ámbito**, seleccione **Unidad operativa**.
1. En el campo **Unidad operativa**, seleccione la tienda para la que se utilizará la secuencia numérica.
1. En la ficha desplegable **Segmentos**, define los segmentos.
1. En la ficha desplegable **Referencias**, establezca el campo **Área** como **Tienda**.
1. Establezca el campo **Referencia** como **Número de extracto** y luego seleccione **Aceptar**.

    ![Fichas desplegables Identificación, Parámetros de ámbito, Segmentos y Referencias en la página Secuencias numéricas.](media/retail-statements-num-seq-setup-01.png)

1. En la ficha desplegable **General**, en la sección **Asignación de número**, actualice los campos **La más pequeña** y **La más grande** para que coincidan con la longitud del segmento **Alfanumérico** que ha definido en la ficha desplegable **Segmentos**.
1. En la ficha despleable **Rendimiento**, le recomendamos que configure la opción **Preasignación** como **Sí** y el campo **Cantidad de números** como **25**.

    ![Fichas desplegables General y Rendimiento en la página Secuencias numéricas.](media/retail-statements-num-seq-setup-02.png)

1. En el Panel de acciones, seleccione **Guardar** para guardar los cambios y cerrar la página.
