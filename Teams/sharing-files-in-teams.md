---
title: Freigabe von Dateien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
search.appverid: MET150
description: Microsoft Teams verwendet die Einstellungen von OneDrive und SharePoint zum Steuern der Freigabe.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae468fdb38c047ae257efeda2465949b1babcb01
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931793"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="9505d-103">Freigabe von Dateien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9505d-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="9505d-104">Mit den Dateifreigabe Features in Teams können Benutzer Inhalte für andere Team Benutzer in Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="9505d-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="9505d-105">Die Freigabe in Teams basiert auf den in SharePoint und OneDrive konfigurierten Einstellungen, sodass die für SharePoint und OneDrive eingerichteten Einstellungen auch die Freigabe in Teams steuern.</span><span class="sxs-lookup"><span data-stu-id="9505d-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

![Diagramm, das zeigt, wie Teams, SharePoint und OneDrive zusammenarbeiten](media/sharing-files-in-teams-image1.png)

<span data-ttu-id="9505d-107">Durch die Freigabe von Teams können Benutzer die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9505d-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="9505d-108">Freigeben von Dateien von OneDrive</span><span class="sxs-lookup"><span data-stu-id="9505d-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="9505d-109">Sie können Berechtigungen für Dateien einrichten, die Sie für andere freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9505d-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="9505d-110">Freigeben von Dateien in Teams.</span><span class="sxs-lookup"><span data-stu-id="9505d-110">Share files across Teams.</span></span>

- <span data-ttu-id="9505d-111">Freigeben von Dateien aus der Liste der zuletzt geöffneten Dateien (in der Regel sind dies die Dateien, an denen die Benutzer am meisten interessiert sind).</span><span class="sxs-lookup"><span data-stu-id="9505d-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="9505d-112">Bleiben Sie in Teams, wenn Sie auf einen Dateinamen klicken, um eine Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9505d-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="9505d-113">Teams verkürzt lange SharePoint-URLs und Browser-URLs, die auf eine Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="9505d-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="9505d-114">Teams verwendet nur den Dateinamen, um eine Verknüpfung mit einer Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9505d-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="9505d-115">Darüber hinaus wurde die Option " **Link abrufen** " in " **Link kopieren** " geändert, um jegliche Verwirrung zu vermeiden, die Benutzer möglicherweise haben, wenn Sie anderen Zugriff auf eine Datei gewähren möchten.</span><span class="sxs-lookup"><span data-stu-id="9505d-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="9505d-116">Konfigurieren der Freigabe in OneDrive und SharePoint</span><span class="sxs-lookup"><span data-stu-id="9505d-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="9505d-117">Weitere Informationen zum Freigeben von Dateien in OneDrive und SharePoint, einschließlich der Konfiguration der Freigabe und der Aktivierung und Deaktivierung von Freigaben, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="9505d-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="9505d-118">[Übersicht über externe Freigabe](https://docs.microsoft.com/sharepoint/external-sharing-overview) – beschreibt, was geschieht, wenn Benutzer die Freigabe durchgeführt haben, je nachdem, was Sie teilen und mit wem.</span><span class="sxs-lookup"><span data-stu-id="9505d-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="9505d-119">[Aktivieren oder Deaktivieren der externen Freigabe](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – beschreibt, wie globale und SharePoint-Administratoren ihre Freigabeeinstellungen auf Organisationsebene für SharePoint und OneDrive ändern können.</span><span class="sxs-lookup"><span data-stu-id="9505d-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="9505d-120">[Ändern der externen Freigabe für eine Website](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – beschreibt, wie globale und SharePoint-Administratoren die externe Freigabe für eine Website aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="9505d-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="9505d-121">[Ändern des Standard Link Typs, wenn Benutzer Links für die Freigabe erhalten](https://docs.microsoft.com/sharepoint/change-default-sharing-link) , beschreibt, wie Sie den Standardverknüpfungstyp so festlegen, dass er restriktiver ist.</span><span class="sxs-lookup"><span data-stu-id="9505d-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="9505d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9505d-122">More information</span></span>

- [<span data-ttu-id="9505d-123">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9505d-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="9505d-124">[SharePoint und Teams: besser zusammen](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="9505d-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="9505d-125">Freigeben von OneDrive-Dateien und-Ordnern</span><span class="sxs-lookup"><span data-stu-id="9505d-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="9505d-126">Freigeben von SharePoint-Dateien oder-Ordnern</span><span class="sxs-lookup"><span data-stu-id="9505d-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

