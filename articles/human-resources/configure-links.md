---
title: Crear vínculos desde Human Resources a otro entorno
description: En este artículo se explica cómo crear un vínculo desde Microsoft Dynamics 365 Human Resources en otro entorno de Dynamics 365.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c9efae1061e96c0c42d5ca6a100bb36889ce56b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859677"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Crear vínculos desde Human Resources a otro entorno de Finance

Un cliente puede tener dos entornos de Dynamics 365 en los que está trabajando. Por ejemplo, el cliente puede tener un entorno de Dynamics 365 Human Resources en la infraestructura de Finance y necesita conectarse a otro entorno de Dynamics 365 Finance. 

Esta característica permitirá vínculos desde una página de Human Resources a una página específica en otro entorno de Finance. Cuando se configuren los vínculos, puede especificar dónde estará disponible el vínculo en Human Resources y la página de destino que se abrirá en el otro entorno.

> [!Note] 
> Debe activar **Mejoras en la experiencia del usuario de recursos humanos** en **Administración de características** para obtener esta característica.

## <a name="configure-target-systems"></a>Configurar sistemas de destino

En Recursos humanos, los administradores del sistema pueden definir vínculos que aparecerán en las páginas de **Recursos humanos**. Partes de la configuración las constituyen los entornos de Finance donde desea navegar como destino del vínculo. 

Para configurar el sistema de destino:
1. En la página **Configurar vínculos**, seleccione **Configurar el sistema de destino**.  
2. Escriba el nombre del sistema de destino y proporcione la dirección URL del entorno de Finance. Una vez configurados los sistemas de destino, puede definir sus vínculos.

## <a name="configure-links"></a>Configurar vínculos

Cada vínculo que cree tendrá la siguiente información definida:
 - **Vínculo**: nombre del vínculo. Se usa solo para identificación.
 - **Habilitar este vínculo**: establezca en **Sí** si desea visualizar el vínculo para los usuarios de Human Resources.
 - **Nombre para mostrar**: escriba el nombre que aparecerá como un vínculo para el entorno secundario. 
 - **Vínculo de superficie en el formulario** permite seleccionar la página donde quisiera mostrar el vínculo. Los vínculos solo pueden aparecer en el espacio de trabajo **Autoservicio para empleados** y las páginas **Trabajo**, **Puesto**, **Trabajador** y **Trabajador optimizado**.
 - **Grupo**: puede organizar sus vínculos usando grupos. Seleccione un grupo existente o cree uno nuevo mediante la columna **Grupo**.
 - **Sistema de destino**: seleccione el sistema de destino que se creó, usando la opción **Configurar el sistema de destino**. Este será el entorno secundario que se utilizará al navegar usando el vínculo.
 - **Usar la compañía actual de usuario**: seleccione **Sí** para usar la empresa actual del usuario al navegar en Finance. Seleccione **No** para seleccionar la empresa que se usará.
 - Elemento de menú de **destino**: permite especificar el elemento de menú del entorno de Finance que el vínculo debe usar al navegar. Están disponibles los elementos de menú a los que puede navegar directamente. 

   Para encontrar el elemento de menú requerido:
   1. Vaya al entorno de Finance y abra la página que es el destino de la navegación. 
   2. Copie el elemento de menú desde la URL. Por ejemplo, si desea que el vínculo lo lleve a la lista de empleados de Finance and Operations, especifique el valor que aparece después de "&mi" en la dirección URL. 
   3. El elemento de menú para navegar a la página de lista de empleados de este ejemplo es: HcmWorkerListPage_Employees.

 - **Vínculo al origen de datos**: seleccione el origen de los datos al que hace referencia el vínculo. La mayoría de los orígenes más habituales como **Trabajador** y **Posición** están disponibles.

### <a name="access-to-links"></a>Acceso a vínculos

Los administradores del sistema verán los vínculos recién creadaos en las páginas definidas incluso si la opción **Habilitar este vínculo** se establece en **No**. Puede utilizarse para probar vínculos antes de sacarlos y asignarlos a otros empleados. El resto de los roles solo verán los vínculos configurados después de que la opción **Habilitar este vínculo** se establezca en **Sí**. Los empleados con acceso a las páginas en las que se emergen los vínculos tendrán acceso a los vínculos.

Los usuarios también deben tener derechos de seguridad dentro del entorno secundario definido para acceder a las páginas de ese entorno. Si no los tienen, se abre un cuadro de diálogo al utilizar el vínculo.

