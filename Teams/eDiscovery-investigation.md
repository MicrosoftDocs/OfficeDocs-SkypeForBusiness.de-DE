---
title: Durchführen einer eDiscovery-Untersuchung von Inhalten
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie vorgehen müssen, wenn Sie eine eDiscovery durchführen müssen, beispielsweise wenn Sie alle elektronisch gespeicherten Informationen für gerichtliche Verfahren übermitteln müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136685"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="5c212-103">Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5c212-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="5c212-104">Große Unternehmen sind häufig hohen strafrechtlichen Verfahren ausgesetzt, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) fordern.</span><span class="sxs-lookup"><span data-stu-id="5c212-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="5c212-105">Alle Teams 1:1-oder Gruppen-Chats werden über die Postfächer der jeweiligen Benutzer in Journalen durchlaufen, und alle standardmäßigen Kanal Nachrichten werden in das Gruppenpostfach, das das Team darstellt, in Journalen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5c212-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="5c212-106">Dateien, die in Standardkanälen hochgeladen werden, werden von der eDiscovery-Funktion für SharePoint Online und OneDrive for Business abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="5c212-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="5c212-107">eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen.</span><span class="sxs-lookup"><span data-stu-id="5c212-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="5c212-108">Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="5c212-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="5c212-109">Derzeit unterstützen wir keine eDiscovery-Chatnachrichten in Szenarien, in denen Gastbenutzer die einzigen Teilnehmer an einem 1:1-oder 1: N-Chat sind.</span><span class="sxs-lookup"><span data-stu-id="5c212-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="5c212-110">Diese Arten von Chats werden auch als *Gast-zu-Gast* -Chats bezeichnet, da Sie keine Home-Tenant-Nutzer sind.</span><span class="sxs-lookup"><span data-stu-id="5c212-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="5c212-111">Wenn Sie eine eDiscovery-Untersuchung mit Microsoft Teams-Inhalten durchführen möchten, lesen Sie Schritt 1 in [diesem](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) Link.</span><span class="sxs-lookup"><span data-stu-id="5c212-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="5c212-112">Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel-eDiscovery-Exportausgabe angezeigt, und Sie können die PST-Datei in Outlook öffnen, um diese Nachrichten nach dem Export anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c212-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="5c212-113">Beachten Sie beim Anzeigen der PST-Datei für das Team, dass alle Unterhaltungen im Team-Chat-Ordner unter "Konversations Verlauf" aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="5c212-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="5c212-114">Der Titel der Nachricht wird an Team und Kanal ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="5c212-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="5c212-115">Wenn Sie das Bild unten überprüfen, können Sie diese Nachricht von Bob sehen, der den Project 7-Standardkanal des Teams "Manufacturing Specs" gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="5c212-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Screenshot eines Team-Chat-Ordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="5c212-117">Um private Chats im Postfach eines Benutzers anzuzeigen, befinden Sie sich auch im Ordner "Team-Chat" unter "Konversationsprotokoll".</span><span class="sxs-lookup"><span data-stu-id="5c212-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="5c212-118">eDiscovery privater Kanäle</span><span class="sxs-lookup"><span data-stu-id="5c212-118">eDiscovery of private channels</span></span>

<span data-ttu-id="5c212-119">Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5c212-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="5c212-120">Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5c212-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="5c212-121">Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5c212-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="5c212-122">Teams unterstützt keine eDiscovery eines einzelnen Kanals, sodass das gesamte Team durchsucht werden muss.</span><span class="sxs-lookup"><span data-stu-id="5c212-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="5c212-123">Wenn Sie eine eDiscovery-Suche nach Inhalten in einem privaten Kanal durchführen möchten, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien einzubeziehen), und Postfächern privater Kanalmitglieder (zum Einbeziehen von Nachrichten).</span><span class="sxs-lookup"><span data-stu-id="5c212-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="5c212-124">Führen Sie die folgenden Schritte aus, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die Sie in Ihre eDiscovery-Suche einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c212-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="5c212-125">Einbeziehen privater Kanaldateien in eine eDiscovery-Suche</span><span class="sxs-lookup"><span data-stu-id="5c212-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="5c212-126">Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="5c212-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="5c212-127">Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die privaten Kanälen im Team zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5c212-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="5c212-128">Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs einer SharePoint-Websitesammlung abzurufen, die privaten Kanälen im Team zugeordnet sind, und die Gruppen-ID der übergeordneten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="5c212-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="5c212-129">Führen Sie für jede Team-oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanal Websites zu identifizieren, wobei $GroupID die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="5c212-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="5c212-130">Einbeziehen privater Kanal Nachrichten in eine eDiscovery-Suche</span><span class="sxs-lookup"><span data-stu-id="5c212-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="5c212-131">Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5c212-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="5c212-132">Führen Sie die folgenden Schritte aus, um eine Liste privater Kanäle im Team abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c212-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="5c212-133">Führen Sie die folgenden Schritte aus, um eine Liste privater Kanalmitglieder abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c212-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="5c212-134">Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil ihrer eDiscovery-Suchabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="5c212-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c212-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5c212-135">Related topics</span></span>

- [<span data-ttu-id="5c212-136">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5c212-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
