---
title: Aufbewahrungsrichtlinien in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Erhalten Sie Informationen zu Aufbewahrungsrichtlinien und wie sie in Teams verwaltet.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 453e6f161b62846143493d7a444b364e27f3885e
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004594"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="6ce60-103">Aufbewahrungsrichtlinien in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="6ce60-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="6ce60-104">Teams Unterhaltungen sind beständigen und ewig standardmäßig beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6ce60-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="6ce60-105">Mit der Einführung von Aufbewahrungsrichtlinien können Administratoren Aufbewahrungsrichtlinien (Aufbewahrung und Löschung) im Compliance Center & Sicherheit für Teams Chat und Channel-Nachrichten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ce60-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="6ce60-106">Dadurch Organisationen, die Daten für die Kompatibilität (d. h., Beibehaltung der Richtlinie) für einen bestimmten Zeitraum beibehalten oder Beseitigen der Daten (d. h., Richtlinie löschen), wenn es eine Haftung nach einem bestimmten Zeitraum berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="6ce60-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="6ce60-107">Aufbewahrungsrichtlinien Teams stellen Sie sicher, dass sie beim Löschen von Daten aus alle Speicherorte permanente Daten in der Teams Dienst entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6ce60-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="6ce60-108">Verwenden Sie zum Verwalten von Teams Aufbewahrungsrichtlinien die Einstellungen und im Compliance Center unter **Daten Governance**& Sicherheit in Office 365-Cmdlets > **Aufbewahrung**.</span><span class="sxs-lookup"><span data-stu-id="6ce60-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="6ce60-109">Aufbewahrungsrichtlinien Teams unterstützen:</span><span class="sxs-lookup"><span data-stu-id="6ce60-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="6ce60-110">Permanentes: Teams Daten für eine angegebene Dauer beibehalten und nichts Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="6ce60-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="6ce60-111">Beibehaltung und dann löschen: Teams Daten für eine angegebene Dauer beibehalten, und klicken Sie dann löschen</span><span class="sxs-lookup"><span data-stu-id="6ce60-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="6ce60-112">Löschen: Löschen von Teams Daten nach einer bestimmten Zeit</span><span class="sxs-lookup"><span data-stu-id="6ce60-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="6ce60-113">Aufbewahrungsrichtlinien Teams noch unterstützt nicht:</span><span class="sxs-lookup"><span data-stu-id="6ce60-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="6ce60-114">Erweiterte Aufbewahrungsrichtlinien gelten nicht für Teams Chat und Teams Channel Nachricht Speicherorte</span><span class="sxs-lookup"><span data-stu-id="6ce60-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="6ce60-115">Dauer von weniger als 30 Tagen</span><span class="sxs-lookup"><span data-stu-id="6ce60-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="6ce60-116">Administratoren können separate Aufbewahrungsrichtlinien für Teams private Chats (1:1 oder 1: n-Chats) und Teams Channel Nachrichten einrichten.</span><span class="sxs-lookup"><span data-stu-id="6ce60-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="6ce60-117">In vielen Fällen sollten Organisationen private chatdaten als mehrere eine Haftung als Channel-Nachrichten, die in der Regel Weitere projektbezogenen Unterhaltungen sind.</span><span class="sxs-lookup"><span data-stu-id="6ce60-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="6ce60-118">Richten Sie diese Richtlinien in die Sicherheit & Compliance Center, **Daten Governance** > **Aufbewahrung**.</span><span class="sxs-lookup"><span data-stu-id="6ce60-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="6ce60-119">Schalten Sie **Teams channel Nachrichten** und **Teams chats** und definieren Sie dann die Aufbewahrungsrichtlinien für diesen Speicherorten (ebenfalls in der folgenden Abbildung dargestellt).</span><span class="sxs-lookup"><span data-stu-id="6ce60-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="6ce60-120">Wenn Sie **Teams channel Nachrichten**aktivieren, können Sie Teams angeben, auf die diese Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6ce60-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="6ce60-121">Beispielsweise für Teams X, Y und Z, der Administrator kann die Löschrichtlinien 1 Jahr (durch diese Teams einzeln auswählen) festgelegt, und Anwenden einer Richtlinie 3 Jahre Löschung auf den Rest der Teams.</span><span class="sxs-lookup"><span data-stu-id="6ce60-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="6ce60-122">Das gleiche möglich für **Teams chats** , indem Sie bestimmte Benutzer auswählen und Anwenden von Aufbewahrungsrichtlinien eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6ce60-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="6ce60-124">Die Teams Channel Nachricht Speicherorte und Teams Chats Speicherorte Adresse nur Teams Unterhaltungen in Exchange Online-Postfächer (Benutzer- und Postfächern) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6ce60-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="6ce60-125">Die Nachrichten werden aus allen relevanten Speicherorte, nämlich die Postfächer, Gate und Chatdienst gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6ce60-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="6ce60-126">Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams Dateien, die in OneDrive für Unternehmen und SharePoint gespeichert sind, ihre Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6ce60-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="6ce60-127">Konzipiert werden Löschrichtlinien für Teams Dateien über SharePoint Online und OneDrive for Business-Standorte konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6ce60-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="6ce60-128">Daher ist es möglich, dass eine Richtlinie löschen konnte eine Datei in einer Nachricht Teams, Chat oder DDE-Kanal verwiesen wird, bevor diese Nachrichten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6ce60-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="6ce60-129">In diesem Fall die Datei wird weiterhin in der Nachricht Teams angezeigt, aber wenn Sie die Datei klicken, erhalten Sie einen "Datei nicht gefunden"-Fehler (Dies kann auch ohne eine Richtlinie vorkommen, wenn ein Benutzer eine Datei manuell aus SharePoint Online oder OneDrive für Unternehmen löscht).</span><span class="sxs-lookup"><span data-stu-id="6ce60-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="6ce60-130">Ausführliche Informationen zur Konfiguration von Aufbewahrungsrichtlinien für Office 365 und das Lesen der [Übersicht über die Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="6ce60-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
