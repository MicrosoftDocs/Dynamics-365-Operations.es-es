---
title: Exportar datos desde Attract y Onboard
description: 'Exporte datos desde Dynamics 365 Talent: Attract y Onboard.'
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: acdd93637385246f9c5c652cccdf2cbfb263cc33
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975943"
---
# <a name="export-data-from-attract-and-onboard"></a>Exportar datos desde Attract y Onboard

[!include [banner](includes/banner.md)]

Como se anunció en [Retirada de las aplicaciones Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), vamos a retirar Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard el 1 de febrero de 2022. Para ayudarle a migrar a otro producto, ahora ofrecen ambas aplicaciones funciones de exportación de datos.

## <a name="export-data-from-attract"></a>Exportar datos desde Attract

Puede exportar los datos sin limitar el acceso a su entorno. Es posible que desee hacer esto con fines de prueba o para comprender nuestra estructura de datos. Cuando esté listo para migrar, limite el acceso a su entorno de Attract mediante las instrucciones que se indican después de este procedimiento. Asegúrese de exportar los datos nuevamente. 

1. Ir a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. En **Exportación de datos**, seleccione **Solicitar una exportación de datos**.

   ![[Solicitar una exportación de datos desde Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Cuando se abra el cuadro de mensaje **Su petición se está procesando**, seleccione **Aceptar**. La exportación de datos puede tardar hasta 20 minutos, en función de su tamaño.

4. Cuando finalice su exportación, haga clic en el botón **Descargar** situado junto a ella. 

   >[!NOTE]
   >Todas las exportaciones de datos están disponibles durante siete días. Después, el vínculo **Descargar** expira.</br>
   
La descarga contiene un archivo .zip con sus datos de Attract, incluidas las siguientes carpetas:

| Nombre de carpeta | Descripción |
| --- | --- |
| Configuración de administrador | Configuraciones del Centro de administración de Attract. |
| Candidatos | Todos los candidatos que se agregaron a trabajos o grupos de talentos. |
| Plantillas de correo electrónico | Todas las plantillas de correo electrónico que se configuraron para el entorno. |
| Plantillas de paquetes de oferta de trabajo | Todas las plantillas de paquetes de ofertas de trabajo que se crearon, con sus configuraciones asociadas. |
| Conjunto de reglas de oferta de trabajo |  Todos los archivos de conjunto de reglas que se cargaron para la administración de ofertas. |
| Plantillas de oferta de trabajo | Todas las plantillas de documentos de ofertas de trabajo creadas para el entorno. |
| Vacantes | Todos los empleos creados. Los trabajos eliminados no se exportan. Las subcarpetas contienen solicitudes de candidatos, con subcarpetas para los archivos adjuntos de las solicitudes de candidatos y paquetes de ofertas, según corresponda. |
| Plantillas de vacantes | Plantillas de proceso de trabajo que se configuraron en el entorno. |
| Grupos de talentos | Todos los grupos de talentos creados, sus listas de colaboradores y las listas de candidatos para los grupos de talentos. |
| Trabajadores | Lista de todos los trabajadores que están presentes en el entorno, y sus roles. |
| (carpeta raíz) | Un archivo de esquema JSON que describe los campos de la estructura de datos. |

### <a name="restrict-access-to-attract"></a>Restringir el acceso a Attract

Cuando esté preparado para realizar la migración, limite el acceso de los no administradores a su entorno de Attract y exporte los datos.

>[!IMPORTANT]
>Restringir el acceso a su entorno de Attract es una acción irreversible. Si desea que los usuarios que no son administradores sigan accediendo a su entorno, omita este paso.

1. Ir a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Para restringir el acceso de los no administradores a su entorno de Attract, en **Restringe el acceso a esta aplicación** seleccione **Restringir el acceso ahora**. Restringir el acceso también elimina los puestos de trabajo activos que se hayan publicado.

   ![[Restringir el acceso de no administradores a Attract](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Cuando vea la advertencia **Este cambio es irreversible**, seleccione **Acceso restringido** para restringir de forma permanente el acceso de los usuarios que no son administradores a este entorno. Si no está preparado para completar este paso, seleccione **Cancelar**.

   ![[Advertencia de que restringir el acceso es un cambio irreversible](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Después de que se restrinja el acceso al entorno de Attract, los administradores podrán seguir accediendo a las páginas de exportación de datos e informes de personas.

## <a name="export-data-from-onboard"></a>Exportar datos de Onboard

Cuando esté preparado podrá descargar plantillas, guías y datos de candidatos desde Onboard.

1. Ir a [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. En **Exportación de datos**, seleccione **Solicitar una exportación de datos**. 

   ![[Solicitar una exportación de datos desde Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Cuando se abra el cuadro de mensaje **Su petición se está procesando**, seleccione **Aceptar**. La exportación de datos puede tardar hasta 20 minutos, en función de su tamaño.

4. Cuando finalice su exportación, haga clic en el botón **Descargar** situado junto a ella. 

   ![[Descargar una exportación de datos desde Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >Su exportación de datos estará disponible durante siete días. Al cabo de los siete días, el vínculo **Descargar**expira y tendrá que solicitar una nueva exportación si tiene que volver a descargar los datos. Al iniciar una nueva exportación de datos, las descargas existentes expirarán cuando se haya completado la nueva exportación.

La descarga es un archivo .zip que contiene:

- Una carpeta **Plantillas** que contiene sus plantillas de Onboard en formato de documento de Word.

- Una carpeta **Guías** que contiene sus guías de Onboard en formato de documento de Word.

## <a name="see-also"></a>Consulte también

[Retirada de las aplicaciones Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)