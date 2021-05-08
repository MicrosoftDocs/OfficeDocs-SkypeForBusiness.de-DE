---
title: Teams Updates
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
description: In diesem Artikel erfahren Sie mehr über den Vorgang hinter dem Aktualisieren des Microsoft Teams Desktopclients.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119244"
---
# <a name="teams-update-process"></a>Teams des Aktualisierungsvorgangs

Die Teams Web App wird wöchentlich aktualisiert.

Teams Desktopclientupdates werden alle zwei Wochen nach strengen internen Tests und Überprüfungen durch unser Programm zur Einführung von Technologie (Technology Adoption Program, TAP) veröffentlicht. Das Update findet normalerweise an einem Dienstag statt. Wenn ein kritisches Update erforderlich ist, Teams die Aktualisierung umgehen und das Update veröffentlichen, sobald es verfügbar ist.

Der Desktopclient wird automatisch aktualisiert. Teams im Hintergrund alle paar Stunden nach Updates sucht, lädt sie herunter und wartet dann darauf, dass sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.

Benutzer können Updates auch manuell herunterladen,  indem sie oben rechts **in** der App im Dropdownmenü Profil die Option Nach Updates suchen auswählen. Wenn ein Update verfügbar ist, wird es heruntergeladen und im Leerlauf des Computers automatisch installiert.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können.

Ab dem 31. Juli 2019 Teams Für Clientupdates wird während des Updates eine geringere Netzwerkbandbreite verwendet. Dieses Update ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Wie sieht es mit Updates für Microsoft 365 Apps for Enterprise?

Teams wird standardmäßig mit neuen Installationen von Microsoft 365 Apps for Enterprise installiert, wie unter Bereitstellen von Microsoft Teams [mit Microsoft 365 Apps for Enterprise](/DeployOffice/teams-install)beschrieben.

Teams verwendet einen eigenen Updateprozess, wie oben beschrieben. Teams wird für die anderen Büros-Apps, z. B. Word und Excel, nicht Excel. Weitere Informationen finden Sie unter [Übersicht über die Updatekanäle für Microsoft 365 Apps for Enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Wie sieht es mit Updates für Teams VDI aus?


Teams Clients in VDI (Virtual Desktop Infrastructure) werden nicht automatisch so aktualisiert, wie es sich nicht für VDI- Teams Clients handelt. Sie müssen das VM-Bild aktualisieren, indem Sie eine neue MSI installieren, wie in den Anweisungen zum Installieren von Teams [auf VDI beschrieben.](teams-for-vdi.md) Sie müssen zum Aktualisieren der Teams-App die aktuelle Version deinstallieren, um auf eine neuere Version aktualisieren zu können.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates bereitstellen, statt Teams Updates zu installieren?

Teams gibt Administratoren nicht die Möglichkeit, Updates über einen Beliebigen Übermittlungsmechanismus bereitstellen.

## <a name="servicing-agreement"></a>Wartungsvertrag

Als moderner Onlinedienst wird der client Teams alle zwei Wochen automatisch aktualisiert. Da Teams der modernen Lebenszyklusrichtlinie unterliegt, wird erwartet, dass Benutzer die neueste Version des Desktopclients verwenden. Automatische Updates stellen sicher, dass Benutzer über die neuesten Funktionen, Leistungsverbesserungen, Sicherheit und Dienstzuverlässigkeit verfügen.

Um zu ermitteln, wann Desktopclients nicht mehr aktuell sind, wird eine In-App-Benachrichtigung angezeigt, wenn die aktuelle Version des Benutzers zwischen einem und drei Monaten alt ist und eine neue Version verfügbar ist. Bei diesem In-App-Messaging werden Die Benutzer ermutigt, auf die neueste Teams zu aktualisieren oder sich bei Bedarf an den IT-Administrator zu ermuntern, dies zu tun. Benutzern auf Teams-Desktopclients, die mehr als drei Monate alt sind, wird eine Sperrseite angezeigt, auf der die Optionen zum Jetzt aktualisieren, sich an den IT-Administrator oder weiterhin Teams im Web befinden.

Desktopclientversionen, die bei der ersten Installation und/oder ersten Ausführung von Teams mehr als drei Monate alt sind, verfügen über eine Nachfrist von 28 Tagen, bevor sie auf die oben genannten Wartungsinformationen treffen. Während dieses Zeitraums wird der Client durch die automatische Aktualisierung Teams aktualisiert. Wenn keine Aktualisierung erfolgt, werden Benutzer in einer In-App-Benachrichtigung dazu ermutigt, manuell auf die neueste Version von Teams. Die Benutzer werden möglicherweise aufgefordert, sich an ihren IT-Administrator zu wenden, um das Update zu tun. Dies schließt Benutzer ein, die Teams-Desktopclient als Teil des Pakets Microsoft 365 Apps for Enterprise verwenden.

Teams Desktopclients auf Government Clouds haben derzeit bis auf weitere Ankündigung eine Ausnahme von diesem Wartungsvertrag.

Informationen zu neuen Versionen finden Sie im [Nachrichtencenter,](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) oder wechseln Sie zu **Hilfe** zu den neuen  >   Versionen des Clients.
