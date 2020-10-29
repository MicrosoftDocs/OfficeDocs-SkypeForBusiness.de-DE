---
title: Teams für virtuelle Besuche
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Einrichten Ihres virtuellen Besuchs Systems mithilfe von Microsoft Teams
ms.openlocfilehash: ed952f678fb353ae623a0020ac565ee4e8288445
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790457"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="718e9-103">Virtuelle Besuche mit Teams – Integration in EPA</span><span class="sxs-lookup"><span data-stu-id="718e9-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="718e9-104">Der Microsoft Teams Electronic Health Record (EHR) Connector macht es Klinikern einfach, einen virtuellen Patienten Besuch oder eine Konsultation mit einem anderen Anbieter in Teams direkt aus dem EPA-System zu starten.</span><span class="sxs-lookup"><span data-stu-id="718e9-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="718e9-105">Microsoft Teams, das auf der Microsoft 365-Cloud basiert, ermöglicht eine einfache, sichere Zusammenarbeit und Kommunikation mit Chat-, Video-, sprach-und Gesundheitstools in einem einzigen Hub, der die Compliance mit HIPAA, HITECH-Zertifizierung und vielem mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="718e9-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="718e9-106">Die Kommunikations-und Zusammenarbeitsplattform von Teams macht es Klinikern einfach, die Übersichtlichkeit fragmentierter Systeme zu durch Schneiden, damit Sie Zeit damit verbringen können, die bestmögliche Versorgung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="718e9-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="718e9-107">Microsoft Teams Electronic Health Record (EHR) Connector kann:</span><span class="sxs-lookup"><span data-stu-id="718e9-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="718e9-108">Starten Sie virtuelle Besuche von Teams sowohl über Anbieter-als auch über Patienten Portale.</span><span class="sxs-lookup"><span data-stu-id="718e9-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="718e9-109">Schreiben Sie zurück in die EPA-Metadaten bei Connect-und Disconnect-Ereignissen, um automatische Überwachung und Datensatzspeicherung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="718e9-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="718e9-110">Integrieren Sie in vorhandene Klinik-und Patienten Workflows, während Sie Microsoft Teams verwenden können.</span><span class="sxs-lookup"><span data-stu-id="718e9-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="718e9-111">Schauen Sie sich das Video an, wie Sie virtuelle Besuche im EPA-Portal verwalten können.</span><span class="sxs-lookup"><span data-stu-id="718e9-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="718e9-112">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="718e9-112">Before you begin</span></span>

<span data-ttu-id="718e9-113">Sie müssen sicherstellen, dass Sie über die folgenden Voraussetzungen verfügen, bevor Sie den EHR-Connector integrieren können:</span><span class="sxs-lookup"><span data-stu-id="718e9-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="718e9-114">Aktives Abonnement von Microsoft Cloud für Healthcare oder Abonnement für das Standalone-Angebot von Microsoft Teams EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="718e9-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="718e9-115">Benutzer müssen über eine geeignete Microsoft 365-oder Office 365-Lizenz verfügen, die Microsoft Teams-Besprechungen enthält.</span><span class="sxs-lookup"><span data-stu-id="718e9-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="718e9-116">Microsoft Teams sollten innerhalb der Organisation angenommen und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="718e9-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="718e9-117">Organisationen müssen mit epic-Version November 2018 oder höher verfügen.</span><span class="sxs-lookup"><span data-stu-id="718e9-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="718e9-118">Ihre Systeme müssen alle [Voraussetzungen für Software und Browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="718e9-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="718e9-119">Darüber hinaus benötigen Sie Informationen von den folgenden Personen in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="718e9-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="718e9-120">Microsoft 365-Administrator</span><span class="sxs-lookup"><span data-stu-id="718e9-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="718e9-121">Epic-Administrator</span><span class="sxs-lookup"><span data-stu-id="718e9-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="718e9-122">Fordern Sie Ihren epischen Administrator auf, den im epic Marketplace verfügbaren Leitfaden für die Epic-Microsoft Teams für die Telehealth-Integration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="718e9-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="718e9-123">Connector-Setup</span><span class="sxs-lookup"><span data-stu-id="718e9-123">Connector setup</span></span>

<span data-ttu-id="718e9-124">Die Einrichtung des Connectors erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="718e9-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="718e9-125">Starten des EPA-Connector-Konfigurations Portals</span><span class="sxs-lookup"><span data-stu-id="718e9-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="718e9-126">Konfigurieren von Informationen zur Anbieterorganisation</span><span class="sxs-lookup"><span data-stu-id="718e9-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="718e9-127">Überprüfen und genehmigen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="718e9-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="718e9-128">Überprüfen und Beenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="718e9-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="718e9-129">Starten des EPA-Connector-Konfigurations Portals</span><span class="sxs-lookup"><span data-stu-id="718e9-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="718e9-130">Wenn Sie Ihre Gesundheitsorganisation so konfigurieren, dass virtuelle Besuche mit Microsoft Teams gestartet werden, starten Sie das EPA-Connector-Konfigurations Portal.</span><span class="sxs-lookup"><span data-stu-id="718e9-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="718e9-131">Verwenden Sie die Test-URL, um den Connector für Ihre epische Testumgebung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="718e9-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="718e9-132">Verwenden Sie die Produktions-URL, wenn Sie bereit sind, ihre epische Produktionsumgebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="718e9-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="718e9-133">Test Umgebung [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="718e9-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="718e9-134">Produktionsumgebung [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="718e9-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="718e9-135">Der Microsoft 365-Administrator und der epic-Administrator Ihrer Organisation müssen die Informations-und Integrationsschritte im Konfigurations Portal ausführen.</span><span class="sxs-lookup"><span data-stu-id="718e9-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="718e9-136">Für epische Konfigurationsschritte wenden Sie sich an die epische Ressource, die Ihrer Organisation zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="718e9-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="718e9-137">Konfigurieren von Informationen zur Anbieterorganisation</span><span class="sxs-lookup"><span data-stu-id="718e9-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="718e9-138">Dieser Schritt muss vom Microsoft 365-Administrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="718e9-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="718e9-139">Der Microsoft 365-Administrator muss das Connector-Konfigurations Portal starten und sich mit Microsoft-Anmeldeinformationen anmelden, um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="718e9-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="718e9-140">Um diesen Schritt ausführen zu können, muss der Microsoft 365-Administrator eine gültige FHIR-Basis-URL von Ihrem Microsoft 365-Administrator und den Benutzernamen des epischen Administrators erhalten, der die Konfiguration genehmigen wird.</span><span class="sxs-lookup"><span data-stu-id="718e9-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="718e9-141">Der Microsoft 365-Administrator muss die Seite Connector-Konfiguration starten und sich mit Microsoft-Anmeldeinformationen anmelden, um den Konfigurationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="718e9-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="718e9-142">Die FHIR-Basis-URL ist eine statische Adresse, die Ihrem Server-FHIR-API-Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="718e9-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="718e9-143">Eine Beispiel-URL ist [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .</span><span class="sxs-lookup"><span data-stu-id="718e9-143">An example URL is [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST).</span></span>

- <span data-ttu-id="718e9-144">Name der Konfigurations genehmigenden Person ist der Name des epischen Systemadministrators, der für die Genehmigung der Konfiguration verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="718e9-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![Der Name der Konfigurations genehmigenden Person wird aus einer Liste im EPA-Connector ausgewählt.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="718e9-146">Überprüfen und genehmigen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="718e9-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="718e9-147">Der epic-Administrator für Ihre Gesundheitsorganisation, der als genehmigende Person hinzugefügt wurde, muss nun dieselbe EPA-Connector-URL aus dem vorherigen Schritt verwenden, um sich mit den Microsoft 365-Anmeldeinformationen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="718e9-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="718e9-148">Nach erfolgreicher Überprüfung wird die genehmigende Person aufgefordert, sich mit ihren epischen Anmeldeinformationen anzumelden, um die epische Organisation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="718e9-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="718e9-149">Der Microsoft 365-Administrator und der epic-Administrator in ihren Organisationen können dieselbe Person sein.</span><span class="sxs-lookup"><span data-stu-id="718e9-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="718e9-150">In diesem Fall fügen Sie im ersten Schritt ihren eigenen Benutzernamen als genehmigende Person hinzu.</span><span class="sxs-lookup"><span data-stu-id="718e9-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="718e9-151">Sie müssen sich weiterhin bei epic anmelden, um Ihren Zugriff zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="718e9-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="718e9-152">Die epische Anmeldung wird nur zur Überprüfung ihrer FHIR-Basis-URL verwendet.</span><span class="sxs-lookup"><span data-stu-id="718e9-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="718e9-153">Microsoft speichert keine Anmeldeinformationen oder keinen Zugriff auf EHR-Daten mit dieser Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="718e9-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Überprüfen und genehmigen der Anmeldeinformationen-Konfiguration](../../media/ehc-provider-2.png)

<span data-ttu-id="718e9-155">Nach einer erfolgreichen epischen Anmeldung **muss** der epic-Administrator die Konfiguration genehmigen.</span><span class="sxs-lookup"><span data-stu-id="718e9-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="718e9-156">Wenn die Konfiguration nicht korrekt ist, kann der Microsoft 365-Administrator die ursprünglichen Konfigurationen ändern, indem Sie sich erneut beim Microsoft EPA Connector-Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="718e9-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Vergewissern Sie sich, dass der EHR-Connector konfiguriert ist, und wählen Sie die Option zum Ändern der Konfiguration aus.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="718e9-158">Überprüfen und Beenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="718e9-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="718e9-159">Wenn die Konfigurationsinformationen vom epic-Administrator genehmigt wurden, werden Ihnen Integrations Einträge für den Start des Patienten und des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="718e9-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="718e9-160">Diese Einträge sind notwendig, um die virtuelle Besuchs Konfiguration in epic abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="718e9-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="718e9-161">Weitere Informationen finden Sie im Epic-Microsoft Teams Telehealth Integration Guide.</span><span class="sxs-lookup"><span data-stu-id="718e9-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="718e9-162">Der Microsoft 365-oder epic-Administrator kann sich bei Bedarf beim Konfigurations Portal anmelden, um integrationsdatensätze anzuzeigen und die Organisationskonfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="718e9-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Die Integrationsinformationen werden angezeigt.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="718e9-164">Virtuelle Besuche von Teams starten</span><span class="sxs-lookup"><span data-stu-id="718e9-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="718e9-165">Nachdem Sie die EPA-Connector-Schritte und die epische Konfiguration abgeschlossen haben, ist Ihre Organisation bereit, Video Besuche mit Microsoft Teams zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="718e9-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="718e9-166">Voraussetzungen für virtuelle Besuche</span><span class="sxs-lookup"><span data-stu-id="718e9-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="718e9-167">Ihre Systeme müssen alle [Voraussetzungen für Software und Browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="718e9-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="718e9-168">Die Organisation des Gesundheitswesens muss das Setup zwischen der epischen Organisation und der Microsoft 365-Organisation abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="718e9-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="718e9-169">Anbieter Erfahrung</span><span class="sxs-lookup"><span data-stu-id="718e9-169">Provider experience</span></span>

<span data-ttu-id="718e9-170">Gesundheitsdienstleister aus Ihrer Organisation können auch an virtuellen besuchen mit Microsoft Teams aus ihren epischen Anbieter Anwendungen (Hyperraum, Haiku, Canto) teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="718e9-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="718e9-171">Die Schaltfläche **Virtueller Besuch beginnen** ist in den Anbieter Fluss eingebettet.</span><span class="sxs-lookup"><span data-stu-id="718e9-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="718e9-172">Die wichtigsten Features der Anbieter Oberfläche:</span><span class="sxs-lookup"><span data-stu-id="718e9-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="718e9-173">Anbieter können mit unterstützten Browsern oder der Microsoft Teams-Anwendung an virtuellen besuchen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="718e9-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="718e9-174">Anbieter müssen eine einmalige Anmeldung mit Ihrem Microsoft 365-Konto durchführen, wenn Sie sich zum ersten Mal an einem virtuellen Besuch beteiligen.</span><span class="sxs-lookup"><span data-stu-id="718e9-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="718e9-175">Nach der einmaligen Anmeldung wird der Anbieter direkt zu dem virtuellen Termin in Microsoft Teams weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="718e9-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="718e9-176">(Der Anbieter muss bei Microsoft Teams angemeldet sein).</span><span class="sxs-lookup"><span data-stu-id="718e9-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="718e9-177">Der Anbieter kann Echtzeitupdates der Teilnehmer sehen, die für einen bestimmten Termin eine Verbindung herstellen und die Verbindung trennen.</span><span class="sxs-lookup"><span data-stu-id="718e9-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="718e9-178">Der Anbieter kann sehen, wann der Patient mit einem virtuellen Besuch verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="718e9-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Anbieter Erfahrung bei einem virtuellen Besuch mit Patienten](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="718e9-180">Patientenerfahrung</span><span class="sxs-lookup"><span data-stu-id="718e9-180">Patient experience</span></span>

<span data-ttu-id="718e9-181">Der Connector unterstützt Patienten bei der Teilnahme an virtuellen besuchen über myChart Web und Mobile.</span><span class="sxs-lookup"><span data-stu-id="718e9-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="718e9-182">Zum Zeitpunkt der Ernennung können die Patienten über die Schaltfläche **Virtueller Besuch beginnen** einen virtuellen Besuch von myChart beginnen.</span><span class="sxs-lookup"><span data-stu-id="718e9-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="718e9-183">Die wichtigsten Funktionen der Patientenerfahrung:</span><span class="sxs-lookup"><span data-stu-id="718e9-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="718e9-184">Patienten können an virtuellen besuchen von modernen Webbrowsern auf Desktop-und Mobiltelefonen ohne App-Installation teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="718e9-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="718e9-185">Patienten können mit nur einem Mausklick an virtuellen besuchen teilnehmen, und es gibt kein zusätzliches Konto oder keine Anmeldung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="718e9-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="718e9-186">Patienten müssen kein Microsoft-Konto erstellen oder sich anmelden, um einen virtuellen Besuch zu starten.</span><span class="sxs-lookup"><span data-stu-id="718e9-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="718e9-187">Die Patienten werden in eine Lobby gestellt, bis der Leistungserbringer sich dem Termin anschließt und Sie dem virtuellen Besuch zugibt.</span><span class="sxs-lookup"><span data-stu-id="718e9-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="718e9-188">Das Testen von Video und Mikrofon steht in der Lobby zur Verfügung, bevor Sie sich dem virtuellen Besuch anschließen.</span><span class="sxs-lookup"><span data-stu-id="718e9-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Patientenerfahrung beim virtuellen Besuch](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="718e9-190">Epic, myChart, Haiku und Canto sind Marken von epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="718e9-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="718e9-191">Datenschutz und Speicherort der Daten</span><span class="sxs-lookup"><span data-stu-id="718e9-191">Privacy and location of data</span></span>

<span data-ttu-id="718e9-192">Die Integration von Teams in EPA-Systeme optimiert die Menge der Daten, die während der Integration und beim virtuellen Besuchs Fluss verwendet und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="718e9-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="718e9-193">Die Lösung folgt den allgemeinen Prinzipien und Richtlinien für die Datenverwaltung in Teams, die in den Datenschutzbestimmungen von Teams erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="718e9-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="718e9-194">Der Microsoft Teams EHR Connector speichert und übermittelt keine identifizierbaren personenbezogenen Daten oder Gesundheitsaufzeichnungen von Patienten oder Leistungserbringer aus dem EPA-System.</span><span class="sxs-lookup"><span data-stu-id="718e9-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="718e9-195">Die einzigen Daten, die vom EPA-Connector gespeichert werden, sind die eindeutige ID des EPA-Benutzers, die während der Einrichtung von Teams verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="718e9-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="718e9-196">Die eindeutige ID des EPA-Benutzers wird in einer der drei geografischen Regionen gespeichert, die in dem Artikel, in dem [Ihre Microsoft 365-Kundendaten gespeichert sind,](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="718e9-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="718e9-197">Alle Chats, Aufzeichnungen und anderen Daten, die von den Besprechungsteilnehmern in Teams eingegeben wurden, werden gemäß den vorhandenen Speicherrichtlinien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="718e9-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="718e9-198">Wenn Sie weitere Informationen zum Speicherort von Daten in Microsoft Teams erfahren möchten, besuchen Sie die [Speicherorte von Daten in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="718e9-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
