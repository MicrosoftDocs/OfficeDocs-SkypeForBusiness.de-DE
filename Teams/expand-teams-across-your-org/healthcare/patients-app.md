---
title: Übersicht der Patienten-App
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informieren Sie sich über die Integration elektronischer Gesundheitsdatensätze in die Microsoft Teams-Patienten-App mithilfe von FHIR-APIs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad490820ac764e70f5dbdf17c2cfe5dffaea7ac8
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766948"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="25bc7-103">Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25bc7-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25bc7-104">**Die Patienten-APP wird ab dem 30. Oktober 2020 veraltet sein, und die Benutzer können Sie nicht mehr aus dem App Store von Teams installieren. Wir empfehlen Ihnen, die Listen- [App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams noch heute zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="25bc7-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="25bc7-105">Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="25bc7-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="25bc7-106">Wenn die patients-App eingestellt wird, werden alle damit verknüpften Daten in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="25bc7-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="25bc7-107">Aktuelle Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="25bc7-108">Die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) ist für alle Teams-Benutzer vorinstalliert und steht in allen Teams und Kanälen als Registerkarte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="25bc7-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="25bc7-109">Mit Listen können Gesundheitsteams mithilfe der integrierten Vorlage "Patienten", von Grund auf neu oder durch Importieren von Daten nach Excel, patientenlisten erstellen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="25bc7-110">Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="25bc7-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="25bc7-111">Dieser Artikel ist für einen allgemeinen IT-Entwickler im Gesundheitswesen vorgesehen, der die Verwendung von FHIR-APIs auf einem medizinischen Informationssystem zum Herstellen einer Verbindung mit Microsoft Teams interessiert.</span><span class="sxs-lookup"><span data-stu-id="25bc7-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="25bc7-112">Auf diese Weise können Pflege Koordinations Szenarien, die den Anforderungen einer Gesundheitsorganisation entsprechen, aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="25bc7-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="25bc7-113">Verknüpfte Artikel dokumentieren die FHIR-Schnittstellenspezifikationen für die Microsoft Teams-Patienten-APP, und in den folgenden Abschnitten wird erläutert, was erforderlich ist, um einen FHIR-Server einzurichten und mit der Patienten-app in Ihrer Entwicklungsumgebung oder Ihrem Mandanten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="25bc7-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="25bc7-114">Außerdem müssen Sie mit der von Ihnen ausgewählten Dokumentation des FHIR-Servers vertraut sein, wobei es sich um eine der unterstützten Optionen handeln muss:</span><span class="sxs-lookup"><span data-stu-id="25bc7-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="25bc7-115">Datica (durch Ihr [CMI](https://datica.com/compliant-managed-integration/) -Angebot)</span><span class="sxs-lookup"><span data-stu-id="25bc7-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="25bc7-116">Infor Kleeblatt (über die [Infor FHIR-Brücke](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="25bc7-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="25bc7-117">Redox (über den [R ^ FHIR-Server](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="25bc7-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="25bc7-118">Dapasoft (über [FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="25bc7-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="25bc7-119">Dieser Prozess enthält keine Schritte, die das Microsoft Teams Admin Center oder PowerShell-Cmdlets verwenden, um Features zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="25bc7-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="25bc7-120">Die Konfiguration erfolgt vollständig auf der FHIR-Server/-Service-Seite und im Patienten-App-Client.</span><span class="sxs-lookup"><span data-stu-id="25bc7-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="25bc7-121">Die folgende Abbildung zeigt die Architektur der App "Patienten":</span><span class="sxs-lookup"><span data-stu-id="25bc7-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagramm der APP-Architektur der Patienten](../../media/patients-app-architecture.png)

<span data-ttu-id="25bc7-123">In den folgenden Abschnitten werden die Anforderungen der FHIR-Datenzugriffsschicht für die Patienten-App erläutert, die ein FHIR-Server (oder EPA-fähige FHIR-APIs) erfüllen muss, um die Integration in die Patienten-APP zu ermöglichen, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="25bc7-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="25bc7-124">Erwartungen bezüglich der Benutzerauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="25bc7-124">Expectations around user authentication</span></span>
- <span data-ttu-id="25bc7-125">Funktionelle und technische Anforderungen der integrationsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="25bc7-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="25bc7-126">Erwartungen bezüglich Leistung und Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="25bc7-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="25bc7-127">Erwartungen rund um FHIR-Ressourcen, die für die Patienten-App unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="25bc7-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="25bc7-128">Integrationsprozess und das erwartete Projektmodell</span><span class="sxs-lookup"><span data-stu-id="25bc7-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="25bc7-129">Erste Schritte mit FHIR und einigen häufigen Herausforderungen, die mit der App "Patienten" konfrontiert sind</span><span class="sxs-lookup"><span data-stu-id="25bc7-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="25bc7-130">Zukünftige Anforderungen für die nächste Iteration der Patienten-App</span><span class="sxs-lookup"><span data-stu-id="25bc7-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="25bc7-131">In den folgenden Abschnitten wird das Wort "Partner" oder "Interop-Partner" verwendet, um auf eine beliebige Organisation von Drittanbietern zu verweisen, die die Integration von EPA-Systemen für die Patienten-App über FHIR ermöglicht und einen FHIR-Server implementiert, der den aufgeführten Spezifikationen entspricht.</span><span class="sxs-lookup"><span data-stu-id="25bc7-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="25bc7-132">Funktionelle und technische Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25bc7-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="25bc7-133">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="25bc7-133">Authentication</span></span>  

<span data-ttu-id="25bc7-134">Autorisierung auf App-Ebene *ohne Unterstützung für die Autorisierung auf Benutzerebene* ist die häufiger unterstützte Möglichkeit, Datentransformationen durchzuführen und Verbindungen zu EPA-Daten über FHIR verfügbar zu machen, auch wenn das EPA-System möglicherweise die Autorisierung auf Benutzerebene implementiert.</span><span class="sxs-lookup"><span data-stu-id="25bc7-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="25bc7-135">Der Interop-Dienst (Partner) erhält erhöhten Zugriff auf die EPA-Daten, und wenn Sie dieselben Daten wie die entsprechenden FHIR-Ressourcen verfügbar machen, wird kein Autorisierungskontext an den Interop-Dienst Consumer (die Patienten-APP) übergeben, der in den Interop-Dienst oder die Plattform integriert ist.</span><span class="sxs-lookup"><span data-stu-id="25bc7-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="25bc7-136">Die Patienten-App kann die Autorisierung auf Benutzerebene nicht erzwingen, unterstützt jedoch die Anwendungsauthentifizierung zwischen der Patienten-APP und dem Dienst des Interop-Partners.</span><span class="sxs-lookup"><span data-stu-id="25bc7-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="25bc7-137">Das Authentifizierungsmodell für die Anwendungs-zu-Anwendung wird im folgenden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="25bc7-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="25bc7-138">Die Dienst-zu-Service-Authentifizierung sollte über den OAuth 2,0- [Client Anmelde Informationsfluss](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)erfolgen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="25bc7-139">Der Partnerdienst muss Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="25bc7-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="25bc7-140">Der Partnerdienst ermöglicht der App "Patienten", ein Konto bei dem Partner zu erstellen, mit dem die Patienten-App client_id und client_secret, die über ein auth-Registrierungs Portal auf dem Authentifizierungsserver des Partners verwaltet werden, generieren und besitzen kann.</span><span class="sxs-lookup"><span data-stu-id="25bc7-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="25bc7-141">Der Partner Dienst besitzt das Authentifizierungs-/Autorisierungssystem, das die bereitgestellten Clientanmeldeinformationen akzeptiert und überprüft (authentifiziert) und ein Zugriffstoken mit Mandanten Hinweis im Bereich zurückgibt, wie nachstehend beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25bc7-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="25bc7-142">Aus Sicherheitsgründen oder im Fall eines geheimen Verstoßes kann die Patienten-App den geheimen Schlüssel neu generieren und das alte Geheimnis ungültig machen oder löschen (Beispiel für das gleiche ist in Azure Portal-Aad-App-Registrierung verfügbar).</span><span class="sxs-lookup"><span data-stu-id="25bc7-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="25bc7-143">Der Metadaten-Endpunkt, der die Konformitäts Anweisung hostet, sollte nicht authentifiziert sein, er sollte ohne Authentifizierungstoken zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="25bc7-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="25bc7-144">Der Partner Dienst stellt den Token-Endpunkt für die patients-App bereit, um mithilfe eines Client Anmelde Informationsflusses ein Zugriffstoken anzufordern.</span><span class="sxs-lookup"><span data-stu-id="25bc7-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="25bc7-145">Die Token-URL als pro autorisierungsserver sollte Teil der FHIR-Konformitäts Anweisung (Capability) sein, die aus Metadaten auf dem FHIR-Server abgerufen wurde, wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="25bc7-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="25bc7-146">Eine Anforderung eines Zugriffstokens besteht aus den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="25bc7-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="25bc7-147">Der Partnerdienst bietet die client_id-und client_secret für die Patienten-APP, die über ein auth-Registrierungs Portal auf der Seite des Partners verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="25bc7-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="25bc7-148">Der Partner Dienst stellt den Endpunkt zum Anfordern des Zugriffstokens mithilfe eines Client Anmelde Informationsflusses bereit.</span><span class="sxs-lookup"><span data-stu-id="25bc7-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="25bc7-149">Eine erfolgreiche Antwort muss die Parameter token_type, access_token und expires_in umfassen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="25bc7-150">Routing: Zuordnen des Aad-Mandanten zum Anbieterendpunkt</span><span class="sxs-lookup"><span data-stu-id="25bc7-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="25bc7-151">Die app "Patienten" stellt über einen einzigen Endpunkt eine Verbindung mit einem Partnerdienst her.</span><span class="sxs-lookup"><span data-stu-id="25bc7-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="25bc7-152">Der Partnerdienst besitzt und verwaltet einen Mechanismus, mit dem jeder Microsoft-Kunde (AAD-Mandanten-ID) einem jeweiligen Gesundheitsdienstleister (FHIR-Server) zugeordnet wird, mit dem der Partnerdienst arbeitet.</span><span class="sxs-lookup"><span data-stu-id="25bc7-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="25bc7-153">Das Zuordnen des Aad-Mandanten zu einem Anbieterendpunkt verwendet die Aad-Mandanten-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="25bc7-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="25bc7-154">Die Patienten-App übergibt die Mandanten-ID im Bereich, während Sie für jede Anforderung ein Access-Token anfordert.</span><span class="sxs-lookup"><span data-stu-id="25bc7-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="25bc7-155">Der Partner Dienst behält die Zuordnung der Mandanten-ID zum Anbieterendpunkt bei und leitet Anforderungen basierend auf der Mandanten-ID an einen Anbieterendpunkt um.</span><span class="sxs-lookup"><span data-stu-id="25bc7-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="25bc7-156">Zu diesem Zweck unterstützt der Partner die Konfiguration am Ende (manuell oder über ein Portal als Teil des Onboarding von Anbieter Organisationen zu Ihrer Interop-Plattform).</span><span class="sxs-lookup"><span data-stu-id="25bc7-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="25bc7-157">Der Workflow für Authentifizierung und Routing wird nachfolgend angezeigt:</span><span class="sxs-lookup"><span data-stu-id="25bc7-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagramm zum Authentifizierungs-und Routing Workflow](../../media/Patient-app-6.png)

1. <span data-ttu-id="25bc7-159">Anfordern eines App-Zugriffstokens durch senden:</span><span class="sxs-lookup"><span data-stu-id="25bc7-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="25bc7-160">Mit einem App-Token Antworten:</span><span class="sxs-lookup"><span data-stu-id="25bc7-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="25bc7-161">Anfordern geschützter Daten mit Zugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="25bc7-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="25bc7-162">Autorisierungsmeldung: Wählen Sie den entsprechenden FHIR-Server aus, zu dem Sie von der Mandanten-ID im Bereich weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="25bc7-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="25bc7-163">Sendet die APP-geschützten Daten vom autorisierten FHIR-Server nach der Authentifizierung mit dem App-Token.</span><span class="sxs-lookup"><span data-stu-id="25bc7-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="25bc7-164">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="25bc7-164">Interfaces</span></span>

<span data-ttu-id="25bc7-165">Spezifische Anrufe und Felder, die von der Patienten-App verwendet werden, sind in den folgenden Artikeln dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="25bc7-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="25bc7-166">Wählen Sie die Schnittstelle aus, die für Ihre FHIR Server/FHIR-APIs gelten soll.</span><span class="sxs-lookup"><span data-stu-id="25bc7-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="25bc7-167">Benutzeroberflächenspezifikation DSTU2</span><span class="sxs-lookup"><span data-stu-id="25bc7-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="25bc7-168">Benutzeroberflächenspezifikation STU3</span><span class="sxs-lookup"><span data-stu-id="25bc7-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="25bc7-169">Leistung und Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="25bc7-169">Performance and Reliability</span></span>

<span data-ttu-id="25bc7-170">Während sich die Patienten-app in der privaten Vorschau befindet, gibt es keine Garantien für die End-to-End-Leistung.</span><span class="sxs-lookup"><span data-stu-id="25bc7-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="25bc7-171">Zu den Leistungsfaktoren zählen die relativen Latenzzeiten aller am Workflow beteiligten Hops, beginnend mit der EPA in der Umgebung des Gesundheitssystems, dem Interop-Partner und dessen Infra, einschließlich des FHIR-Servers und Across zur Office 365-Anwendung für Ökosysteme und Patienten.</span><span class="sxs-lookup"><span data-stu-id="25bc7-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Abbildung der Leistung von Interop-Partnern](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="25bc7-173">Erste Schritte mit FHIR</span><span class="sxs-lookup"><span data-stu-id="25bc7-173">Get started with FHIR</span></span>  

<span data-ttu-id="25bc7-174">Wenn Sie neu bei FHIR sind und einfachen Zugriff auf einen FHIR-Server benötigen, den Sie für die Microsoft Teams EPA-integrationsschnittstelle verfügbar machen können, verfügt Microsoft über einen Open-Source-FHIR-Server, der für alle Entwickler zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="25bc7-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="25bc7-175">Lesen Sie den Artikel [Was ist FHIR Server für Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) , um mehr über den von Microsoft verfügbaren Open-Source-FHIR-Server zu erfahren und ihn für ihre Organisationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="25bc7-176">Sie können auch die HSPC Open Sandbox EPA-Umgebung verwenden, um eine EHR zu erstellen, die auch einen geöffneten FHIR-Server unterstützt und diese Funktion zur Wiedergabe mit der Patienten-App verwendet.</span><span class="sxs-lookup"><span data-stu-id="25bc7-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="25bc7-177">Wir empfehlen, dass Sie die [HSPC-Sandbox-Dokumentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)durchlesen.</span><span class="sxs-lookup"><span data-stu-id="25bc7-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="25bc7-178">Die Sandbox bietet nicht nur eine einfache, UI-orientierte und benutzerfreundliche Methode zum Erstellen, hinzufügen und Bearbeiten von Patienten, sondern bietet Ihnen auch einige Beispiele für die ersten Schritte.</span><span class="sxs-lookup"><span data-stu-id="25bc7-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
