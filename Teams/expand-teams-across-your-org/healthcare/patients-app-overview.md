---
title: 'Patienten-App für Teams-Administratoren '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Patienten-App für Teams-Administratoren
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749557"
---
# <a name="patients-app-overview"></a><span data-ttu-id="b3f2e-103">Übersicht der Patienten-App</span><span class="sxs-lookup"><span data-stu-id="b3f2e-103">Patients app overview</span></span>

<span data-ttu-id="b3f2e-104">Die patients-Anwendung ist eine Microsoft Teams Store-App, die für alle Teams-Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="b3f2e-105">Die APP ermöglicht es Patienten Teams aus klinischen Arbeitern (wie Krankenschwestern, Ärzten, Sozialarbeitern), Listen von Patienten für Szenarien, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen, zu kuratiert und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="b3f2e-106">Die APP hat zwei Modi:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-106">The app has two modes:</span></span> 

- <span data-ttu-id="b3f2e-107">Der EMR-verbundene Modus, der über FHIR eine Verbindung mit EMRs herstellt.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="b3f2e-108">Die EMR-App für den verbundenen Modus bleibt in der privaten Vorschau und interessierte Kunden oder Administratoren können den Zugriff auf die APP anfordern, indem Sie Microsoft eine e-Mail unter teamsforhealthcare@Service.Microsoft.com mit Informationen zu Ihrem Office 365-Mandanten ablegen.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="b3f2e-109">Der manuelle Modus, in dem Betreuerteams die Patienteninformationen manuell hinzufügen/einbringen können.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="b3f2e-110">Die Anwendung ist im Teams-App-Store verfügbar, damit Endbenutzer standardmäßig heruntergeladen werden und in der öffentlichen Vorschau angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="b3f2e-111">Die APP kann mithilfe von [App-Setup Richtlinien in Microsoft Teams](../../teams-app-setup-policies.md) auf bestimmte Benutzer Abschnitte beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="b3f2e-112">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="b3f2e-112">Usage example</span></span>

<span data-ttu-id="b3f2e-113">Während der runden Sitzungen bei jeder Schicht in medizinischen Stationen versammeln sich Kliniker an der Krankenstation, um über die neuesten Updates über den Fortschritt bei Patienten in der Gemeinde zu diskutieren.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="b3f2e-114">Sie betonen die wichtigsten wichtigen Metriken (nicht unbedingt medizinisch oder ausdrücklich auf die medizinischen Unterlagen der Patienten) und stellen sicher, dass der Patient auf dem richtigen Gleitweg zur Entladung ist, basierend auf seiner Diagnose.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="b3f2e-115">Um diese Patienten umrunden zu können, richtet die Krankenschwester die Patienten-app in einem Team ein, in dem alle Ärzte hinzugefügt werden und Patienten zu einer Patientenliste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="b3f2e-116">Während der Runde greifen die Krankenschwestern und die anderen Betreuer für den Patienten auf die Microsoft Teams und die Patienten-App auf Ihren mobilen Geräten zu und aktualisieren relevante Patienteninformationen auf Ihrem Gerät, und alle anderen Personen im Betreuerteam können diese Updates und Notizen sehen und bleiben Sie synchron. Zweimal am Tag, am Anfang und am Ende einer Schicht, haben Sie auch mehrere displicinary-Teambesprechungen, um über die Patientenliste zu wechseln und die Patienten-APP zu verwenden, um sich selbst zu beerdigen und Informationen über jeden Patienten über die Patienten-App auf einem größeren Bildschirm zu teilen.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="b3f2e-117">Oft können sich bestimmte Kliniker auch Remote in diese Teams einwählen und dennoch Teil der Diskussion sein.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="b3f2e-118">Konfigurieren der Patienten-App</span><span class="sxs-lookup"><span data-stu-id="b3f2e-118">Configure Patients app</span></span>

<span data-ttu-id="b3f2e-119">Informationen dazu, wie Sie Ihre Umgebung auf die Verwendung der EMR-Modus-Patienten-App vorbereiten, finden Sie unter [integrieren elektronischer Gesundheitsdatensätze in Microsoft Teams](patients-app.md).</span><span class="sxs-lookup"><span data-stu-id="b3f2e-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="b3f2e-120">Außerdem müssen Sie [in Microsoft Teams die Richtlinien für die APP-Einrichtung verwalten](../../teams-app-setup-policies.md) anzeigen, um die Patienten-App für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="b3f2e-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b3f2e-121">Related topics</span></span>

[<span data-ttu-id="b3f2e-122">Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3f2e-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
