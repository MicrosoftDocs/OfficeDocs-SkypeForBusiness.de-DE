---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden, sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232278"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="d524d-103">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d524d-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="d524d-104">Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="d524d-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="d524d-p101">Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.</span><span class="sxs-lookup"><span data-stu-id="d524d-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="d524d-107">Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d524d-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="d524d-108">Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d524d-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="d524d-109">Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.</span><span class="sxs-lookup"><span data-stu-id="d524d-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="d524d-110">Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.</span><span class="sxs-lookup"><span data-stu-id="d524d-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="d524d-111">Die Integration in SharePoint lokal wird für Microsoft Teams zurzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d524d-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="d524d-112">Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="d524d-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="d524d-p103">Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d524d-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramm der Ordner "freigegebene Dokumente" in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="d524d-116">Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d524d-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="d524d-117">Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="d524d-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="d524d-118">In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d524d-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="d524d-119">So fügen Sie Ihrem Team eine Registerkarte hinzu, die mit einer vorhandenen SharePoint-Website Seite oder mit Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft ist:</span><span class="sxs-lookup"><span data-stu-id="d524d-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="d524d-120">Wählen Sie das Pluszeichen neben den Registerkarten aus.</span><span class="sxs-lookup"><span data-stu-id="d524d-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="d524d-121">Wählen Sie entweder **SharePoint** für eine vorhandene SharePoint-Website Seite oder eine **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="d524d-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="d524d-122">Wählen Sie die entsprechende Seite oder Dokumentbibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="d524d-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="d524d-123">Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="d524d-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramm des OneDrive-Ordners mit dem Namen Microsoft Teams-Chat Dateien](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="d524d-125">Registerkarte "Kanaldateien"</span><span class="sxs-lookup"><span data-stu-id="d524d-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="d524d-126">Die Registerkarte **Dateien** in Microsoft Teams ähnelt der Ansicht SharePoint-Dokumente.</span><span class="sxs-lookup"><span data-stu-id="d524d-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="d524d-127">Auf der Registerkarte " **Dateien** " können Benutzer:</span><span class="sxs-lookup"><span data-stu-id="d524d-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="d524d-128">Weitere Optionen finden Sie im Menü " **neue** Datei".</span><span class="sxs-lookup"><span data-stu-id="d524d-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="d524d-129">Synchronisieren Sie Dateien auf dem lokalen Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="d524d-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="d524d-130">Wechseln Sie im Menü **alle Dokumente** von der **Listen** Ansicht zur **kompaktliste** in die **Kachel** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="d524d-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="d524d-131">Ermitteln Sie Dateien, die auf die Berücksichtung oder Malware abstellen.</span><span class="sxs-lookup"><span data-stu-id="d524d-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="d524d-132">Sehen Sie sofort, ob eine Datei schreibgeschützt oder ausgecheckt ist.</span><span class="sxs-lookup"><span data-stu-id="d524d-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="d524d-133">Auschecken und Einchecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="d524d-133">Check out and check in files.</span></span>
- <span data-ttu-id="d524d-134">Anheften, unpin und Ändern der Sortierreihenfolge von Dateien</span><span class="sxs-lookup"><span data-stu-id="d524d-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="d524d-135">Ermitteln, welche Dateien Metadaten benötigen</span><span class="sxs-lookup"><span data-stu-id="d524d-135">Identify which files need metadata</span></span>
- <span data-ttu-id="d524d-136">Wählen Sie aus vielen weiteren Filteroptionen aus.</span><span class="sxs-lookup"><span data-stu-id="d524d-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="d524d-137">Gruppieren Sie Dateien basierend auf Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="d524d-137">Group files based on column headings.</span></span>
- <span data-ttu-id="d524d-138">Ändern Sie die Spalteneinstellungen (nach links oder rechts, ausblenden) und Spaltenbreite.</span><span class="sxs-lookup"><span data-stu-id="d524d-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="d524d-139">Standardeinstellung für den Verknüpfungstyp</span><span class="sxs-lookup"><span data-stu-id="d524d-139">Default link type setting</span></span>

<span data-ttu-id="d524d-140">SharePoint und OneDrive verfügen über eine Administratoreinstellung zum Angeben des Standardverknüpfungstyp für Links, die für eine Datei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d524d-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="d524d-141">Teams nimmt denselben Ansatz an, indem die Einstellungen wieder verwendet werden, die der Administrator für SharePoint und OneDrive festlegt.</span><span class="sxs-lookup"><span data-stu-id="d524d-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="d524d-142">Weitere Informationen zu diesem Ansatz finden Sie unter [Ändern des Standard Link Typs, wenn Benutzer Links für die Freigabe erhalten](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="d524d-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="d524d-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d524d-143">More information</span></span>

<span data-ttu-id="d524d-144">Weitere Informationen zur Funktionsweise von SharePoint mit Teams finden Sie unter [SharePoint und Teams: besser zusammen](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="d524d-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="d524d-145">Wenn Sie mehr über die Gastfreundlichkeit in Teams erfahren möchten, lesen Sie, [wie die Gast Erfahrung aussieht](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="d524d-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

