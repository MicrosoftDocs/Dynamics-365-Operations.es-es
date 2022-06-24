---
title: Comprender campos de fecha y hora
description: Este artículo explica qué esperar cuando usa los campos Fecha y Hora en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e314efa5ac08288bc7d00c197be59ba9decac203
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856320"
---
# <a name="understand-date-and-time-fields"></a>Comprender campos de fecha y hora

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Los campos **Fecha y hora** son un concepto fundamental en Microsoft Dynamics 365 Human Resources. Es importante comprender cómo trabajar con los datos de **Fecha y hora** en páginas, Dataverse y orígenes externos.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprensión de la diferencia entre los tipos de datos de los campo de fecha y fecha y hora

Los campos **Fecha y hora** contienen información de la zona horaria, mientras que los campos **Fecha** no. Los campos **Fecha** muestran la misma información en cualquier ubicación. Cuando se especifica una fecha en un campo **Fecha**, se escribe esa misma fecha en la base de datos.

Al visualizar datos en un campo **Fecha y hora**, la fecha y hora se ajustan en función de la zona horaria del usuario seleccionada en la página **Opciones de usuario** (**Común \> Configuración \> Opciones de usuario**). Puede que la información de fecha y hora que especifique en el campo no sea la misma que la información escrita en la base de datos.

[![Página de opciones de usuario.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>Comprensión de los campos de fecha y hora en páginas 

Los datos de **Fecha y hora** que se muestran en pantalla no serán los mismos que los datos almacenados en la base de datos si la zona horaria del usuario no se establece en la hora universal coordinada (UTC). Los datos de campos **Fecha y hora** se almacenan siempre como UTC.

[![UTC de página de trabajador.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Comprensión de los campos de fecha y hora en la base de datos 

Cuando se escribe un valor de **Fecha y hora** en la base de datos, los datos se almacenan en UTC. Por tanto, los usuarios pueden ver datos **Fecha y hora** en relación con la zona horaria definida en sus opciones de usuario.
 
En el ejemplo anterior, la hora de inicio es un punto en el tiempo, no una fecha concreta. Al cambiar a GMT UTC la zona horaria del usuario que inició sesión en GMT+12:00, el mismo registro muestra 30/04/2019 12:00:00 en lugar de 01/05/2019 12:00:00.

En el siguiente ejemplo, el empleo del empleado 000724 se activa al mismo tiempo independientemente de zona horaria. El empleado estará activo el 30/04/2019 en la zona horaria del GMT, que es lo mismo que 01/05/2019 en la zona horaria GMT+12:00. Ambas hacen referencia el mismo momento dado y no a una fecha concreta. 

[![GMT de página de trabajador.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Datos de fecha y hora en marco de administración de datos, Excel, Dataverse y Power BI 

El marco de gestión de datos (DMF), el complemento de Excel, Dataverse, y la notificación de Power BI están diseñados para interactuar con datos directamente en el nivel de la base de datos. Dado que no hay cliente para ajustar los datos de **Fecha y hora** a la zona horaria del usuario, todos los valores **Fecha y hora** se muestran en UTC, lo que puede conducir a algunas suposiciones incorrectas al especificar o ver datos.
 
Cuando los datos **Fecha y hora** se envían mediante DMF, Excel o Dataverse, la base de datos asume que están en UTC. Sin embargo, si los usuarios que ven los datos no tienen su zona horaria de usuario configurada en UTC, el valor de **Fecha y hora** no aparecerá como se esperaba y los usuarios podrían confundirse. 
 
La misma cosa puede suceder a la inversa, cuando se exportan los datos. Los datos de **Fecha y hora** de la entidad exportada de DMF pueden ser diferentes de lo que se presenta en el cliente de Dynamics. 
 
Al usar orígenes externos como DMF para ver o crear datos, es importante tener presente que, de forma predeterminada, se consideran que los valores de **Fecha y hora** están en UTC, con independencia de la zona horaria del equipo del usuario o de los valores de la zona horaria del usuario actual. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Ejemplos del mismo registro que se muestra en varias áreas del producto 

**Human Resources con la zona horaria del usuario configurada en UTC**.

[![Página de trabajador en UTC.](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources con la zona horaria del usuario configurada en GMT +12:00**. 

[![Página de trabajador en GMT.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel mediante OData**

[![Excel mediante OData.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Ubicación provisional de DMF**

[![Ubicación provisional de DMF.](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportar DMF**

[![Exportación de DMF.](./media/DMFExport.png)](./media/DMFExport.png)

**Excel mediante Dataverse**

[![Excel mediante Dataverse.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Consulte también

[Datos de fecha y hora](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Zonas horarias preferidas del usuario](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
