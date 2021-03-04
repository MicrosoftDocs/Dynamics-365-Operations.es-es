---
title: Generar informes agregando contenido como XML sin formato
description: Puede diseñar formatos de informes electrónicos (ER) que generan documentos salientes en formato XML.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 824d6bdf53cacbd81004a009e4019b5ab7e5cff0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686738"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Generar informes agregando contenido como XML sin formato

[!include[banner](../includes/banner.md)]

Puede utilizar el nuevo elemento del formato **XML SIN FORMATO** para diseñar formatos de informes electrónicos (ER) que generan documentos salientes en formato XML. En algunos casos, es posible que prefiera agregar datos XML sin formato a estos informes por uno o más de los siguientes motivos:

- Es más conveniente usar un XML sin formato para el diseño original y el mantenimiento continuo de un informe, ya que la estructura XML puede generarse automáticamente mediante la ejecución de una expresión de tiempo de ejecución. Por lo tanto, múltiples enlaces no tienen que determinase para varios elementos de formato en el tiempo de diseño. Es posible cuando los orígenes de datos que utiliza contienen la información que se puede usar para hacer los elementos XML a medida que se genera el informe.
- No se pueden utilizar ningún otro método para rellenar el informe con el contenido de XML que se recibió y almacenó previamente en el sistema. Por ejemplo, es posible que la respuesta XML que se genera tenga que contener el contenido de una solicitud XML que se envió anteriormente.
- No se puede utilizar ningún otro método para insertar los caracteres en el documento generado en función de sus códigos numéricos. Para algunos idiomas y caracteres, los códigos de este tipo no existen. Los ejemplos incluyen la letra griega rho (ρ) y los códigos de entidad de HTML como \&eacute; para una *e* que tiene un acento agudo (é).

> [!NOTE]
> Tenga en cuenta que el marco no controla si el contenido de XML que se coloca en el documento generado mediante el elemento del formato **XML SIN FORMATO** es correcto.

Para obtener más información acerca de esta función, reproduzca las guías de tareas **ER Usar datos XML sin formato para generar informes XML (Parte 1: Modelo de datos de diseño)** y **ER Usar datos XML sin formato para generar informes XML (Parte 2: Diseñar y ejecutar informe)**, que forman parte del proceso empresarial **7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677)** y se puede descargar del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Estas guías de tareas le guían por el proceso de configuración de un formato de ER para insertar datos XML sin formato en los archivos generados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]