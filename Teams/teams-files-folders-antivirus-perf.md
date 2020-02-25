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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265620"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="4f2ba-103">Teamdateien und -ordner, die vom Antivirusscan ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="4f2ba-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="4f2ba-104">Sie können die Gesamtleistung Ihrer Teams-Bereitstellung verbessern, indem Sie verhindern, dass Ihre Antivirenprogramme bestimmte Teams-Dateien und-Ordner durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="4f2ba-105">Dadurch wird der Aufwand für Systemressourcen beim Scannen von Dateien und Ordnern vermieden, die nicht gescannt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="4f2ba-106">Wenn Ihre Benutzer Dateien herunterladen oder Dateien für andere Personen freigeben, werden diese Dateien nicht an den im folgenden Abschnitt aufgeführten Speicherorten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="4f2ba-107">Die Speicherorte, an denen Ihre Benutzer Dateien hochladen, herunterladen oder freigeben, werden von Ihrem Antivirenprogramm weiterhin regelmäßig gescannt.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="4f2ba-108">Dateien und Ordner, die zu ihren Antivirus-Listen hinzugefügt werden sollen</span><span class="sxs-lookup"><span data-stu-id="4f2ba-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="4f2ba-109">Verwenden Sie die vom Antivirus-Programm unterstützten Verfahren, um die folgenden Dateien und Ordner zu ihren sicheren Listen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="4f2ba-110">Dadurch werden Systemressourcen gespart, indem Antivirus-Scans dieser Speicherorte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="4f2ba-111">Programme</span><span class="sxs-lookup"><span data-stu-id="4f2ba-111">Programs</span></span>

<span data-ttu-id="4f2ba-112">Fügen Sie die folgenden Teams-Programme zu Ihrer Antivirus-Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="4f2ba-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="4f2ba-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="4f2ba-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="4f2ba-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="4f2ba-115">Ordner</span><span class="sxs-lookup"><span data-stu-id="4f2ba-115">Folders</span></span>

<span data-ttu-id="4f2ba-116">Fügen Sie der Liste der sicheren Antivirus-Dateien die folgenden Teams-Ordner hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f2ba-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="4f2ba-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4f2ba-117">Category</span></span>  |<span data-ttu-id="4f2ba-118">Ort</span><span class="sxs-lookup"><span data-stu-id="4f2ba-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="4f2ba-119">Programmdateien</span><span class="sxs-lookup"><span data-stu-id="4f2ba-119">Program files</span></span>  |<span data-ttu-id="4f2ba-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4f2ba-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="4f2ba-121">Datendateien</span><span class="sxs-lookup"><span data-stu-id="4f2ba-121">Data files</span></span>     |<span data-ttu-id="4f2ba-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4f2ba-122">%appdata%\Microsoft\Teams</span></span>\ |
