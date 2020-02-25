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

### <a name="folders"></a>Ordner

Fügen Sie der Liste der sicheren Antivirus-Dateien die folgenden Teams-Ordner hinzu.

|Kategorie  |Ort  |
|---------|---------|
|Programmdateien  |%localappdata%\Microsoft\Teams|
|Datendateien     |%appdata%\Microsoft\Teams\ |
