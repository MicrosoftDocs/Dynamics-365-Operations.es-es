---
title: Autentificación
description: Este artículo proporciona información general sobre cómo autenticar con la interfaz de programación de aplicaciones (API) de datos de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a0509ce99205d49d516e180203ffb65a1dc09a7c
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092115"
---
# <a name="authentication"></a><span data-ttu-id="b610a-103">Autentificación</span><span class="sxs-lookup"><span data-stu-id="b610a-103">Authentication</span></span>

<span data-ttu-id="b610a-104">Este artículo proporciona información general sobre cómo autenticar con la interfaz de programación de aplicaciones (API) de datos de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b610a-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="b610a-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="b610a-105">Overview</span></span>

<span data-ttu-id="b610a-106">La API de datos para Recursos Humanos es una implementación de OData.</span><span class="sxs-lookup"><span data-stu-id="b610a-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="b610a-107">Para obtener más información, consulte [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="b610a-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="b610a-108">Su aplicación debe autenticar como autor de llamada autorizado para que la API atienda las solicitudes de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="b610a-109">Conceptos fundamentales</span><span class="sxs-lookup"><span data-stu-id="b610a-109">Fundamentals</span></span>

<span data-ttu-id="b610a-110">Para llamar a la API de datos, su aplicación debe adquirir un token de acceso de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b610a-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="b610a-111">El token de acceso contiene información sobre su aplicación y el permiso que tiene para llamar a recursos de Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="b610a-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="b610a-112">Token de acceso</span><span class="sxs-lookup"><span data-stu-id="b610a-112">Access token</span></span>

<span data-ttu-id="b610a-113">Los tokens de acceso emitidos por la plataforma de identidad de Microsoft son tokens web (JWT) de JavaScript Object Notation (JSON) codificados en base64.</span><span class="sxs-lookup"><span data-stu-id="b610a-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="b610a-114">Contienen información (notificaciones) que la API de datos (y otras API web que están protegidas por la plataforma de identidad de Microsoft) utilizan para validar a la persona que llama y asegurarse de que la persona que llama tenga los permisos correctos para realizar la operación que solicita.</span><span class="sxs-lookup"><span data-stu-id="b610a-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="b610a-115">Durante las llamadas, puede tratar los tokens de acceso como opacos.</span><span class="sxs-lookup"><span data-stu-id="b610a-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="b610a-116">Siempre debe transmitir tokens de acceso a través de un canal seguro, como Transport Layer Security (TLS) y Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="b610a-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="b610a-117">Este es un ejemplo de un token de acceso emitido por la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b610a-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="b610a-118">Para llamar a la API de datos, adjunte el token de acceso como token de portador al encabezado de autorización en su solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="b610a-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="b610a-119">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b610a-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="b610a-120">Registre una aplicación nueva mediante el portal de Azure</span><span class="sxs-lookup"><span data-stu-id="b610a-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="b610a-121">Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) con una cuenta profesional o educativa, o una cuenta de Microsoft personal.</span><span class="sxs-lookup"><span data-stu-id="b610a-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="b610a-122">Si su cuenta le da acceso a más de un inquilino, seleccione su cuenta en la esquina superior derecha y configure su sesión de portal en el inquilino de Azure Active Directory (Azure AD) que desee.</span><span class="sxs-lookup"><span data-stu-id="b610a-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="b610a-123">En el panel izquierdo, seleccione el servicio de **Azure Active Directory** y luego seleccione **Registros de aplicaciones \> Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="b610a-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="b610a-124">Cuando aparezca la página **Registrar una aplicación**, introduzca la información de registro de su aplicación:</span><span class="sxs-lookup"><span data-stu-id="b610a-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="b610a-125">**Nombre**: introduzca un nombre de aplicación significativo que se mostrará a los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="b610a-126">**Tipos de cuenta admitidos** : seleccione los tipos de cuentas que su aplicación debería admitir.</span><span class="sxs-lookup"><span data-stu-id="b610a-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="b610a-127">Tipos de cuenta admitidos</span><span class="sxs-lookup"><span data-stu-id="b610a-127">Supported account types</span></span> | <span data-ttu-id="b610a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="b610a-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="b610a-129">Cuentas en el directorio de esta organización solo</span><span class="sxs-lookup"><span data-stu-id="b610a-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="b610a-130">Seleccione esta opción si está creando una aplicación de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="b610a-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="b610a-131">Esta opción no está disponible a menos que esté registrando la aplicación en un directorio.</span><span class="sxs-lookup"><span data-stu-id="b610a-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="b610a-132">Esta opción está asignada a **inquilino único de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b610a-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="b610a-133">Esta opción es la predeterminada a menos que esté registrando la aplicación fuera de un directorio.</span><span class="sxs-lookup"><span data-stu-id="b610a-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="b610a-134">En ese caso, la opción predeterminada es **cuentas de Microsoft personales y multiinquilino de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b610a-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="b610a-135">Cuentas en cualquier directorio de organización</span><span class="sxs-lookup"><span data-stu-id="b610a-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="b610a-136">Seleccione esta opción para tener como objetivos todos los clientes empresariales y educativos.</span><span class="sxs-lookup"><span data-stu-id="b610a-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="b610a-137">Esta opción está asignada a **solo multiinquilino de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b610a-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="b610a-138">Si registró la aplicación como **solo inquilino único de Azure AD**, puede usar la hoja **Autenticación** para actualizarla a **solo multiinquilino de Azure AD** y luego de nuevo a **solo inquilino único de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b610a-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="b610a-139">Cuentas en cualquier cuenta de Microsoft personal y directorio de organización</span><span class="sxs-lookup"><span data-stu-id="b610a-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="b610a-140">Seleccione esta opción para dirigirse al conjunto más amplio de clientes.</span><span class="sxs-lookup"><span data-stu-id="b610a-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="b610a-141">Esta opción se asigna a **cuentas de Microsoft personales y multiinquilino de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b610a-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="b610a-142">Si ha registrado la aplicación como **cuentas de Microsoft personal y multiinquilino de Azure AD**, no puede cambiar esta configuración en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="b610a-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="b610a-143">En su lugar, debe usar el editor de manifiesto de la aplicación para cambiar los tipos de cuenta admitidos.</span><span class="sxs-lookup"><span data-stu-id="b610a-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="b610a-144">**URI de redireccionamiento (opcional)**: seleccione el tipo de aplicación que está creando: **Web** o **Cliente público (móvil y de escritorio)**.</span><span class="sxs-lookup"><span data-stu-id="b610a-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="b610a-145">A continuación, introduzca el URI de redireccionamiento (o URL de respuesta) para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="b610a-146">Para aplicaciones web, proporcione la URL base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="b610a-147">Por ejemplo, `http://localhost:31544` podría ser la URL de una aplicación web que se ejecuta en su máquina local.</span><span class="sxs-lookup"><span data-stu-id="b610a-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="b610a-148">A continuación, los usuarios usan esta dirección URL para iniciar sesión en una aplicación cliente web.</span><span class="sxs-lookup"><span data-stu-id="b610a-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="b610a-149">Para aplicaciones de cliente público, proporcione el URI que Azure AD utiliza para devolver respuestas de token.</span><span class="sxs-lookup"><span data-stu-id="b610a-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="b610a-150">Introduzca un valor específico para su aplicación, como `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="b610a-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="b610a-151">Para ver ejemplos específicos de aplicaciones web o aplicaciones nativas, consulte los tutoriales rápidos en [Plataforma de identidad de Microsoft (anteriormente, Azure Active Directory para desarrolladores)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="b610a-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="b610a-152">En **Permisos de API**, seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="b610a-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="b610a-153">Después, en la **API que usa mi organización**, busque **Dynamics 365 Human Resources** y agregue el permiso **usuario\_interpretación** a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="b610a-154">El id. de aplicación para Recursos Humanos es f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="b610a-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="b610a-155">Use este id. para asegurarse de haber elegido la aplicación correcta.</span><span class="sxs-lookup"><span data-stu-id="b610a-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="b610a-156">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="b610a-156">Select **Register**.</span></span>

   <span data-ttu-id="b610a-157">[![Registro de una aplicación nueva en el portal de Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b610a-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="b610a-158">Azure AD asigna un id. de aplicación único (id. de cliente) a su aplicación y lo lleva a la página **Visión general** para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b610a-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="b610a-159">Para agregar más capacidades a su aplicación, puede seleccionar otras opciones de configuración, como opciones como marcas y para certificados y secretos.</span><span class="sxs-lookup"><span data-stu-id="b610a-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="b610a-160">Recuperación de un token de acceso</span><span class="sxs-lookup"><span data-stu-id="b610a-160">Retrieving an access token</span></span>

<span data-ttu-id="b610a-161">Los detalles de cómo recuperar un token de acceso para llamar a la API de datos de Recursos Humanos dependerán de las tecnologías que esté utilizando para desarrollar su aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="b610a-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="b610a-162">Por ejemplo, podría estar [probando con una utilidad de terceros](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (como Postman), desarrollando una aplicación de consola C# o un servicio web, o creando un cliente javascript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="b610a-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="b610a-163">Aplicación de cliente C# de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b610a-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="b610a-164">Una vez que haya recuperado un token de acceso, pasará el token en el encabezado de Autorización como un token de portador con cada solicitud que envíe a la API de datos, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b610a-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
