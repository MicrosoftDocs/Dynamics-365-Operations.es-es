---
title: Evitar truncamiento del texto en la jerarquía de puestos y exportar a Visio
description: Este tema explica cómo resolver un problema en el que los nombres de personas y de puestos se truncan cuando los clientes ven la jerarquía de puestos en Microsoft Dynamics 365 Talent. El truncamiento de texto puede hacer difícil tomar una captura de pantalla o imprimir la jerarquía.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e151818f29ac37ff449daaf1dc02e44b8fb317c3
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008509"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Evitar truncamiento del texto en la jerarquía de puestos y exportar a Visio

[!include [banner](includes/banner.md)]

**Emisión**

Cuando los clientes ven la jerarquía de puestos en Microsoft Dynamics 365 Talent, los nombres de personas y puestos se truncan. Por lo tanto, puede resultar difícil tomar una captura de pantalla, o imprimir y distribuir la jerarquía.

![Jerarquía de puestos](media/position-h.png)

**Causa**

Este comportamiento se debe al diseño.

**Resolución**

Desafortunadamente, los usuarios no pueden cambiar fácilmente el tamaño de texto. Sin embargo, puede exportar la jerarquía de puestos fuera de Talent y después importarla a Microsoft Visio. Aunque el artículo siguiente se escribió para Microsoft Dynamics AX 2012, el proceso también se aplica a Talent: [Exportar una jerarquía de puestos a Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Siga estos pasos para exportar a Visio.

1. En Talent abra la página de lista **Puestos**.

    Para incluir obtener más información en el gráfico de la estructura de la organización, agregue campos a la lista **Puestos** , de modo que estén disponibles cuando utilice el asistente más adelante en este procedimiento.

2. En el panel de acciones, seleccione el botón **Abrir en Microsoft Office** y, a continuación, en **Exportar a Excel**, seleccione **Puestos**. Como alternativa, presione Ctrl+T.

    ![Exportación de la página de lista de puestos a Excel](media/org-admin.png)

3. Guarde el archivo de Excel que se exporta.

    ![Exportación al cuadro de diálogo de Excel](media/export-excel.png)

4. En Visio, seleccione **Visio - Crear nuevo**, y seleccione la categoría de plantilla **Negocio**.

    ![Nuevo gráfico](media/new.png)

5. Seleccione **Asistente para organigramas**, y después seleccione **Crear**.

    ![Cuadro de diálogo del Asistente para organigramas](media/orgchart-wizard.png)

6. Seleccione **Información que ya está guardada en un archivo o una base de datos**, y después seleccione **Siguiente**.

    ![Asistente para Organigrama 1](media/orgchart-wizard7.png)

7. Seleccione **Un archivo de texto, Org Plus (\*.txt), o Excel** y, a continuación seleccione **Siguiente**.

    ![Asistente para Organigrama 2](media/orgchart-wizard3.png)

8. Explore para seleccionar el archivo de Excel exportado que contiene la jerarquía de puestos, y después selecciona **Siguiente**.

    ![Asistente para Organigrama 3](media/orgchart-wizard2.png)

9. Establezca el campo **Nombre** en **Puesto**, establezca el campo **Informa a** en **Notifica al puesto** y continuación seleccione **Siguiente**.

    ![Asistente para Organigrama 4](media/orgchart-wizard1.png)

10. Seleccione los campos que se deben mostrar en cada nodo y, a continuación seleccione **Siguiente**.

    ![Asistente para Organigrama 5](media/orgchart-wizard5.png)

11. Agregue la columna **Puesto** a la lista **Campos de los datos de formas** y, a continuación, seleccione **Siguiente**.

    ![Asistente para Organigrama 6](media/orgchart-wizard6.png)

12. Las imágenes no se encuentran disponibles. Por tanto, en la siguiente página, seleccione **Siguiente**.
13. Seleccione **Deseo que el asistente divida automáticamente el organigrama entre las distintas páginas**.

    ![Asistente para Organigrama 7](media/orgchart-wizard4.png)

14. Seleccione **Fin**.

    Si existen algunos puestos que no están en la estructura, se le pedirá que los incluya en el diagrama.

El gráfico que se genera en Visio muestra a cada administrador en una hoja de cálculo propia.

Según los campos que incluya en el gráfico, cada nodo muestra la información adecuada cuando se genera el archivo de Visio.

![Diagrama de jerarquía](media/hierarchy.png)

**Opción adicional**

En Talent, es posible que también puede usar el espacio de trabajo **Personas** para ver información relacionada con la jerarquía.
