---
title: Comprender los campos de fecha y hora
description: Comprende qué esperar al usar los campos de fecha y hora de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb011ca7b5f4c036b2f49875a256885182564c391c6dd263a0bfa70bbd29f4a7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733549"
---
# <a name="understand-date-and-time-fields"></a>Comprender campos de fecha y hora

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

los campos **Fecha y hora** son un concepto fundamental en Dynamics 365 Human Resources. Es importante comprender cómo trabajar con los datos de **Fecha y hora** en formularios, Dataverse y orígenes externos.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprensión de la diferencia entre los tipos de datos de los campo de fecha y fecha y hora

Los campos **Fecha y hora** contienen información de la zona horaria, mientras que los campos **Fecha** no. Los campos **Fecha** muestran la misma información en cualquier ubicación. Cuando se especifica una fecha en un campo **Fecha**, Human Resources escribe esa misma fecha en la base de datos.

Al visualizar datos en un campo **Fecha y hora**, Human Resources ajusta la fecha y hora basada en función de la zona horaria del usuario establecida en el formulario **Opciones de usuario** (**Común > Configuración > Opciones de usuario**). Puede que la información de fecha y hora que especifique en el campo no sea la misma que la información escrita en la base de datos.

[![Formulario de opciones de usuario.](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Comprensión de los campos de fecha y hora en los formularios 

Los datos de **Fecha y hora** que se muestran en pantalla no serán los mismos que los datos almacenados en la base de datos si la zona horaria del usuario no se establece en la hora universal coordinada (UTC). Los datos de campos **Fecha y hora** se almacenan siempre como UTC.

[![Formulario de trabajador UTC.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Comprensión de los campos de fecha y hora en la base de datos 

Cuando Human Resources escribe un valor de **Fecha y hora** en la base de datos, almacena los datos en UTC. Esto permite a los usuarios ver los datos **Fecha y hora** en relación con la zona horaria definida en sus opciones de usuario.
 
En el ejemplo anterior, la hora de inicio es un punto en el tiempo, no una fecha concreta. Al cambiar a GMT UTC la zona horaria del usuario que inició sesión en GMT+12:00, el mismo registro muestra 30/04/2019 12:00:00 en lugar de 01/05/2019 12:00:00.
  
En el siguiente ejemplo, el empleo del empleado 000724 se activa al mismo tiempo independientemente de zona horaria. El empleado estará activo el 30/04/2019 en la zona horaria del GMT, que es lo mismo que 01/05/2019 en la zona horaria GMT+12:00. Ambas hacen referencia el mismo momento dado y no a una fecha concreta. 

[![Formulario de trabajador GMT.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Datos de fecha y hora en marco de administración de datos, Excel, Dataverse y Power BI 

El marco de gestión de datos, el complemento de Excel, Dataverse, y la notificación de Power BI están diseñados para interactuar con datos directamente en el nivel de la base de datos. Dado que no hay cliente para ajustar los datos de **Fecha y hora** a la zona horaria del usuario, todos los valores **Fecha y hora** se muestran en UTC, lo que puede conducir a algunas suposiciones incorrectas al especificar o ver datos.  
 
La base de datos asume que los datos **Fecha y hora** enviados mediante DMF, Excel, o Dataverse están en UTC. Esto puede provocar cierta confusión cuando el valor **Fecha y hora** enviado no se muestra del modo esperado porque el usuario que ve los datos no tiene su zona horaria establecida en UTC. 
 
La misma cosa puede suceder a la inversa, cuando se exportan los datos. Los datos de **Fecha y hora** de la entidad exportada de DMF pueden ser diferentes de lo que se presenta en el cliente de Dynamics. 
 
Al usar orígenes externos como DMF para ver o crear datos, es importante tener presente que, de forma predeterminada, se consideran que los valores de **Fecha y hora** están en UTC, con independencia de la zona horaria del equipo del usuario o de los valores de la zona horaria del usuario actual. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Ejemplos del mismo registro que se muestra en varias áreas del producto 

**Human Resources con la zona horaria del usuario configurada en UTC**.

[![Formulario de trabajador en UTC.](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources con la zona horaria del usuario configurada en GMT +12:00**. 

[![Formulario de trabajador en GMT.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel mediante OData**

[![Excel mediante OData.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Ubicación provisional de DMF**

[![Ubicación provisional de DMF.](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportar DMF**

[![Exportación de DMF.](./media/DMFexport.png)](./media/DMFexport.png)

**Excel mediante Dataverse**

[![Excel mediante Dataverse.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Consulte también

[Datos de fecha y hora](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Zonas horarias preferidas del usuario](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]