---
title: Freigeben von Dateien in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Dateifreigabe in Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138353"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="defa1-103">Freigeben von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="defa1-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="defa1-104">In Microsoft Teams können Benutzer Inhalte für andere Teams-Benutzer innerhalb und außerhalb ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="defa1-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="defa1-105">Die Freigabe in Teams basiert auf den Einstellungen, die in SharePoint und OneDrive konfiguriert sind. Die Einstellungen, die Sie für SharePoint und OneDrive festlegen, steuern also auch die Freigabe in Teams.</span><span class="sxs-lookup"><span data-stu-id="defa1-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="defa1-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="defa1-106">Overview</span></span>

<span data-ttu-id="defa1-107">Benutzer können Dateien von OneDrive, von Teams und Websites, auf die sie Zugriff haben, und von ihrem Computer aus freigeben.</span><span class="sxs-lookup"><span data-stu-id="defa1-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="defa1-108">Um eine Datei freizugeben, können Benutzer die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="defa1-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="defa1-109">Klicken Sie in einem Kanal auf **Anfügen** (das Büroklammer-Symbol), wählen Sie **Zuletzt verwendet**, **Teams und Kanäle durchsuchen**, **OneDrive** oder **Von meinem Computer hochladen** und dann die Datei aus, die sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="defa1-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="defa1-110">![Screenshot der Freigabe einer Datei aus einem Kanal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="defa1-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="defa1-111">Klicken Sie in einem Chat auf **Anfügen** (das Büroklammer-Symbol), wählen Sie **OneDrive** oder **Von meinem Computer hochladen** und dann die Datei aus, die sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="defa1-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="defa1-112">![Screenshot der Freigabe einer Datei aus einem Chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="defa1-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="defa1-113">Kopieren Sie den Freigabelink, und fügen Sie ihn in das Feld „Verfassen“ ein.</span><span class="sxs-lookup"><span data-stu-id="defa1-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="defa1-114">![Screenshot mit der Dateivorschau im Feld „Verfassen“](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="defa1-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="defa1-115">Was Sie über die Dateifreigabe wissen müssen</span><span class="sxs-lookup"><span data-stu-id="defa1-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="defa1-116">Berechtigungen für freigegebene Dateien und Freigabelinks</span><span class="sxs-lookup"><span data-stu-id="defa1-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="defa1-117">Wenn Benutzer eine Datei freigeben, indem sie sie in OneDrive oder in Teams und Kanälen aufrufen, wird allen Empfängern der Zugriff mit der [auf Organisationsebene festgelegten Standardberechtigung](https://docs.microsoft.com/sharepoint/change-default-sharing-link) gewährt.</span><span class="sxs-lookup"><span data-stu-id="defa1-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="defa1-118">Wenn ein Benutzer einen Freigabelink kopiert und einfügt, werden die für diesen Freigabelink festgelegten Berechtigungen beachtet, und die SharePoint-URL wird auf den Dateinamen verkürzt.</span><span class="sxs-lookup"><span data-stu-id="defa1-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="defa1-119">Mit anderen Worten: Teams verwendet nur den Dateinamen, um die Verknüpfung zu einer Datei herzustellen.</span><span class="sxs-lookup"><span data-stu-id="defa1-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="defa1-120">Wenn Benutzer eine Datei aus Teams heraus freigeben, können sie genau wie in Microsoft 365 festlegen, wer auf die Datei zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="defa1-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="defa1-121">Sie können jedem, Personen in Ihrer Organisation, Personen mit bestehendem Zugriff oder bestimmten Personen (zu denen auch die Personen in einem 1:1-Chat, Gruppenchat oder Kanal gehören können) Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="defa1-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="defa1-122">Wenn eine Datei freigegeben wird, ist die Dateivorschau in der Nachricht verfügbar, zusammen mit allen Dateiaktionen wie **Online öffnen**, **Herunterladen** und **Link kopieren**.</span><span class="sxs-lookup"><span data-stu-id="defa1-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="defa1-123">Standardmäßig wird die Datei in Teams geöffnet.</span><span class="sxs-lookup"><span data-stu-id="defa1-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="defa1-124">Manchmal kann es vorkommen, dass der Freigabelink noch nicht in eine Dateivorschau umgewandelt wurde, wenn ein Benutzer die Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="defa1-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="defa1-125">Die Dateivorschau wird vom System generiert, aber in diesem Szenario wird der Freigabelink nicht auf den reinen Dateinamen gekürzt.</span><span class="sxs-lookup"><span data-stu-id="defa1-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="defa1-126">Wenn Benutzer eine Datei in einem Chat oder Kanal freigeben, werden sie benachrichtigt, wenn einzelne oder alle Empfänger keine Berechtigung zum Anzeigen der Datei haben.</span><span class="sxs-lookup"><span data-stu-id="defa1-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="defa1-127">Sie können die Berechtigungen für die Datei vor der Freigabe ändern, indem sie auf den Pfeil neben der Dateivorschau klicken, der nun in der Nachricht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="defa1-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Screenshot der Benachrichtigung, wenn Empfänger keine Berechtigungen haben](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="defa1-129">Kopieren eines Freigabelinks in Teams</span><span class="sxs-lookup"><span data-stu-id="defa1-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="defa1-130">Benutzer können einen SharePoint-Freigabelink kopieren und Freigabeberechtigungen ändern, genau wie in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="defa1-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="defa1-131">Sie können jedem, Personen in Ihrer Organisation, Personen mit bestehendem Zugriff oder bestimmten Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="defa1-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="defa1-132">Die Standardberechtigung des Links entspricht der auf Organisationsebene festgelegten Standardberechtigung, es sei denn, die Berechtigungen auf SharePoint-Webseitenebene setzen diese außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="defa1-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="defa1-133">Konfigurieren der Freigabe in OneDrive und SharePoint</span><span class="sxs-lookup"><span data-stu-id="defa1-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="defa1-134">Weitere Informationen zur Freigabe von Dateien in OneDrive und SharePoint, einschließlich Konfiguration der Freigabe und Aktivierung/Deaktivierung der Freigabe, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="defa1-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="defa1-135">[Externe Freigabe – Übersicht](https://docs.microsoft.com/sharepoint/external-sharing-overview) – Beschreibt, was bei Benutzerfreigaben geschieht, und zwar abhängig davon, was freigegeben wird und für wen die Freigabe erfolgt.</span><span class="sxs-lookup"><span data-stu-id="defa1-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="defa1-136">[Verwalten von Freigabeeinstellungen](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – Beschreibt, wie globale und SharePoint-Administratoren ihre Freigabeeinstellungen für SharePoint und OneDrive auf Unternehmensebene ändern können.</span><span class="sxs-lookup"><span data-stu-id="defa1-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="defa1-137">[Aktivieren oder Deaktivieren der externen Freigabe für eine Website](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – Beschreibt, wie globale und SharePoint-Administratoren die externe Freigabe für eine Website aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="defa1-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="defa1-138">[Ändern des Standard-Linktyps für eine Website](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – Beschreibt, wie Sie den Standardlinktyp festlegen, um ihn restriktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="defa1-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="defa1-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="defa1-139">More information</span></span>

- [<span data-ttu-id="defa1-140">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="defa1-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="defa1-141">SharePoint und Teams: ein starkes Team</span><span class="sxs-lookup"><span data-stu-id="defa1-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="defa1-142">Freigeben von OneDrive-Dateien und -Ordnern</span><span class="sxs-lookup"><span data-stu-id="defa1-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="defa1-143">Freigeben von SharePoint-Dateien oder -Ordnern</span><span class="sxs-lookup"><span data-stu-id="defa1-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
