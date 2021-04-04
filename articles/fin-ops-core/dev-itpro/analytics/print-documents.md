---
title: Visión general de la impresión de documentos
description: Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red. Este artículo proporciona una visión general de cómo se imprimen los documentos.
author: TJVass
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c349e50826aa577ce6a3b8a68676d549f7fed1b1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564414"
---
# <a name="document-printing-overview"></a>Visión general de la impresión de documentos

[!include [banner](../includes/banner.md)]

Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red. Este artículo proporciona una visión general de cómo se imprimen los documentos.

## <a name="printing-overview"></a>Visión general de la impresión

La aplicación proporciona los servicios integrados y las aplicaciones cliente que facilitan la generación, el almacenamiento y la distribución de documentos que respaldan la actividad empresarial. Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red. Además, puede exportar páginas e informes directamente desde el cliente, como archivos PDF o documentos de Microsoft Office. Finalmente, la carga de trabajo distribuida le permite imprimir documentos empresariales directamente desde un dispositivo móvil mediante el uso de recursos de red. Aunque los requisitos de impresión pueden variar, normalmente todas las industrias deben crear copias impresas de documentos empresariales mediante la aplicación. La impresión de documentos en dispositivos de red desde aplicaciones hospedadas presenta un conjunto exclusivo de retos. A continuación se incluyen algunos ejemplos:

- Puede que los controladores de impresión no estén disponibles en el dispositivo del usuario.
- Puede que el dispositivo del usuario no esté conectado a la red corporativa.

Al utilizar el host dedicado y tras unos sencillos pasos, los administradores del sistema pueden configurar las implementaciones de modo que los usuarios puedan imprimir directamente desde aplicaciones empresariales en los dispositivos de red.

### <a name="application-printing-scenarios"></a>Situaciones de impresión de la aplicación 

La siguiente tabla describe los tres escenarios principales de impresión.

| Situación                        | Objetivo                                                      | Solución |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. Imprimir lo que ve        | Imprima lo que se muestra actualmente en el explorador.             | Se genera una versión "fácil de imprimir" de la página web para el explorador. |
| 2. Impresión interactiva         | Imprima un documento de precisión en un dispositivo conectado a nivel local. | Puede exportar una versión PDF del informe y descargarla en el explorador. |
| 3. Impresión en un dispositivo de red | Envíe un documento de precisión a una impresora de dominio.     | Un documento de precisión se envía a una aplicación cliente que se ejecuta en un servidor que se hospeda en el dominio del cliente. |

Dado que la solución varía en función del escenario, las aplicaciones proporcionan servicios y herramientas integradas para ayudar a los usuarios a cumplir sus objetivos:

- El **Escenario 1** es compatible con la representación del explorador del cliente HTML5.
- El **Escenario 2** usa aplicaciones cliente y servicios de Microsoft 365.
- El **Escenario 3** requiere soporte desde aplicaciones cliente y desde servicios que se hospedan en Microsoft Azure.

Además de la plataforma que se implementa en la suscripción de Azure, las aplicaciones de Finance and Operations proporcionan a los clientes una aplicación de Azure integrada propia que les ayuda a utilizar con más facilidad dispositivos hospedados en dominios para imprimir documentos.

## <a name="service-overview"></a>Visión general de servicios
Aunque los documentos producidos por las aplicaciones hospedadas están esperando para ser impresos en un dispositivo conectado a la red, estos se guardan en el almacenamiento de blobs de Azure. El [Agente de instalar ruta de documentos para habilitar la impresión de red](install-document-routing-agent.md) utiliza la autenticación de Azure para establecer un canal seguro para los servicios de Azure.

**Secuencia de ejecuciones**

1. El informe es generado por Microsoft SQL Server Reporting Services (SSRS) y almacenado en el almacenamiento de blobs de Azure. La configuración de la impresora adjunta se almacena junto con el documento.
2. El Agente de rutas de documentos consulta la cola de Azure Service Bus para los trabajos activos.
3. El documento es descargado por el Agente de rutas de documentos y se pone en la cola de la impresora de red.

La solución basada en cliente permite a los clientes administrar la escala de sus necesidades de impresión. Los clientes que tengan cargas de trabajo de impresión de gran volumen pueden instalar muchos Agentes de rutas de documentos para aumentar el número de operaciones de impresión simultáneas. De manera alternativa, algunos clientes requieren muy pocas instalaciones del Agente de rutas de documentos para administrar sus necesidades de impresión anticipadas.

### <a name="service-components-for-network-printing"></a>Componentes de servicio para la impresión de red

En el siguiente diagrama se muestran los componentes básicos que ayudan con las operaciones de impresión de red.

[![componentes de servicio para la impresión de red\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

Tenga en cuenta que una sola impresora se puede registrar con varios agentes de ruta de documento. Para resolver las preferencias de la impresora, el servicio hospedado utiliza la ruta de red que identifica de manera única a cada impresora de red. Como resultado, incluso cuando una impresora es registrada por varios clientes, aparece como única selección en la lista de impresoras disponibles en las aplicaciones.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]