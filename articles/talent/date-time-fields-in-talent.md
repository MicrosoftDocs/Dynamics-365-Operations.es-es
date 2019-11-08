---
title: Trabajar con la fecha y hora en Microsoft Dynamics 365 Talent
description: Comprende qué esperar al usar los campos de fecha y hora de Microsoft Dynamics 365 Talent. Gana claridad en qué esperar al interactuar con datos de fecha y hora en un formulario en Talent, un origen externo, o Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: abd215243cbda68ba3f57b5fa41054a10745d11f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551035"
---
# <a name="work-with-date-and-time-in-microsoft-dynamics-365-talent"></a>Trabajar con la fecha y hora en Microsoft Dynamics 365 Talent

[!include [banner](includes/banner.md)]

los campos**Fecha y hora** son un concepto fundamental en Dynamics 365 Talent. Es importante comprender cómo trabajar con los datos de **Fecha y hora** en un formulario de Dynamics 365, Common Data Service, y fuentes externas.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprensión de la diferencia entre los tipos de datos de los campo de fecha y fecha y hora

Los campos **Fecha y hora** contienen información de la zona horaria, mientras que los campos **Fecha** no. Los campos**Fecha** muestran la misma información en cualquier ubicación. Cuando se especifica una fecha en un campo **Fecha**, Talent escribe esa misma fecha en la base de datos.

Al visualizar datos en un campo **Fecha y hora**, Talent ajusta la fecha y hora basada en función de la zona horaria del usuario establecida en el formulario **Opciones de usuario** (**Común > Configuración > Opciones de usuario**). Puede que la información de fecha y hora que especifique en el campo no sea la misma que la información escrita en la base de datos.

[![Formulario de opciones de usuario](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Comprensión de los campos de fecha y hora en los formularios 

Al especificar datos en un campo **Fecha y hora**, los datos visualizados en la pantalla no son los mismos que los datos almacenados en la base de datos si la zona horaria del usuario no se establece en la hora universal coordinada (UTC). Los datos de campos **Fecha y hora** se almacenan siempre como UTC.

[![Formulario de trabajador](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Comprensión de los campos de fecha y hora en la base de datos 

Cuando Talent escribe un valor de **Fecha y hora** en la base de datos, almacena los datos en UTC. Esto permite a los usuarios ver los datos **Fecha y hora** en relación con la zona horaria definida en sus opciones de usuario.
 
En el ejemplo anterior, la hora de inicio es un punto en el tiempo, no una fecha concreta. Al cambiar la zona horaria del usuario que ha iniciado sesión de GMT +12:00 a GMT UTC, el mismo registro terminado de crear muestra 30/04/2019 12:00:00 en lugar de 01/05/2019 12:00:00.
  
En el siguiente ejemplo, el empleo del empleado 000724 se activa al mismo tiempo independientemente de zona horaria. El empleado estará activo el 30/04/2019 en la zona horaria del GMT, que es lo mismo que 01/05/2019 en la zona horaria GMT+12:00. Ambas hacen referencia el mismo momento dado y no a una fecha concreta. 

[![Formulario de trabajador](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Datos de fecha y hora en marco de administración de datos, Excel, Common Data Service y Power BI 

El marco de gestión de datos, el complemento de Excel, Common Data Service, y la notificación de Power BI están diseñados para interactuar con datos directamente en el nivel de la base de datos. Dado que no hay cliente para ajustar los datos **Fecha y hora** a la zona horaria del usuario, todos los valores **Fecha y hora** se muestran en UTC, lo que puede conducir a algunas suposiciones incorrectas al especificar o ver datos.  
 
La base de datos asume que los datos**Fecha y hora** que se registran mediante DMF, Excel, o Common Data Service están en UTC. Esto puede provocar cierta confusión cuando el valor **Fecha y hora** enviado no se muestra del modo esperado porque el usuario que ve los datos no tiene su zona horaria establecida en UTC. 
 
La misma cosa puede suceder a la inversa, cuando se exportan los datos. Los datos **Fecha y hora** de la entidad exportada de DMF pueden ser diferentes de lo que se presenta en el cliente de Dynamics. 
 
Al usar fuentes externas como DMF para ver o crear datos, es importante tener presente que los valores **Fecha y hora** se consideran de forma predeterminada que están en UTC independientemente de la zona horaria del equipo del usuario o de los valores de la zona horaria del usuario actual. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Ejemplos del mismo registro que se muestra en varias áreas del producto 

**Talent con la zona horaria del usuario configurada en UTC**.

[![Formulario de trabajador](./media/worker-form3.png)](./media/worker-form3.png)

**Talent con la zona horaria del usuario configurada en GMT +12:00**. 

[![Formulario de trabajador](./media/worker-form4.png)](./media/worker-form4.png)

**Excel mediante OData**

[![Excel mediante OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Ubicación provisional de DMF**

[![Ubicación provisional de DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportar DMF**

[![Ubicación provisional de DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel mediante Common Data Service**

[![Excel mediante Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>Consulte también

[Datos de fecha y hora](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Zonas horarias preferidas del usuario](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
