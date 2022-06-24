---
title: Crear un nuevo motor de administración de transporte
description: Este artículo describe cómo crear un nuevo motor de administración de transporte en Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 627972ef6afb7551bb57821ded24183f8f335e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857268"
---
# <a name="create-a-new-transportation-management-engine"></a>Crear un nuevo motor de administración de transporte

[!include [banner](../includes/banner.md)]

Este artículo describe cómo crear un nuevo motor de administración de transporte en Dynamics 365 Supply Chain Management. 

Los motores de administración del transporte (TMS) definen la lógica que se usa para generar y procesar tasas de transporte en Administración de transporte. Supply Chain Management proporciona varios tipos de motores diferentes que calculan diferentes parámetros, como tarifas, tiempos de tránsito y la cantidad de zonas que se cruzarán durante el tránsito. Este artículo explica cómo utilizar el entorno de desarrollo Microsoft Visual Studio junto con las herramientas de desarrollo de Supply Chain Management para crear e implementar un nuevo motor TMS, y luego cómo configurar el motor en Operaciones. Para obtener más información sobre los motores, consulte [Motores de gestión de transporte](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Crear un nuevo motor TMS

Esta sección explica cómo crear una biblioteca de clases que tiene una implementación de motor TMS y cómo hacer referencia a ella desde un modelo de Supply Chain Management.

1. Para implementar sus nuevos motores, debe tener un modelo que contendrá los motores. En el menú **Dynamics 365** &gt; **Administración de modelos**, haga clic en **Crear modelo** para crear un nuevo modelo. En la primera página del asistente **Crear modelo**, nombre el modelo **TMSEngines**. 

   [![Crear una lista.](./media/012.png)](./media/012.png)

2. En la página siguiente, seleccione **Crear nuevo paquete**. 

   [![Crear un nuevo paquete.](./media/021.png)](./media/021.png)

3. En la página siguiente, seleccione el modelo **ApplicationSuite** de referencia. (El modelo **ApplicationPlatform** está preseleccionado.) 

   [![Seleccionar el modelo al que hacer referencia.](./media/032.png)](./media/032.png)

4. En la página siguiente, haga clic en **Terminar** para confirmar la creación de un nuevo modelo. 

   [![Completar la creación del modelo.](./media/042.png)](./media/042.png)

5. En una nueva solución, cree un nuevo proyecto de Supply Chain Management y asígnele el nombre **TMSThirdParty**. En las propiedades del proyecto, establezca el modelo del proyecto en **TMSEngines**.
6. Agregar una nueva biblioteca de clase C\# a su solución, y asígnele el nombre **ThirdPartyTMSEngines**.
7. En el proyecto ThirdPartyTMSEngines, agregue referencias a ensamblajes específicos de Supply Chain Management:
   -   Ensamblados de aplicaciones que permiten hacer referencia a tipos X++. Estos conjuntos se pueden encontrar en las siguientes ubicaciones. \[Packages root\] es la ruta de la ubicación donde se colocan todos los ensamblajes implementados, como C:\\Packages.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Ensamblados de marco que permiten el acceso a datos, LINQ y funciones auxiliares. Todos estos ensamblajes se pueden encontrar en la ubicación \[Packages root\]\\.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   El ensamblado principal de TMS (que contiene motores) y el ensamblado base de TMS (que contiene ayudantes, constantes, definiciones de clases de transferencia de datos, etc.). Estos conjuntos se pueden encontrar en las siguientes ubicaciones.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Cambiar el nombre de la clase C\# que se genera automáticamente en el proyecto ThirdPartyTMSEngines para **SampleRatingEngine**.
9. Implementar el motor. Debido a que estamos creando un motor de tarifas en este ejemplo, heredamos de la clase base para los motores de tarifas. La clase base implementa la mayor parte de la interfaz del motor de tarifas (**TMSFwkIRateEngine**). Solo tenemos que implementar el método de tasa. Para mantener este ejemplo simple, haremos que este método registre una tasa codificada de 100. Puede crear motores que implementen cualquiera de las interfaces del motor, como **TMSFwkIAccessorialEngine**. Todas las interfaces del motor están definidas en X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Construir la solución.
11. Agregue una nueva referencia al proyecto TMSThirdParty. La referencia debe apuntar al proyecto ThirdPartyTMSEngines. Cuando haya terminado, su solución debería verse así. 

    [![La solución, que incluye una referencia al proyecto TMSThirdParty.](./media/052.png)](./media/052.png)

12. Construir la solución. Verifique que la nueva biblioteca aparezca en el nodo **Referencias** en el Explorador de la aplicación. 

    [![La nueva biblioteca en el nodo Referencias del Explorador la aplicación.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Implementar el motor TMS como un paquete

Una forma de implementar motores TMS de terceros es mediante un paquete de implementación. Este enfoque se recomienda en un entorno de producción. En un entorno de desarrollo, puede copiar manualmente los ensamblajes, como se describe en la siguiente sección, "Configurar un motor TMS en Supply Chain Management". Siga estos pasos para implementar el motor como un paquete:

1. En el menú **Dynamics 365** &gt; **Implementar**, haga clic en <strong>Crear paquete de implementación</strong>.
2. En el cuadro de diálogo **Crear paquete de implementación**, seleccione el modelo TMSEngines e introduzca la ruta donde desea almacenar los archivos del paquete. 

   [![Seleccionar el modelo TMSEngines.](./media/071.png)](./media/071.png)

3. Ahora puede implementar el paquete en el entorno de destino. Para obtener un tutorial, consulte [Instalar un paquete desplegable](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Configurar un motor TMS en Supply Chain Management

Esta sección explica cómo configurar Supply Chain Management para usar un motor TMS y muestra cómo se usa el nuevo motor que hemos creado en la comparación de tarifas. El ejemplo en esta sección usa la empresa de datos de demostración USMF.

1. Cree un nuevo motor como se describe en la sección "Crear un nuevo motor TMS".
2. Cree su solución.
3. Copie el ensamblaje resultante en la ubicación binaria del servidor de Supply Chain Management, ubicación \[AOSWebRoot\]. **Nota:** Este paso es relevante solo en un entorno de desarrollo. En un entorno de producción, debe llevar a cabo la implementación a través de un paquete de implementación. Para obtener instrucciones, consulte la sección anterior, "Implementar el motor TMS como un paquete".
4. En Supply Chain Management, en la página **Motores de tarifas**, cree un nuevo motor de clasificación. El motor debe apuntar al ensamblado del motor que se produce al crear la biblioteca de clases de motor y la clase de motor que implementó. 

   [![Crear de un nuevo motor de calificación en la página Motores de tarifas.](./media/081.png)](./media/081.png)

5. Cree un transportista de envío que utilice el motor de tarifas de ejemplo. Debido a que nuestro motor no usa ningún dato, no es necesario que asigne una tasa maestra. 

   [![Crear un nuevo transportista de envío.](./media/092.png)](./media/092.png)

6. En la página **Área de trabajo de la ruta de la tasa**, haga clic en **Opciones de tasas**. Debería ver una tasa de 100,00 de SampleCarrier, como se muestra en la siguiente captura de pantalla. En este ejemplo, calificamos la comparación de tarifas de una ruta desde el almacén 24 hasta el cliente US-004. Sin embargo, debido a que la tasa está codificada, siempre verá una tasa de 100,00.

   [![Área de trabajo índice y la ruta.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Sugerencias y trucos

- Si está utilizando herramientas de desarrollo para Supply Chain Management, es útil agregar un nuevo proyecto a su solución. Si configura este proyecto como su proyecto de inicio e inicia una sesión de depuración, puede depurar tanto el código X++ como C\# en la misma sesión de depuración.
- Cada vez que cambie y vuelva a compilar su proyecto ThirdPartyTMSEngines, debe copiar manualmente el ensamblado resultante en la ubicación binaria o implementarlo a través de un paquete de implementación. De lo contrario, puede ejecutarlo utilizando un ensamblado obsoleto.
- Después de ejecutar operaciones específicas de TMS en Supply Chain Management, el proceso de trabajo de Internet Information Services (IIS) puede bloquear el ensamblado ThirdPartyTMSEngines para que el ensamblado no se pueda actualizar. En este caso, reinicie el proceso w3svc.

### <a name="whitepaper"></a>Notas del producto

Para obtener más información, descargue las siguientes notas del producto (escrito para ser compatible con AX2012, pero aún sirve para Dynamics 365 Supply Chain Management)

- [Implementar motores de administración de transporte](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]