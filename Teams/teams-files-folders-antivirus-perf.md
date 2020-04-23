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
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Teamdateien und -ordner, die vom Antivirusscan ausgeschlossen werden sollen
=================================

Sie können die Gesamtleistung Ihrer Teams-Bereitstellung verbessern, indem Sie verhindern, dass Ihre Antivirenprogramme bestimmte Teams-Dateien und-Ordner durchsuchen. Dadurch wird der Aufwand für Systemressourcen beim Scannen von Dateien und Ordnern vermieden, die nicht gescannt werden müssen.

> [!NOTE]
> Wenn Ihre Benutzer Dateien herunterladen oder Dateien für andere Personen freigeben, werden diese Dateien nicht an den im folgenden Abschnitt aufgeführten Speicherorten durchlaufen. Die Speicherorte, an denen Ihre Benutzer Dateien hochladen, herunterladen oder freigeben, werden von Ihrem Antivirenprogramm weiterhin regelmäßig gescannt.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>Dateien und Ordner, die zu ihren Antivirus-Listen hinzugefügt werden sollen

Verwenden Sie die vom Antivirus-Programm unterstützten Verfahren, um die folgenden Dateien und Ordner zu ihren sicheren Listen hinzuzufügen. Dadurch werden Systemressourcen gespart, indem Antivirus-Scans dieser Speicherorte vermieden werden.

### <a name="programs"></a>Programme

Fügen Sie die folgenden Teams-Programme zu Ihrer Antivirus-Liste hinzu.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

