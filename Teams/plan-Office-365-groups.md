---
title: Planen von Office 365-Gruppen beim Erstellen von Teams in Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informieren Sie sich über die Entscheidungen, die Sie bei der Planung für Office 365-Gruppen treffen sollten, wie beispielsweise das auswählen öffentlicher und privater Gruppen, die Verwendung des Teams-Clients oder die Office 365-Administrator-Webkonsole, und erfahren Sie, wie Sie Ihre Teams über die Verwendung von Unterhaltungen
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 092a30be3fb8cffce8abfc9b885e3de3caa8bed4
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833835"
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="8c4b8-103">Planen von Office 365-Gruppen beim Erstellen von Teams in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c4b8-103">Plan for Office 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="8c4b8-p101">Berücksichtigen Sie bei Ihren Überlegungen zur Verwendung von Office 365-Gruppen oder beim Erstellen von Teams, wozu das Team verwendet werden soll, wer Zugriff haben soll und welches Ergebnis das Team erzielen möchte. Widmen Sie der Anzahl der Kanäle, die Sie erstellen, besondere Aufmerksamkeit, da Benutzer zu weit (über zu viele Kanäle) verteilte Inhalte schnell als überwältigend empfinden.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-p101">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve. Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="8c4b8-106">Es gibt zwei Szenarien im Zusammenhang mit der Planung von Office 365-Gruppen und ihren Auswirkungen auf (oder durch) Microsoft Teams, die der Erläuterung bedürfen:</span><span class="sxs-lookup"><span data-stu-id="8c4b8-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="8c4b8-p102">Da Kunden möglicherweise bereits in Gruppen tätig sind, unterstützen wir derzeit sowohl öffentliche als auch private Gruppen mit weniger als 5000 Mitgliedern. Wie bereits erwähnt, möchten Sie die Mitgliedschaft von Personen in einem Team mithilfe des Teams-Clients und nicht der Office 365-Administrator-Webkonsole verwalten. In diesem Fall ist es sinnvoll, wenn Personen für Thread Unterhaltungen in Office 365-Gruppen verwendet werden, dass eine Gruppenunterhaltung im Wesentlichen eine e-Mail und nicht die gleiche wie eine Chatnachricht in einem Teams-Kanal ist. Informieren Sie Ihre Mitarbeiter über diesen Unterschied, und empfehlen Sie, das flexiblere Chatnachrichten Format in Teams zu übernehmen, anstatt die Gruppe mithilfe von Outlook oder OWA per e-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-p102">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members. As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console. Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel. Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="8c4b8-p103">Für Kunden, die in Office 365 keine vorhandenen Gruppen definiert haben, können Sie diese entweder mithilfe des Office 365-Administrator Portals, des Teams Web oder der Desktop Clients erstellen. Wie bereits erwähnt, verwalten Sie alle zukünftigen Mitgliedschaften in der Office 365-Gruppe mithilfe des Teams-Clients. Da die Mitgliedschaft in einem Team auch die Mitgliedschaft in Office 365-Gruppen definiert, sollten Sie die Personen auf diese Änderung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-p103">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients. As mentioned previously, manage all future membership to the Office 365 Group using the Teams client. Since membership to a team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="8c4b8-114">Microsoft Teams respektiert Benennungsrichtlinien für Office 365-Gruppen (private Vorschau)</span><span class="sxs-lookup"><span data-stu-id="8c4b8-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="8c4b8-115">Benennungsrichtlinien für Office 365-Gruppen, die Ihr Administrator festgelegt hat, werden in Teams angewendet, wenn Benutzer Teamnamen erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="8c4b8-116">Dies gilt unter anderem für erforderliche Präfixe oder Suffixe und das Ausschließen von gesperrten Wörtern.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="8c4b8-117">Diese Funktion ist als private Vorschau verfügbar. Das heißt, wenn Sie nicht an dieser Vorschau teilnehmen, hält Microsoft Teams diese Benennungsrichtlinien für Office 365-Gruppen noch nicht ein.</span><span class="sxs-lookup"><span data-stu-id="8c4b8-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="8c4b8-118">Weitere Informationen finden Sie unter [Benennungsrichtlinie für Office 365-Gruppen](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span><span class="sxs-lookup"><span data-stu-id="8c4b8-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="8c4b8-119">Die folgenden Artikel sind ein guter Ort, um Eignungs-und Adoptions Inhalte für Ihre Office 365-Gruppen zu finden:</span><span class="sxs-lookup"><span data-stu-id="8c4b8-119">The following articles are a good place to find readiness and adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="8c4b8-120">Mehr Möglichkeiten mit Gruppen in Outlook</span><span class="sxs-lookup"><span data-stu-id="8c4b8-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="8c4b8-121">Hinzufügen oder Entfernen von Mitgliedern aus Office 365-Gruppen mithilfe des Microsoft 365 admin Centers</span><span class="sxs-lookup"><span data-stu-id="8c4b8-121">Add or remove members from Office 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="8c4b8-122">Wiederherstellen einer gelöschten Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="8c4b8-122">Restore a deleted Office 365 Group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
