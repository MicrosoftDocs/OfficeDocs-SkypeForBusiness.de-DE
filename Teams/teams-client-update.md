---
title: Teams-Updates
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie mehr über den Prozess hinter der Aktualisierung des Microsoft Teams-Desktopclients.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 136cca899b0c79b549ee9ae890e90f1e84c04eaa
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506384"
---
# <a name="teams-update-process"></a>Teams-Updateprozess

Die Teams-Web-App wird wöchentlich aktualisiert.

Updates des Microsoft Teams-Desktopclients werden alle zwei Wochen nach strengen internen Tests und Überprüfungen veröffentlicht. Das Update findet in der Regel an einem Dienstag statt. Bei wichtigen Updates wird dieser Zeitplan von Microsoft Teams umgangen, und die Updates werden freigegeben, sobald sie verfügbar sind.

Der Desktopclient wird automatisch aktualisiert. Teams sucht im Hintergrund alle paar Stunden nach Updates, lädt sie herunter und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update im Hintergrund installiert wird.

Benutzer können Updates auch manuell herunterladen, indem sie oben rechts in der App im Dropdownmenü **Profil** **Nach Updates suchen** auswählen. Wenn ein Update verfügbar ist, wird es heruntergeladen und im Hintergrund installiert, wenn sich der Computer im Leerlauf befindet.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können.

Ab dem 31. Juli 2019 verwenden Teams-Clientupdates während des Updates eine geringere Netzwerkbandbreite. Dieses Update ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Was ist mit Updates für Microsoft 365 Apps for Enterprise?

Teams wird standardmäßig mit neuen Installationen von Microsoft 365 Apps for Enterprise installiert, wie in [Bereitstellen von Microsoft Teams mit Microsoft 365 Apps for Enterprise](/DeployOffice/teams-install) beschrieben.

Teams folgt einem eigenen Updateprozess, wie oben beschrieben. Dieser Updateprozess für Microsoft Teams unterscheidet sich von dem Updateprozess für die anderen Office-Apps wie Word und Excel. Weitere Informationen finden Sie unter [Übersicht über die Updatekanäle für Microsoft 365 Apps for Enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus).

## <a name="what-about-updates-to-teams-on-vdi"></a>Wie sieht es mit Updates für Teams auf VDI aus?


Teams-Clients in Virtual Desktop Infrastructure (VDI) werden nicht automatisch auf die gleiche Weise aktualisiert wie Nicht-VDI-Teams-Clients. Sie müssen das VM-Image aktualisieren, indem Sie eine neue MSI installieren, wie im Abschnitt [Installieren oder Aktualisieren der Teams-Desktop-App auf VDI](teams-for-vdi.md) beschrieben. Sie müssen zum Aktualisieren der Teams-App die aktuelle Version deinstallieren, um auf eine neuere Version aktualisieren zu können.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates bereitstellen, anstelle der automatischen Aktualisierung von Teams?

Teams bietet Administratoren nicht die Möglichkeit, Updates über einen Übermittlungsmechanismus bereitzustellen.

## <a name="servicing-agreement"></a>Wartungsvertrag

Als moderner Onlinedienst wird der Teams-Client alle zwei Wochen automatisch aktualisiert. Da Teams der Modern Lifecycle-Richtlinie unterliegt, wird davon ausgegangen, dass Benutzer auf der aktuellsten Version des Desktopclients bleiben. Automatische Updates stellen sicher, dass Benutzer über die neuesten Funktionen, Leistungsverbesserungen, über Sicherheit und Dienstzuverlässigkeit verfügen.

Um zu ermitteln, wann Desktopclients veraltet sind, wird eine In-App-Warnung angezeigt, wenn die aktuelle Version des Benutzers zwischen einem und drei Monaten alt ist, und falls eine neue Version verfügbar ist. Dieses In-App-Messaging empfiehlt Benutzern, auf die neueste Version von Teams zu aktualisieren oder sich, falls nötig, an ihren IT-Administrator zu wenden. Benutzern auf Teams-Desktopclients, die älter als drei Monate sind, wird eine Sperrseite angezeigt, auf der Sie sämtliche Optionen zum Aktualisieren, zum Kontaktieren Ihres IT-Administrators oder zum Fortfahren mit Teams im Web finden.

Teams-Desktopclients in Government-Clouds haben derzeit bis auf weiteres eine Ausnahme von diesem Wartungsvertrag.

Informationen zu neuen Versionsreleases finden Sie im [Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) oder im Client unter **Hilfe** > **Neuerungen**.
