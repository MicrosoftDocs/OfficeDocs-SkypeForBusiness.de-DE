---
title: Neuerungen in Skype for Business Server 2019 | Funktionen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: diese Funktionen sind neu in Skype for Business Server 2019.'
ms.openlocfilehash: 6db5ea6589a56f696f233854372fc95d6064fed7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799415"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="4a6b4-103">Was ist in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4a6b4-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="4a6b4-104">**Zusammenfassung:** In diesem Thema finden Sie Informationen zu den neuen Funktionen in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="4a6b4-105">Zu den neuen Funktionen in Skype for Business Server 2019 gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="4a6b4-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="4a6b4-106">Cloudvoicemail</span><span class="sxs-lookup"><span data-stu-id="4a6b4-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="4a6b4-107">Anrufdatenconnector</span><span class="sxs-lookup"><span data-stu-id="4a6b4-107">Call Data Connector</span></span>
- <span data-ttu-id="4a6b4-108">Parallele Migration</span><span class="sxs-lookup"><span data-stu-id="4a6b4-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="4a6b4-109">Unified Messaging-Dienste: Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="4a6b4-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="4a6b4-110">Exchange um bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="4a6b4-111">Aufgrund von Änderungen an der Unterstützung in Exchange 2019 wird die Exchange um-Integration zu Gunsten der Features Cloud Voicemail und Cloud-automatische Telefonzentrale de-hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="4a6b4-112">Mit Cloud Voicemail können alle Ihre Skype for Business 2019-Benutzer&#x2014;, ob Sie lokal oder Online&#x2014;auf den gleichen Voicemaildienst in der Microsoft-Cloud zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="4a6b4-113">Cloud Voicemail bietet die folgenden Vorteile für Ihre lokalen und Online Benutzer:</span><span class="sxs-lookup"><span data-stu-id="4a6b4-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="4a6b4-114">Zugriff auf Voicemail in Ihrem Exchange-Postfach mithilfe der Skype for Business Online-, Teams-oder Outlook-Clients</span><span class="sxs-lookup"><span data-stu-id="4a6b4-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="4a6b4-115">Möglichkeit zur Verwendung des webbasierten Portals zum Verwalten der Voicemail-Optionen</span><span class="sxs-lookup"><span data-stu-id="4a6b4-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="4a6b4-116">Weitere Informationen finden Sie unter [Planen des Cloud Voicemail-Diensts](../sfbhybrid/hybrid/plan-cloud-voicemail.md) und [Planen der Skype for Business Server-und Exchange Server-Migration](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="4a6b4-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="4a6b4-117">Anrufüberwachung: Anrufdaten-Konnektor</span><span class="sxs-lookup"><span data-stu-id="4a6b4-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="4a6b4-118">Der Anruf Datenkonnektor vereinfacht die Anrufüberwachung in einer Hybridumgebung erheblich, da Sie keine unterschiedlichen lokalen und Online Tools mehr verwenden müssen, um die Anrufqualität Ihrer Benutzer zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="4a6b4-119">Unabhängig davon, ob Ihre Benutzer lokal oder online sind, können Sie festlegen, dass die Anrufqualität für Ihre gesamte Organisation online angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="4a6b4-120">Mit Call Data Connector können Sie die folgenden Aufgaben mithilfe eines einzelnen Toolsets ausführen:</span><span class="sxs-lookup"><span data-stu-id="4a6b4-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="4a6b4-121">Überwachen Sie Ihre Benutzererfahrung in Microsoft Teams, Skype for Business Online und Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="4a6b4-122">Anzeigen und Beheben von Problemen in Ihrem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="4a6b4-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="4a6b4-123">Weisen Sie Helpdesk-und Administratorrollen für die anrufanalyse zu, damit Sie Helpdesk-Mitarbeitern die Möglichkeit geben können, ihre Zuständigkeitsbereiche anzuzeigen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="4a6b4-124">Weitere Informationen finden Sie unter [Planen von Anrufdaten-Konnektoren](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="4a6b4-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="4a6b4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a6b4-125">See also</span></span>

[<span data-ttu-id="4a6b4-126">Was ist in Skype for Business Server 2019 veraltet?</span><span class="sxs-lookup"><span data-stu-id="4a6b4-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
