---
title: Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Erfahren Sie mehr über das Verwalten von Richtlinien und deren Verwaltung in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793521"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="ca027-103">Aufbewahrungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca027-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="ca027-104">Teams-Unterhaltungen sind dauerhaft und werden standardmäßig für immer aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="ca027-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="ca027-105">Mit der Einführung von Aufbewahrungsrichtlinien können Administratoren im Security #a0 Compliance Center für Teams-Chats und Kanal Nachrichtenaufbewahrungsrichtlinien (sowohl Konservierung als auch Löschung) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ca027-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="ca027-106">Dies hilft Organisationen, Daten für einen bestimmten Zeitraum für die Compliance (nämlich die Erhaltungs Richtlinie) zu speichern oder Daten (nämlich Löschrichtlinien) loszuwerden, wenn Sie nach einem bestimmten Zeitraum als verbindlich erachtet werden.</span><span class="sxs-lookup"><span data-stu-id="ca027-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="ca027-107">Durch die Aufbewahrungsrichtlinien von Teams wird sichergestellt, dass Sie beim Löschen von Daten aus allen permanenten Datenspeicherorten des Teams-Diensts entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ca027-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="ca027-108">Wir unterstützen noch keine Konfiguration für die Aufbewahrung privater Kanal Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="ca027-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="ca027-109">Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ca027-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="ca027-110">Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams die Einstellungen und Cmdlets im Office 365 Security #a0 Compliance Center unter **Information Governance** > -**Aufbewahrung**.</span><span class="sxs-lookup"><span data-stu-id="ca027-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="ca027-111">Die Aufbewahrungsrichtlinien von Teams unterstützen:</span><span class="sxs-lookup"><span data-stu-id="ca027-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="ca027-112">Konservierung: Verwalten von Teams-Daten für eine bestimmte Dauer und dann nichts</span><span class="sxs-lookup"><span data-stu-id="ca027-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="ca027-113">Beibehalten und dann löschen: Verwalten von Teams-Daten für eine bestimmte Dauer und anschließendes Löschen</span><span class="sxs-lookup"><span data-stu-id="ca027-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="ca027-114">Löschen: Löschen von Teams-Daten nach einer bestimmten Dauer</span><span class="sxs-lookup"><span data-stu-id="ca027-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="ca027-115">Teams-Aufbewahrungsrichtlinien unterstützen noch nicht:</span><span class="sxs-lookup"><span data-stu-id="ca027-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="ca027-116">Erweiterte Aufbewahrungsrichtlinien gelten nicht für Team-Chats und Teams Kanal Nachrichtenspeicher Orte</span><span class="sxs-lookup"><span data-stu-id="ca027-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="ca027-117">Dauer von weniger als 30 Tagen</span><span class="sxs-lookup"><span data-stu-id="ca027-117">Duration of fewer than 30 days</span></span>

<span data-ttu-id="ca027-118">Administratoren können separate Aufbewahrungsrichtlinien für private Microsoft-Chats (1:1 oder 1: viele Chats) und für Teams Kanal Nachrichten einrichten.</span><span class="sxs-lookup"><span data-stu-id="ca027-118">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="ca027-119">In vielen Fällen sehen Organisationen private Chat-Daten eher als eine Haftung als Kanal Nachrichten an, die in der Regel mehr projektbezogene Unterhaltungen sind.</span><span class="sxs-lookup"><span data-stu-id="ca027-119">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="ca027-120">Richten Sie diese Richtlinien im Security #a0 Compliance Center,**Retention**von **Information Governance** > ein.</span><span class="sxs-lookup"><span data-stu-id="ca027-120">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="ca027-121">Aktivieren Sie die **Channel-Nachrichten** und **Teams-Chats** von Teams, und definieren Sie dann Aufbewahrungsrichtlinien für diese Speicherorte (siehe Abbildung unten).</span><span class="sxs-lookup"><span data-stu-id="ca027-121">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="ca027-122">Wenn Sie Channel- **Nachrichten für Teams**aktivieren, können Sie Teams angeben, für die diese Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="ca027-122">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="ca027-123">Beispielsweise kann der Administrator für Teams X, Y und Z die Löschrichtlinien für ein Jahr festlegen (durch Auswahl dieser Teams einzeln) und eine 3-jährige Löschrichtlinie für die restlichen Teams anwenden.</span><span class="sxs-lookup"><span data-stu-id="ca027-123">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="ca027-124">Sie können für **Teams-Chats** dasselbe tun, indem Sie bestimmte Benutzer auswählen und eindeutige Aufbewahrungsrichtlinien anwenden.</span><span class="sxs-lookup"><span data-stu-id="ca027-124">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="ca027-126">In den Teams-Channel-Nachrichtenspeicher Orten und Teams-Chats werden nur die in Exchange Online-Postfächern gespeicherten Team Unterhaltungen (Benutzer-und Gruppen Postfächer) behandelt.</span><span class="sxs-lookup"><span data-stu-id="ca027-126">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="ca027-127">Die Nachrichten werden aus allen relevanten Speicherorten, nämlich den Postfächern, dem Substrat und dem Chatdienst, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ca027-127">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="ca027-128">Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams-Dateien, die in OneDrive for Business und SharePoint gespeichert sind, deren Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ca027-128">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="ca027-129">Nach dem Entwurf werden Löschrichtlinien für Teams-Dateien über SharePoint Online und OneDrive for Business-Speicherorte konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ca027-129">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="ca027-130">Daher ist es möglich, dass eine Richtlinie eine Datei löscht, auf die in einer Team-Chat-oder Kanal Nachricht verwiesen wird, bevor diese Nachrichten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ca027-130">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="ca027-131">In diesem Fall wird die Datei weiterhin in der Nachricht "Teams" angezeigt, aber wenn Sie auf die Datei klicken, wird die Fehlermeldung "Datei nicht gefunden" angezeigt (Dies kann auch in Abwesenheit einer Richtlinie geschehen, wenn jemand eine Datei manuell aus SharePoint Online oder OneDrive for Business löscht).</span><span class="sxs-lookup"><span data-stu-id="ca027-131">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="ca027-132">Detaillierte Informationen zum Konfigurieren von Aufbewahrungsrichtlinien für Office 365 finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="ca027-132">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
