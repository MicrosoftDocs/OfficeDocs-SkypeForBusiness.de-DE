---
title: Freigabe von Dateien in Microsoft Teams
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138353"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="2316a-103">Freigabe von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2316a-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="2316a-104">In Microsoft Teams können Benutzer Inhalte für andere Team Benutzer innerhalb und außerhalb Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="2316a-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="2316a-105">Die Freigabe in Teams basiert auf den in SharePoint und OneDrive konfigurierten Einstellungen, sodass die für SharePoint und OneDrive eingerichteten Einstellungen auch die Freigabe in Teams steuern.</span><span class="sxs-lookup"><span data-stu-id="2316a-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="2316a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2316a-106">Overview</span></span>

<span data-ttu-id="2316a-107">Benutzer können Dateien aus OneDrive, aus Teams und Websites, auf die Sie Zugriff haben, und von Ihrem Computer aus freigeben.</span><span class="sxs-lookup"><span data-stu-id="2316a-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="2316a-108">Zum Freigeben einer Datei können Benutzer die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2316a-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="2316a-109">Klicken Sie in einem Kanal auf **Anfügen** (das Büroklammersymbol), wählen Sie **zuletzt**verwendet, **Teams und Kanäle durchsuchen**, **OneDrive**oder **vom Arbeitsplatz Hochladen aus**, und wählen Sie dann die Datei aus, die Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="2316a-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="2316a-110">![Screenshot, der zeigt, wie eine Datei über einen Kanal freigegeben wird](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="2316a-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="2316a-111">Klicken Sie in einem Chat auf **Anfügen** (das Büroklammersymbol), wählen oder **OneDrive** oder auf **vom Arbeitsplatz Hochladen aus**, und wählen Sie dann die Datei aus, die Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="2316a-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="2316a-112">![Screenshot, der zeigt, wie eine Datei über einen Chat freigegeben wird](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="2316a-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="2316a-113">Kopieren Sie den Link Freigabe, und fügen Sie ihn in das Feld zum Verfassen ein.</span><span class="sxs-lookup"><span data-stu-id="2316a-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="2316a-114">![Screenshot mit Dateivorschau im Feld zum Verfassen](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="2316a-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="2316a-115">Was Sie über die gemeinsame Nutzung von Dateien wissen müssen</span><span class="sxs-lookup"><span data-stu-id="2316a-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="2316a-116">Berechtigungen für freigegebene Dateien und Freigabelinks</span><span class="sxs-lookup"><span data-stu-id="2316a-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="2316a-117">Wenn Benutzer eine Datei freigeben, indem Sie Sie in OneDrive oder in Teams und Kanälen durchsuchen, werden allen Empfängern Zugriff zusammen mit der [Standardberechtigung gewährt, die auf Organisationsebene festgesetzt ist](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="2316a-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="2316a-118">Wenn ein Benutzer einen Freigabe Link kopiert und einfügt, werden die für diesen Freigabe Link festgelegten Berechtigungen berücksichtigt, und die SharePoint-URL wird auf den Dateinamen verkürzt.</span><span class="sxs-lookup"><span data-stu-id="2316a-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="2316a-119">Mit anderen Worten: Teams verwendet nur den Dateinamen, um eine Verknüpfung mit einer Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2316a-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="2316a-120">Wenn Benutzer eine Datei in Microsoft Teams freigeben, können Sie die Personen, die auf die Datei zugreifen können, genau wie in Microsoft 365 einstellen.</span><span class="sxs-lookup"><span data-stu-id="2316a-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="2316a-121">Sie können jedem Personen, Personen in Ihrer Organisation, Personen mit vorhandenem Zugriff oder bestimmten Personen (die Personen in einem 1:1-Chat, Gruppen-Chat oder Kanal einbeziehen können) Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="2316a-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="2316a-122">Wenn eine Datei freigegeben ist, ist die Dateivorschau in der Nachricht zusammen mit allen Dateiaktionen wie " **Online öffnen**", " **herunterladen**" und " **Link kopieren**" verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2316a-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="2316a-123">Standardmäßig wird die Datei in Teams geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2316a-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="2316a-124">Manchmal wurde der Freigabe Link möglicherweise nicht in eine Dateivorschau konvertiert, wenn ein Benutzer die Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="2316a-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="2316a-125">Die Dateivorschau wird vom System generiert, in diesem Szenario wird der Freigabe Link jedoch nicht auf den Dateinamen verkürzt.</span><span class="sxs-lookup"><span data-stu-id="2316a-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="2316a-126">Wenn Benutzer eine Datei in einem Chat oder Kanal freigeben, werden Sie benachrichtigt, ob einige oder alle Empfänger nicht über die Berechtigung zum Anzeigen der Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="2316a-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="2316a-127">Sie können die Berechtigungen für die Datei ändern, bevor Sie Sie freigeben, indem Sie auf den Pfeil neben der Dateivorschau klicken, die nun in der Nachricht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2316a-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Screenshot der Benachrichtigung, wenn Empfänger keine Berechtigungen besitzen](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="2316a-129">Kopieren eines Freigabelinks in Teams</span><span class="sxs-lookup"><span data-stu-id="2316a-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="2316a-130">Benutzer können einen SharePoint-Freigabe Link kopieren und Freigabeberechtigungen genauso wie in Microsoft 365 ändern.</span><span class="sxs-lookup"><span data-stu-id="2316a-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="2316a-131">Sie können jedem Personen, Personen in Ihrer Organisation, Personen mit vorhandenem Zugriff oder bestimmten Personen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="2316a-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="2316a-132">Die Standardberechtigung für den Link entspricht dem Standardberechtigungssatz auf Organisationsebene, es sei denn, die Berechtigungen für die SharePoint-Websiteebene überschreiben ihn.</span><span class="sxs-lookup"><span data-stu-id="2316a-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="2316a-133">Konfigurieren der Freigabe in OneDrive und SharePoint</span><span class="sxs-lookup"><span data-stu-id="2316a-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="2316a-134">Weitere Informationen zum Freigeben von Dateien in OneDrive und SharePoint, einschließlich der Konfiguration der Freigabe und der Aktivierung und Deaktivierung von Freigaben, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="2316a-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="2316a-135">[Übersicht über externe Freigabe](https://docs.microsoft.com/sharepoint/external-sharing-overview) – beschreibt, was geschieht, wenn Benutzer die Freigabe durchgeführt haben, je nachdem, was Sie teilen und mit wem.</span><span class="sxs-lookup"><span data-stu-id="2316a-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="2316a-136">[Verwalten von Freigabeeinstellungen](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – beschreibt, wie globale und SharePoint-Administratoren ihre Freigabeeinstellungen auf Organisationsebene für SharePoint und OneDrive ändern können.</span><span class="sxs-lookup"><span data-stu-id="2316a-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="2316a-137">[Aktivieren oder Deaktivieren der externen Freigabe für eine Website](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – beschreibt, wie globale und SharePoint-Administratoren die externe Freigabe für eine Website aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="2316a-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="2316a-138">[Ändern des Standard Verknüpfungstyps für eine Website](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – beschreibt, wie Sie den Standardverknüpfungstyp so festlegen, dass er restriktiver ist.</span><span class="sxs-lookup"><span data-stu-id="2316a-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="2316a-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2316a-139">More information</span></span>

- [<span data-ttu-id="2316a-140">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2316a-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="2316a-141">SharePoint und Teams: besser zusammen</span><span class="sxs-lookup"><span data-stu-id="2316a-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="2316a-142">Freigeben von OneDrive-Dateien und-Ordnern</span><span class="sxs-lookup"><span data-stu-id="2316a-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="2316a-143">Freigeben von SharePoint-Dateien oder-Ordnern</span><span class="sxs-lookup"><span data-stu-id="2316a-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
