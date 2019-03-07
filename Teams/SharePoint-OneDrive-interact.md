---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: article
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
ms.openlocfilehash: 1d9bb769c1ad99f0990192ed0bdad69af71dd8c5
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460276"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="c0e42-103">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0e42-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

> [!Tip]
> <span data-ttu-id="c0e42-104">Sehen Sie sich die folgenden Sitzung um zu erfahren, wie Teams interagiert mit Azure Active Directory (AAD), Gruppen von Office 365, Exchange, SharePoint und OneDrive für Unternehmen: [Grundlagen der Microsoft-Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="c0e42-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="c0e42-p101">Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.</span><span class="sxs-lookup"><span data-stu-id="c0e42-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="c0e42-107">Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c0e42-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="c0e42-108">Wenn Benutzer sind nicht zugewiesen und mit SharePoint Online-Lizenzen aktiviert, verfügen nicht OneDrive for Business-Speicher in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0e42-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="c0e42-109">Dateifreigabe wird in weiterhin, Kanäle, aber Benutzer werden nicht in der Lage, Freigeben von Dateien in Chats ohne OneDrive for Business-Speicher in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0e42-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="c0e42-110">Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.</span><span class="sxs-lookup"><span data-stu-id="c0e42-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="c0e42-111">Integration in lokale Sharepoint-wird für Microsoft-Teams, zu diesem Zeitpunkt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c0e42-111">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="c0e42-112">Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c0e42-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="c0e42-p103">Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c0e42-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramm des Ordners „Freigegebene Dokumente“ in SharePoint Online für ein Team und dessen Kanäle in Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="c0e42-116">Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c0e42-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="c0e42-117">Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="c0e42-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="c0e42-118">In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c0e42-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="c0e42-119">Hinzufügen eine Registerkarte an Ihr Team, die zu einer vorhandenen SharePoint-Website-Seite oder in Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft:</span><span class="sxs-lookup"><span data-stu-id="c0e42-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="c0e42-120">Wählen Sie das Pluszeichen (+) neben den Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="c0e42-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="c0e42-121">Wählen Sie **SharePoint** für eine vorhandene Seite der SharePoint-Website oder **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c0e42-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="c0e42-122">Wählen Sie aus der entsprechenden Seite oder -Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c0e42-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="c0e42-123">Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="c0e42-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramm des OneDrive-Ordners „Microsoft Teams-Chatdateien“ für die Chats der einzelnen Benutzer](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a><span data-ttu-id="c0e42-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0e42-125">More information</span></span>
----------------

<span data-ttu-id="c0e42-126">Weitere Informationen zur Funktionsweise von SharePoint mit den Teams, finden Sie unter [SharePoint und Teams: ein starkes Team](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="c0e42-126">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>


