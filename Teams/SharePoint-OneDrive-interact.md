---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden, sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827740"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="b3b6b-103">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3b6b-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="b3b6b-104">Sehen Sie sich die folgenden Sitzung um zu erfahren, wie Teams interagiert mit Azure Active Directory (AAD), Gruppen von Office 365, Exchange, SharePoint und OneDrive für Unternehmen: [Grundlagen der Microsoft-Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="b3b6b-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="b3b6b-p101">Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="b3b6b-107">Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="b3b6b-108">Wenn Benutzer sind nicht zugewiesen und mit SharePoint Online-Lizenzen aktiviert, verfügen nicht OneDrive for Business-Speicher in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="b3b6b-109">Dateifreigabe wird in weiterhin, Kanäle, aber Benutzer werden nicht in der Lage, Freigeben von Dateien in Chats ohne OneDrive for Business-Speicher in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="b3b6b-110">Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3b6b-111">Integration in lokale SharePoint-wird für Microsoft-Teams, zu diesem Zeitpunkt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="b3b6b-112">Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="b3b6b-p103">Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramm des Ordners „Freigegebene Dokumente“ in SharePoint Online für ein Team und dessen Kanäle in Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="b3b6b-116">Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="b3b6b-117">Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="b3b6b-118">In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="b3b6b-119">Hinzufügen eine Registerkarte an Ihr Team, die zu einer vorhandenen SharePoint-Website-Seite oder in Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft:</span><span class="sxs-lookup"><span data-stu-id="b3b6b-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="b3b6b-120">Wählen Sie das Pluszeichen (+) neben den Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="b3b6b-121">Wählen Sie **SharePoint** für eine vorhandene Seite der SharePoint-Website oder **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="b3b6b-122">Wählen Sie aus der entsprechenden Seite oder -Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="b3b6b-123">Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramm des OneDrive-Ordners „Microsoft Teams-Chatdateien“ für die Chats der einzelnen Benutzer](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="b3b6b-125">Registerkarte Channel-Dateien</span><span class="sxs-lookup"><span data-stu-id="b3b6b-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="b3b6b-126">Die Registerkarte **Dateien** in Teams ähnelt die SharePoint-Dokumente-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="b3b6b-127">Klicken Sie auf der Registerkarte **Dateien** können Benutzer:</span><span class="sxs-lookup"><span data-stu-id="b3b6b-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="b3b6b-128">Finden Sie unter Weitere Optionen im Dateimenü **neu** .</span><span class="sxs-lookup"><span data-stu-id="b3b6b-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="b3b6b-129">Synchronisieren von Dateien auf ihrem lokalen Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="b3b6b-130">Klicken Sie im Menü **Alle Dokumente** aus **Listenansicht** **Compact** Liste zur **Kacheln** Ansicht wechseln.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="b3b6b-131">Identifizieren Sie die Dateien, die Aufmerksamkeit erfordern oder Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="b3b6b-132">Sofort zu überprüfen, ob eine Datei schreibgeschützt oder checked out.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="b3b6b-133">Auschecken und Einchecken von Dateien.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-133">Check out and check in files.</span></span>
- <span data-ttu-id="b3b6b-134">Heften Sie an, lösen Sie, und ändern Sie die Sortierreihenfolge der Dateien.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="b3b6b-135">Bestimmen Sie, welche Dateien Metadaten benötigt</span><span class="sxs-lookup"><span data-stu-id="b3b6b-135">Identify which files need metadata</span></span>
- <span data-ttu-id="b3b6b-136">Wählen Sie viele weitere Filteroptionen.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="b3b6b-137">Gruppe Dateien auf Basis von Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-137">Group files based on column headings.</span></span>
- <span data-ttu-id="b3b6b-138">Spalteneinstellungen (nach links oder rechts, ausblenden) und Spaltenbreite zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="b3b6b-139">Standard-Verknüpfungstyp festlegen</span><span class="sxs-lookup"><span data-stu-id="b3b6b-139">Default link type setting</span></span>

<span data-ttu-id="b3b6b-140">SharePoint- und OneDrive haben eine administratoreinstellung zur Angabe der Standard-Verknüpfungstyp für Links, die für eine Datei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="b3b6b-141">Teams ist, derselbe Ansatz entscheiden, durch die Wiederverwendung von den Einstellungen, die der Administrator für SharePoint und OneDrive festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="b3b6b-142">Weitere Informationen zu diesem Ansatz werden in [der Standard-Verknüpfungstyp Aktion für Benutzer Links für die Freigabe ändern](https://docs.microsoft.com/sharepoint/change-default-sharing-link)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3b6b-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="b3b6b-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3b6b-143">More information</span></span>

<span data-ttu-id="b3b6b-144">Weitere Informationen zur Funktionsweise von SharePoint mit den Teams, finden Sie unter [SharePoint und Teams: ein starkes Team](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="b3b6b-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="b3b6b-145">Lesen Sie weitere Informationen zu den Gast Erfahrung in Teams zu finden, [Was die Erfahrung Gast ist, wie](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="b3b6b-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

