---
title: Erste Schritte mit Teams für Organisationen im Gesundheitswesen
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
ms.reviewer: ''
description: Erste Schritte mit Teams für Organisationen im Gesundheitswesen
ms.openlocfilehash: 15e10a69174787d104a990f8b71a6e8ef4f8be04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147688"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="9f69e-103">Erste Schritte mit Teams für Organisationen im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="9f69e-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="9f69e-104">Microsoft Teams bietet eine Reihe von Funktionen, die für Krankenhäuser und andere Gesundheitsorganisationen nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="9f69e-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="9f69e-105">Die Features von Teams sind derzeit in der Entwicklung, um Krankenhäusern zu helfen:</span><span class="sxs-lookup"><span data-stu-id="9f69e-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="9f69e-106">Pflege Koordination und Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="9f69e-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="9f69e-107">Sicheres Messaging</span><span class="sxs-lookup"><span data-stu-id="9f69e-107">Secure Messaging</span></span>
- <span data-ttu-id="9f69e-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="9f69e-108">Telehealth</span></span>
- <span data-ttu-id="9f69e-109">Integration elektronischer Gesundheitsakte (EPA)</span><span class="sxs-lookup"><span data-stu-id="9f69e-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="9f69e-110">Integration von Arbeitssystemen in ersterLinie</span><span class="sxs-lookup"><span data-stu-id="9f69e-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="9f69e-111">Der Inhalt dieses Abschnitts basiert auf den grundlegenden Funktionen von Teams wie Besprechungen, anrufen und Nachrichten und geht davon aus, dass Sie bereits Teams in Ihrer Organisation bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="9f69e-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="9f69e-112">Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst, [wie Sie Microsoft Teams Ausrollen](../../How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9f69e-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="9f69e-113">Pflege Koordination – Microsoft Teams patients-App</span><span class="sxs-lookup"><span data-stu-id="9f69e-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="9f69e-114">Microsoft Teams verfügt nun über eine speziell für Gesundheitsorganisationen spezifische Pflege Koordinierungs Lösung, die Ihnen hilft, die beste Patientenversorgung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="9f69e-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="9f69e-115">Der Kern der Lösung zur Pflege Koordination, der Microsoft Teams patients-APP, ist eine APP des First-Party-Tabs, die mit einer schnellen Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/))-Schnittstelle integriert wird, die in das System der elektronischen Krankenakte (EPA) integriert ist, um wertvolle medizinische Informationen in Microsoft Teams zusammenzubringen, um die klinische Zusammenarbeit und Kommunikation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9f69e-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="9f69e-116">Die Lösung zur Pflege Koordination kann mit führenden unabhängigen Software Anbietern (Independent Software Vendors, ISVs) verbunden werden, die die Patienten-App mithilfe vorhandener Integritätsdaten Standards wie HL7v2 und FHIR mit ihren EPA-Systemen verbinden können.</span><span class="sxs-lookup"><span data-stu-id="9f69e-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="9f69e-117">Microsoft-Partner mit den folgenden Branchenführern zur Einrichtung elektronischer Integritätsdaten Satz Integration in Teams:</span><span class="sxs-lookup"><span data-stu-id="9f69e-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="9f69e-118">Datica (durch Ihr [CMI](https://datica.com/compliant-managed-integration/) -Angebot)</span><span class="sxs-lookup"><span data-stu-id="9f69e-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="9f69e-119">Infor Kleeblatt (über die [Infor FHIR-Brücke](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="9f69e-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="9f69e-120">Redox (über den [R ^ FHIR-Server](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="9f69e-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="9f69e-121">Dapasoft (über [FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="9f69e-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="9f69e-122">Ein EPA-Integrations-und Interop-Partner, der versucht, Microsoft Teams für eine Organisation des Gesundheitswesens zu implementieren, muss der Patienten-App eine sichere und authentifizierte Verbindung mit den EPA-Systemen des Gesundheits Dienstanbieters bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9f69e-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="9f69e-123">Auf diese Weise kann der unidirektionale (schreibgeschützte) Fluss der relevanten Patientendaten in die Patienten-App übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="9f69e-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="9f69e-124">Die patients-App versteht das FHIR-Format, sodass der Partner auch dafür verantwortlich ist, die aggregierten Daten aus verschiedenen anderen Formaten wie HL7v2 usw. in FHIR DSTU2 oder STU3 zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="9f69e-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![Illustrations-Highlighting-Koordination und Zusammenarbeit](../../media/ehr-1.png)

<br>

<span data-ttu-id="9f69e-126">Die patients-APP ist in elektronische Health Records (EPA)-Systeme integriert und ermöglicht es den Leistungserbringer, in Echtzeit innerhalb der sicheren Plattform von Teams über die Patientenversorgung zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9f69e-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="9f69e-127">Die Patienten-APP ist die erste größere Investition in den Bereich der Pflege Koordination, die sich mit den folgenden Herausforderungen befassen soll:</span><span class="sxs-lookup"><span data-stu-id="9f69e-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="9f69e-128">Geringe Effizienz in der Hand-offs und kritische Kommunikation durch die Patientenerfahrung</span><span class="sxs-lookup"><span data-stu-id="9f69e-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="9f69e-129">Silo-Informationen, die Verwaltungslasten schaffen</span><span class="sxs-lookup"><span data-stu-id="9f69e-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="9f69e-130">Unzufriedenheit von Klinikern mit komplexen und fragmentierten Tools für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="9f69e-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="9f69e-131">Ineffiziente in-Person-Pflege Koordination, die zu viel teure klinische Zeit verbrennen kann</span><span class="sxs-lookup"><span data-stu-id="9f69e-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="9f69e-132">Microsoft Teams ermöglicht es Ärzten, Klinikern, Krankenschwestern und anderen Mitarbeitern, effizient zusammenzuarbeiten, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="9f69e-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="9f69e-133">Teil eines einzelnen virtualisierten Teams, das an Office-Dokumenten arbeitet und zusammenarbeitet</span><span class="sxs-lookup"><span data-stu-id="9f69e-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="9f69e-134">Beständige Unterhaltungen zu unterschiedlichen Patienten, die darauf achten müssen</span><span class="sxs-lookup"><span data-stu-id="9f69e-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="9f69e-135">Verwenden von Kanälen mit Registerkarten als Möglichkeit, ihre Arbeit zu strukturieren, mit zusätzlicher Hilfe von Registerkarten, an die Sie Informationsquellen anheften können</span><span class="sxs-lookup"><span data-stu-id="9f69e-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="9f69e-136">Verwenden von Kanal Besprechungen mit der Leistung von Teams für Audio-, Video-, Bildschirmfreigabe-, Aufzeichnung-und Transkriptions Funktionen zum Verwalten von täglichen Besprechungen</span><span class="sxs-lookup"><span data-stu-id="9f69e-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="9f69e-137">Verwenden Sie die Patienten-APP, um eine Liste von Patienten mit hoher Gefährdung zu kuratiert, die überwacht werden müssen, und ziehen Sie Ihre neuesten Informationen aus dem EPA-System.</span><span class="sxs-lookup"><span data-stu-id="9f69e-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="9f69e-138">Die Patienten-APP selbst fügt Microsoft Teams die folgenden Features hinzu:</span><span class="sxs-lookup"><span data-stu-id="9f69e-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="9f69e-139">Möglichkeit zum Erstellen mehrerer patientenlisten in einem einzigen Kanal</span><span class="sxs-lookup"><span data-stu-id="9f69e-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="9f69e-140">Möglichkeit zum Anzeigen und Sortieren von Informationen, die über Patienten über konfigurierbare Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f69e-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="9f69e-141">Möglichkeit zur automatischen Bereitstellung der APP über eine Teamvorlage</span><span class="sxs-lookup"><span data-stu-id="9f69e-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="9f69e-142">Verfügbar in der Teams-App für IOS und Android für Mobile First Healthcare-Mitarbeiter sowie Microsoft Teams Web-und Desktop-Client.</span><span class="sxs-lookup"><span data-stu-id="9f69e-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="9f69e-143">Unterstützung für FHIR-DSTU2-und STU3-Versionen mithilfe der Analyse der Konformitäts Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9f69e-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="9f69e-144">Überwachungsprotokolle für alle Ansichts-und Suchaktionen auf der Benutzeroberfläche, um Phi pro HIPAA-Richtlinien zu schützen.</span><span class="sxs-lookup"><span data-stu-id="9f69e-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="9f69e-145">Die app "Patienten" basiert auf der Erweiterungs Plattform für Teams und nutzt das Registerkarten-Framework, um umfangreiche Patienten Inhalte in einem Kanal anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f69e-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="9f69e-146">Weitere Informationen zu anderen Teams-apps und der Plattform selbst finden Sie unter [Apps für Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="9f69e-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="9f69e-147">Die Patienten-App befindet sich in der privaten Vorschau, und die FHIR-Schnittstelle befindet sich in Beta.</span><span class="sxs-lookup"><span data-stu-id="9f69e-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="9f69e-148">Es wird davon ausgegangen, dass veröffentlichte Versionen nicht abwärtskompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="9f69e-148">Released versions are not expected to be backward compatible.</span></span>

![Screenshot der App "Patienten" auf Desktop-und mobilen Geräten](../../media/ehr-2.png)

<span data-ttu-id="9f69e-150">Einzelheiten zur Implementierung finden Sie unter [integrieren elektronischer Gesundheitsdatensätze in Microsoft Teams](patients-app.md) .</span><span class="sxs-lookup"><span data-stu-id="9f69e-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="9f69e-151">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9f69e-151">Templates</span></span>

<span data-ttu-id="9f69e-152">Neue Vorlagen für die Erstellung von Teams wurden entwickelt, um auf eine Krankenhauseinstellung anzuwenden, und weitere werden in Kürze erwartet.</span><span class="sxs-lookup"><span data-stu-id="9f69e-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="9f69e-153">Auf diese Weise ist es einfacher, Teams zu erstellen, die von Mitarbeitern des Gesundheitswesens zur Koordinierung der Versorgung von Patienten in verschiedenen Abteilungen oder Stationen eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9f69e-153">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="9f69e-154">Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen für Organisationen im Gesundheitswesen](healthcare-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9f69e-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="9f69e-155">Teams können für interne Abteilungen wie Kardiologie oder für Pflegestationen gestartet werden, und weitere Vorlagen befinden sich in der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="9f69e-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="9f69e-156">Sicheres Messaging</span><span class="sxs-lookup"><span data-stu-id="9f69e-156">Secure Messaging</span></span>

<span data-ttu-id="9f69e-157">Secure Messaging unterstützt die Zusammenarbeit in Care Teams, einschließlich mehrerer neuer Funktionen:</span><span class="sxs-lookup"><span data-stu-id="9f69e-157">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="9f69e-158">Ein Nachrichtenabsender kann eine besondere Priorität für seine Nachricht festzulegen, sodass der Empfänger wiederholt benachrichtigt wird, bis er die Nachricht gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="9f69e-158">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="9f69e-159">Ein Nachrichtenabsender kann eine Lesebestätigung anfordern, damit er benachrichtigt wird, wenn eine von Ihnen gesendete Nachricht vom Empfänger der Nachricht gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f69e-159">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="9f69e-160">Zusammen ermöglichen diese Features eine schnellere Berücksichtung dringender Nachrichten und die Gewissheit, dass die Nachricht empfangen und gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f69e-160">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="9f69e-161">Neue Betreuerteams, die diese Funktionen verwenden, können für jeden Patienten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f69e-161">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="9f69e-162">Diese Features sind Richtlinien basiert und können Einzelpersonen oder gesamten Teams zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9f69e-162">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="9f69e-163">Weitere Informationen finden Sie unter [Erste Schritte mit Richtlinien für sichere Nachrichten für Organisationen im Gesundheitswesen](messaging-policies-hc.md) .</span><span class="sxs-lookup"><span data-stu-id="9f69e-163">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="9f69e-164">Im Zusammenhang mit Secure Messaging können auch andere Mandanten von Organisationen des Gesundheitswesens verbunden werden, was eine umfassendere Kommunikation zwischen Mandanten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9f69e-164">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="9f69e-165">(siehe [Verwalten des externen Zugriffs (Föderation) in Microsoft Teams](../../manage-external-access.md)).</span><span class="sxs-lookup"><span data-stu-id="9f69e-165">(see [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="9f69e-166">Integration von First-Worker-Arbeitskräften</span><span class="sxs-lookup"><span data-stu-id="9f69e-166">Firstline Worker integration</span></span>

<span data-ttu-id="9f69e-167">Microsoft Teams ist in die First-Worker-Anwendung integriert, mit der Sie die Funktionen von Shift-Mitarbeitern koordinieren können, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="9f69e-167">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="9f69e-168">Lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="9f69e-168">See the following articles:</span></span>

- [<span data-ttu-id="9f69e-169">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f69e-169">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="9f69e-170">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f69e-170">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
