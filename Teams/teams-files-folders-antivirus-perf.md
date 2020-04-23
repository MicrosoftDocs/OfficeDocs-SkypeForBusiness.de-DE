---
title: Teamdateien und -ordner, die vom Antivirusscan ausgeschlossen werden sollen
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Verbessern Sie die Leistung von Teams, indem Sie bestimmte Dateien und Ordner aus dem normalen Virenscan ausschließen.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579591"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="a96a6-103">Teamdateien und -ordner, die vom Antivirusscan ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="a96a6-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="a96a6-104">Sie können die Gesamtleistung Ihrer Teams-Bereitstellung verbessern, indem Sie verhindern, dass Ihre Antivirenprogramme bestimmte Teams-Dateien und-Ordner durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="a96a6-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="a96a6-105">Dadurch wird der Aufwand für Systemressourcen beim Scannen von Dateien und Ordnern vermieden, die nicht gescannt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a96a6-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="a96a6-106">Wenn Ihre Benutzer Dateien herunterladen oder Dateien für andere Personen freigeben, werden diese Dateien nicht an den im folgenden Abschnitt aufgeführten Speicherorten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a96a6-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="a96a6-107">Die Speicherorte, an denen Ihre Benutzer Dateien hochladen, herunterladen oder freigeben, werden von Ihrem Antivirenprogramm weiterhin regelmäßig gescannt.</span><span class="sxs-lookup"><span data-stu-id="a96a6-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="a96a6-108">Dateien und Ordner, die zu ihren Antivirus-Listen hinzugefügt werden sollen</span><span class="sxs-lookup"><span data-stu-id="a96a6-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="a96a6-109">Verwenden Sie die vom Antivirus-Programm unterstützten Verfahren, um die folgenden Dateien und Ordner zu ihren sicheren Listen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a96a6-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="a96a6-110">Dadurch werden Systemressourcen gespart, indem Antivirus-Scans dieser Speicherorte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="a96a6-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="a96a6-111">Programme</span><span class="sxs-lookup"><span data-stu-id="a96a6-111">Programs</span></span>

<span data-ttu-id="a96a6-112">Fügen Sie die folgenden Teams-Programme zu Ihrer Antivirus-Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="a96a6-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="a96a6-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="a96a6-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="a96a6-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="a96a6-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

