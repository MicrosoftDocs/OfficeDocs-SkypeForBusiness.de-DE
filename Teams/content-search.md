---
title: Verwenden der Inhaltssuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informationen zur Inhaltssuche in Microsoft Teams und zum Suchen nach Kanal Unterhaltungen aus Exchange, Dateiuploads und Änderungen aus SharePoint und OneNote-Änderungen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222b57021a259795823031d9855304d1ecf27f4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825343"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="18e7d-103">Verwenden der Inhaltssuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18e7d-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="18e7d-104">Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="18e7d-105">Weitere Informationen finden Sie unter [Inhaltssuche privater Kanäle](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="18e7d-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="18e7d-106">Die Inhaltssuche bietet eine Möglichkeit zum Abfragen von Microsoft Teams-Informationen, die Exchange, SharePoint Online und OneDrive for Business umfassen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="18e7d-107">Weitere Informationen finden Sie unter [Inhaltssuche in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span><span class="sxs-lookup"><span data-stu-id="18e7d-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="18e7d-108">So können Sie beispielsweise mithilfe der **Inhaltssuche** auf der SharePoint-Website für die Produktionsspezifikationen für das Postfach und die Fertigungsspezifikationen nach Teams Standardkanal Unterhaltungen von Exchange, Dateiuploads und Änderungen aus SharePoint Online und OneNote-Änderungen suchen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="18e7d-p102">Sie können der **Inhaltssuche** auch Abfragekriterien hinzufügen, um die zurückgegebenen Ergebnisse einzuschränken. Im obigen Beispiel können Sie nach Inhalten suchen, bei denen die Schlüsselwörter "**New Factory Specs"** verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="18e7d-p102">You can also add query criteria to the **Content Search** to narrow the results returned. In the above example, you can look for content where the keywords “**New Factory Specs”** were used.</span></span>

> [!TIP]
> <span data-ttu-id="18e7d-111">Nach dem Hinzufügen von Suchbedingungen können Sie einen Bericht oder die Daten zur Analyse auf Ihren Computer exportieren.</span><span class="sxs-lookup"><span data-stu-id="18e7d-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="18e7d-112">Inhaltssuche privater Kanäle</span><span class="sxs-lookup"><span data-stu-id="18e7d-112">Content search of private channels</span></span>

<span data-ttu-id="18e7d-113">Datensätze für Nachrichten, die in einem privaten Kanal gesendet wurden, werden an das Postfach aller privaten Kanalmitglieder und nicht an ein Gruppenpostfach übermittelt.</span><span class="sxs-lookup"><span data-stu-id="18e7d-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="18e7d-114">Die Titel der Datensätze werden so formatiert, dass Sie angeben, von welchem privaten Kanal Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="18e7d-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="18e7d-115">Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.</span><span class="sxs-lookup"><span data-stu-id="18e7d-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="18e7d-116">Teams unterstützen nicht die Inhaltssuche eines einzelnen Kanals, damit das gesamte Team durchsucht werden muss.</span><span class="sxs-lookup"><span data-stu-id="18e7d-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="18e7d-117">Wenn Sie eine Inhaltssuche in einem privaten Kanal durchführen möchten, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien einzubeziehen), und Postfächern privater Kanalmitglieder (zum Einbeziehen von Nachrichten).</span><span class="sxs-lookup"><span data-stu-id="18e7d-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="18e7d-118">Führen Sie die folgenden Schritte aus, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in die Inhaltssuche einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="18e7d-119">Einbeziehen privater Kanaldateien in eine Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="18e7d-119">Include private channel files in a content search</span></span>

<span data-ttu-id="18e7d-120">Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="18e7d-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="18e7d-121">Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die privaten Kanälen im Team zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="18e7d-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="18e7d-122">Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs einer SharePoint-Websitesammlung abzurufen, die privaten Kanälen im Team zugeordnet sind, und die Gruppen-ID der übergeordneten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="18e7d-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="18e7d-123">Führen Sie für jede Team-oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanal Websites zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="18e7d-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="18e7d-124">Einbeziehen privater Kanal Nachrichten in eine Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="18e7d-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="18e7d-125">Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="18e7d-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="18e7d-126">Führen Sie die folgenden Schritte aus, um eine Liste privater Kanäle im Team abzurufen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="18e7d-127">Führen Sie die folgenden Schritte aus, um eine Liste privater Kanalmitglieder abzurufen.</span><span class="sxs-lookup"><span data-stu-id="18e7d-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="18e7d-128">Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil der Inhalts Suchabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="18e7d-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18e7d-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="18e7d-129">Related topics</span></span>

- [<span data-ttu-id="18e7d-130">eDiscovery-Fälle im Office 365 Security #a0 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="18e7d-130">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 