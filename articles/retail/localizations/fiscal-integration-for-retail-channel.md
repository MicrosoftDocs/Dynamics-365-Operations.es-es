---
title: "Integración fiscal para el canal comercial"
description: "Este tema proporciona una introducción a la integración fiscal para Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: es-es
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Integración fiscal para el canal comercial

[!include [banner](../includes/banner.md)]

Este tema es una visión general de la funcionalidad de integración fiscal que está disponible en Microsoft Dynamics 365 for Retail. La funcionalidad de la integración fiscal es un marco diseñado para dar soporte a las leyes fiscales locales que están dirigidas a evitar el fraude en el sector minorista. Situaciones de ejemplo habituales que se pueden cubrir mediante inclusión de la integración fiscal:

- Imprimir un recibo fiscal y dárselo al cliente.
- Asegurar el envío de la información relacionada con las ventas y devoluciones realizados en POS a un servicio externo proporcionado por la autoridad.
- Usasr la protección de datos con una firma digital autorizada por la autoridad.

En este tema se proporcionan instrucciones para configurar la integración fiscal para que los usuarios pueden realizar las siguientes tareas. 

- Configurar los conectores fiscales, que son dispositivos o servicios fiscales usados para fines fiscales de registro como el guardado, las firmas digitales y el envío seguro de datos fiscales.
- Configurar el proveedor de documentos, que define un método de salida y un algoritmo de generación de documentos fiscales.
- Configurar el proceso de registro fiscal, que define una secuencia de pasos y un grupo de conectores utilizados en cada paso.
- Asignar procesos de registro fiscales a perfiles de funcionalidad de PDV.
- Asignar perfiles técnicos de conector a perfiles de hardware (para los conectores fiscales locales) o a perfiles de funcionalidad PDV (para otros tipos de conectores fiscales).

## <a name="fiscal-integration-execution-flow"></a>Flujo de ejecución de integración fiscal
La situación de ejemplo siguiente muestra el flujo de ejecución de la integración fiscal común.

1. Inicialización del proceso de registro fiscal.
  
   Después de realizar algunos acciones en las que se requiere el registro fiscal, como por ejemplo después de finalizar una transacción al por menor, el proceso de registro fiscal se asocia al perfil de funcionalidad actual de PDV.

1. Buscar un conector fiscal.
   
   Para cada paso de registro fiscal incluido en el proceso de registro fiscal, el sistema correlaciona la lista de conectores fiscales. Estos conectores tienen un perfil funcional incluido en el grupo de conectores especificados, con una lista de conectores que tienen un perfil técnico asociado al perfil de hardware actual (para un tipo de conector que es **Local** solo) o al perfil de funcionalidad actual de PDV (para otros tipos de conectores).
   
1. Realice la integración fiscal.

   El sistema ejecuta todas las acciones necesarias definidas por un ensamblado vinculado con el conector encontrado. Esto se realiza de acuerdo con los valores del perfil funcional y del perfil técnico que se encontraron en el paso anterior para este conector.

## <a name="setup-needed-before-using-fiscal-integration"></a>Configuración necesaria antes de utilizar la integración fiscal
Antes de usar la funcionalidad de la integración fiscal, debe definir los valores siguientes:

- Defina la secuencia numérica en la página **Parámetros de ventas** para el número de perfil funcional fiscal.
  
- Defina las secuencias numéricas en la página **Parámetros compartidos comerciales** para las referencias siguientes:
  
  - Número de perfil técnico fiscal
  - Número de grupo del conector fiscal
  - Número de proceso de registro

- Cree un **Conector fiscal** en **Venta minorista > Configuración de canal > integración fiscal > conectores fiscales** para cada dispositivo o servicio que tenga previsto usar para fines de integración fiscal.

-  Cree **Proveedor de documento fiscal** en **Venta minorista > Configuración de canal > integración fiscal > proveedores de documentos fiscales** para todos los conectores fiscales. La asignación de datos se considera una parte del proveedor de documentos fiscales. Para configurar diferentes asignaciones de datos para el mismo conector (como normas de esetado específicas), debe crear varios proveedores de documentos fiscales.

- Cree un **Perfil funcional de conector** en **Venta minorista > configurar canal> integración fiscal > perfiles funcionales de conector** para cada proveedor de documentos fiscales.
  - Seleccione un nombre de conector.
  - Seleccione un proveedor de documentos.
  - Especifique los valores de índices de IVA en la pestaña **configuración del servicio**.
  - Especifique la asignación de códigos de IVA y la asignación de tipo de pago en la pestaña **Asignación de datos**.

  #### <a name="examples"></a>Ejemplo 

  |  | Formato | Ejemplo | 
  |--------|--------|--------|
  | Configuración de índices de IVA | valor: VATrate | 1 : 2000, 2 : 1800 |
  | Asignación de códigos de IVA | VATcode : valor | vat20 : 1, vat18 : 2 |
  | Asignación de tipos de forma de pago | TenderTyp: valor | Cash : 1, Card : 2 |

- Cree **Grupos del conector fiscal** en **Venta minorista > Configuración de canal > integración fiscal > grupo del conector fiscal**. Un grupo de conectores es un subconjunto de perfiles funcionales vinculados con conectores fiscales que realizan idénticas funciones y se usan en la misma etapa del proceso de registro fiscal.

   - Agregue perfiles funcionales el grupo de conectores. Haga clic en **Agregar** en la página **Perfiles funcionales** y seleccione un número del perfil.
   - Si desea suspender el uso del perfil funcional, establezca **Deshabilitar** en **Sí**. 
   
     Este cambio afecta al grupo de conectores actuales únicamente. Puede continuar con el mismo perfil funcional en otros grupos de conectores.

     >[!NOTE]
     > Dentro de un grupo de conectores, cada conector fiscal solo puede tener un perfil funcional.

- Cree un **Perfil técnico de conector** en **Venta minorista > configurar canal> integración fiscal > perfiles técnicos de conector** para cada conector fiscal.
  - Seleccione un nombre de conector.
  - Seleccione un tipo de conector: 
      - **Local** - Establezca este tipo para los dispositivos o las solicitudes instaladas en un equipo local.
      - **Interno** - Estableza este tipo para los dispositivos fiscales y servicios conectados a Retail Server.
      - **Externo** - Para los servicios fiscales externos como un portal Web proporcionado por una autoridad fiscal.
    
  - Especifique la configuración en la pestaña **Conexión**.

      
 >[!NOTE]
 > Una versión actualizada de una configuración que se cargó anteriormente se cargará para los perfiles funcionales y técnicos. Si ya se está usando un conector o un proveedor de documentos adecuado, se le notificará. De forma predeterminada, todos los cambios realizados manualmente en perfiles funcionales y técnicos se guardarán. Para anular estos perfiles con el conjunto de parámetros predeterminado de una configuración, haga clic en **Actualizar** en la página **Perfiles funcionales del conector** y la página **Perfiles técnicos del conector**.
 
- Cree un **Proceso de registro fiscal** en **venta minorista > configurar canal > integración fiscal > procesos de registro fiscales** para cada proceso único de integración fiscal. Un proceso de registro se define por la secuencia de los pasos de registro y el grupo de conectores utilizados en cada paso. 
  
  - Agregar pasos de registro al proceso:
      - Haga clic en **Agregar**.
      - Seleccione un tipo de conector.
      
      >[!NOTE]
      > Este campo define dónde el sistema buscará el conector en un perfil técnico, en los perfiles de hardware para el tipo de conector **local** o en los perfiles de funcionalidad de PDV para otros tipos de conectores fiscales.
      
   - Seleccione un grupo de conectores.
   
     >[!NOTE]
     > Haga clic en **Validar** para comprobar la integridad de la estructura del proceso de registro. Se recomienda que se hagan las validaciones en los casos siguientes:
       >- Para un proceso de registro nuevo después de que toda la configuración se complete, incluidos los perfiles de funcionalidad PDV y los perfiles de hardware.
       >- Después de crear actualizaciones en un proceso de registro existente.

-  Vincule los procesos de registro fiscales a los perfiles de funcionalidad del PDV en **Venta minorista > configurar canal > Configuración de PDV > perfiles de PDV > perfiles de funcionalidad**.
   - Haga clic en **Editar** y seleccione **Número de proceso** en la pestaña **Proceso de registro fiscal**.
- Vincule los perfiles técnicos de conectores a los perfiles de hardware en **venta minorista > configurar canal > Configuración de PDV > perfiles PDV > perfiles de hardware**.
   - Haga clic en **Editar** y, a continuación, haga clic en **Nuevo** en la pestaña **Perfil técnico fiscal**.
   - Seleccione un perfil del técnico de conector en el campo **Número de perfil**.
   
     >[!NOTE]
     > Puede agregar varios perfiles técnicos a un perfil de hardware. Sin embargo, esto no se admite si un perfil de hardware tiene más de una intersección con cualquier grupo de conectores. Para evitar valores incorrectos, se recomienda que valide el proceso de registro después de actualizar todos los perfiles de hardware.

