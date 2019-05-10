---
title: Freigeben von Dateien in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Microsoft-Teams, verwendet die Einstellungen von OneDrive und SharePoint zum Steuern der Freigabe.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69f4ee036c951197e697c1f74bffb5c079d85bc3
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835075"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="3fac0-103">Freigeben von Dateien in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="3fac0-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="3fac0-104">Die Datei Freigabefeatures in Teams kann Benutzer Inhalte für andere Teams Benutzer in ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="3fac0-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="3fac0-105">Freigabe in Teams basiert auf der Einstellungen in SharePoint und OneDrive, was Sie für SharePoint und OneDrive einrichten sowie Freigabe in Teams steuern werden konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3fac0-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

<span data-ttu-id="3fac0-106">Freigeben von Teams können Benutzer folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="3fac0-106">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="3fac0-107">Freigeben von Dateien aus OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3fac0-107">Share files from OneDrive.</span></span>

- <span data-ttu-id="3fac0-108">Festlegen von Berechtigungen für Dateien, die sie für andere Personen freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="3fac0-108">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="3fac0-109">Freigeben von Dateien für mehrere Teams.</span><span class="sxs-lookup"><span data-stu-id="3fac0-109">Share files across Teams.</span></span>

- <span data-ttu-id="3fac0-110">Freigeben von Dateien aus der Liste der zuletzt geöffneten Dateien (in der Regel sind die Benutzer am häufigsten interessiert Freigeben von sind Dateien).</span><span class="sxs-lookup"><span data-stu-id="3fac0-110">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="3fac0-111">Bleiben Sie innerhalb der Teams, wenn sie einen Dateinamen zum Öffnen einer Datei klicken.</span><span class="sxs-lookup"><span data-stu-id="3fac0-111">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="3fac0-112">Teams verkürzt lang SharePoint-URLS und Browser URLS, die in eine Datei zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3fac0-112">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="3fac0-113">Teams wird nur der Dateiname zur Verknüpfung mit einer Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fac0-113">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="3fac0-114">Darüber hinaus wurde die Option **Link Get** **Link kopieren** , um Verwechslungen zu vermeiden, die Benutzer verfügen möglicherweise über die andere Benutzer Zugriff auf eine Datei geändert.</span><span class="sxs-lookup"><span data-stu-id="3fac0-114">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="3fac0-115">Konfigurieren der Freigabe in OneDrive und SharePoint</span><span class="sxs-lookup"><span data-stu-id="3fac0-115">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="3fac0-116">Weitere Informationen zum Freigeben von Dateien in OneDrive und SharePoint einschließlich zum Konfigurieren der Freigabe und zum Aktivieren der Freigabe auf und deaktiviert werden kann, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="3fac0-116">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="3fac0-117">[Übersicht über die externe Freigabe](https://docs.microsoft.com/sharepoint/external-sharing-overview) - wird beschrieben, was geschieht, wenn Benutzer gemeinsam verwenden, je nachdem, was sie gerade freigeben und mit denen.</span><span class="sxs-lookup"><span data-stu-id="3fac0-117">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="3fac0-118">[Externe Freigabe ein- oder ausschalten aktivieren](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - wird beschrieben, wie globale und SharePoint-Administratoren können deren Freigabe auf Organisationsebene-Einstellungen für SharePoint und OneDrive ändern.</span><span class="sxs-lookup"><span data-stu-id="3fac0-118">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="3fac0-119">[Externe Freigabe für eine Website ändern](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – beschreibt Funktionsweise globaler und SharePoint-Administratoren können externe Freigabe ein- oder ausschalten für eine Website aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3fac0-119">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="3fac0-120">[Ändern der Standard-Verknüpfungstyp Aktion für Benutzer Links für die Freigabe](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - wird beschrieben, wie der Standard-Verknüpfungstyp festgelegt, sodass restriktiver ist.</span><span class="sxs-lookup"><span data-stu-id="3fac0-120">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="3fac0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fac0-121">More information</span></span>

- [<span data-ttu-id="3fac0-122">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fac0-122">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="3fac0-123">[SharePoint und Teams: ein starkes Team](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="3fac0-123">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="3fac0-124">Freigeben von OneDrive-Dateien und Ordnern</span><span class="sxs-lookup"><span data-stu-id="3fac0-124">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="3fac0-125">Freigeben von SharePoint-Dateien oder Ordner</span><span class="sxs-lookup"><span data-stu-id="3fac0-125">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

