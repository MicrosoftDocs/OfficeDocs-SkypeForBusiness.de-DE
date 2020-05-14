---
title: Planen einer Cloud-Anrufwarteschlange
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung einer automatischen Cloud-Telefonzentrale mit Skype for Business Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221305"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="c0442-103">Planen von Cloud-Anrufwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="c0442-103">Plan Cloud call queues</span></span>

<span data-ttu-id="c0442-104">Cloud-Anrufwarteschlange ist ein Dienst, der Kundenanrufe akzeptiert, eine grußmeldung abgibt und diese Anrufe dann in einer Warteschlange platziert, während eine vorkonfigurierte Liste mit Agents durchsucht wird, um diese Anrufe zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="c0442-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="c0442-105">Sie können die Gruppe von Agents in e-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren.</span><span class="sxs-lookup"><span data-stu-id="c0442-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="c0442-106">Ihre Organisation kann eine oder mehrere Anrufwarteschlangen haben.</span><span class="sxs-lookup"><span data-stu-id="c0442-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="c0442-107">Anrufwarteschlangen werden in der Regel in Kombination mit automatischen Telefonzentralen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0442-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="c0442-108">Darüber hinaus können Cloud-Anrufwarteschlangen Folgendes bieten:</span><span class="sxs-lookup"><span data-stu-id="c0442-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="c0442-109">Musik, während Anrufer auf die Warteschleife warten</span><span class="sxs-lookup"><span data-stu-id="c0442-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="c0442-110">Angepasste Einstellungen für maximale Größe, Timeout und Anruf Behandlungsoptionen für die Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="c0442-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="c0442-111">Jeder Anrufwarteschlange wird ein **Ressourcenkonto** (siehe [Configure Resource Accounts](configure-onprem-ra.md)) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschlange im Microsoft Teams Admin Center verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="c0442-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c0442-112">Weitere Informationen dazu, welche Anrufwarteschlangen und welche Optionen und Funktionen für Anrufwarteschlangen vorhanden sind, finden Sie unter [Erstellen einer Warteschlange für Cloud-Anrufe](/MicrosoftTeams/create-a-phone-system-call-queue) .</span><span class="sxs-lookup"><span data-stu-id="c0442-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="c0442-113">Sie können einer Anrufwarteschlange mehrere Telefonnummern zuweisen, Sie müssen jedoch Microsoft-Dienstnummern, direkte Routing Nummern oder Hybrid Nummern sein.</span><span class="sxs-lookup"><span data-stu-id="c0442-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0442-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0442-114">Requirements</span></span>

<span data-ttu-id="c0442-115">Bei den folgenden Anforderungen wird vorausgesetzt, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="c0442-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="c0442-116">Ihre Anforderungen hängen von Ihrem Szenario ab:</span><span class="sxs-lookup"><span data-stu-id="c0442-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="c0442-117">Für eine neue Konfiguration von Cloud-Anrufwarteschlangen führen Sie die unter [Configure Resource Accounts](configure-onprem-ra.md)beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="c0442-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="c0442-118">Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen, und Sie müssen möglicherweise auch eine Telefonnummer der Anrufwarteschlange zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c0442-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="c0442-119">Zusätzlich zu den oben aufgeführten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Anrufwarteschlangen-Dienst hergestellt wird:</span><span class="sxs-lookup"><span data-stu-id="c0442-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="c0442-120">Hybrid Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="c0442-120">Hybrid connectivity.</span></span> <span data-ttu-id="c0442-121">Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloud-Anrufwarteschlangen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie eine hybride Konnektivität zwischen Ihren lokalen und Online-Umgebungen eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="c0442-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c0442-122">Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0442-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="c0442-123">Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c0442-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="c0442-124">Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die virtuelle Benutzerlizenz für das ﻿kostenlose Telefon System verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0442-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="c0442-125">Dadurch werden Telefon System Funktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können eine automatische Telefonzentrale und Funktionen für die Anrufwarteschlange erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0442-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="c0442-126">Erstellen Sie für jede Anrufwarteschlange ein lokales [Ressourcenkonto](configure-onprem-ra.md) , und weisen Sie bei Bedarf eine Lizenz und eine Telefonnummer zu.</span><span class="sxs-lookup"><span data-stu-id="c0442-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="c0442-127">Zusätzliche Planungsressourcen</span><span class="sxs-lookup"><span data-stu-id="c0442-127">Additional planning resources</span></span>

<span data-ttu-id="c0442-128">Das Lernprogramm mit dem Titel [Small Business Beispiel: Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) durchläuft den Prozess der Erfassung von Informationen zu Benutzeranforderungen, der Planung einer Struktur von automatischen Telefonzentralen und Benutzern (und möglicherweise auch von Anrufwarteschlangen), dem Schreiben der Menüansagen und dem Implementieren des Plans im Online Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c0442-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="c0442-129">Lesen Sie das Lernprogramm, und verwenden Sie die Übungen dort t erstellen Sie Ihren Plan.</span><span class="sxs-lookup"><span data-stu-id="c0442-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="c0442-130">Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit [Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)fort.</span><span class="sxs-lookup"><span data-stu-id="c0442-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0442-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0442-131">See Also</span></span>

[<span data-ttu-id="c0442-132">Konfigurieren von Ressourcenkonten</span><span class="sxs-lookup"><span data-stu-id="c0442-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="c0442-133">Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben</span><span class="sxs-lookup"><span data-stu-id="c0442-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="c0442-134">Was sind automatische Cloudtelefonzentralen?</span><span class="sxs-lookup"><span data-stu-id="c0442-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="c0442-135">Einrichten einer automatischen Cloudtelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="c0442-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="c0442-136">Planen der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="c0442-136">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="c0442-137">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="c0442-137">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="c0442-138">Verwalten von Ressourcenkonten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0442-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
