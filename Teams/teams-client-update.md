---
title: Updates für Teams
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
description: In diesem Artikel erfahren Sie, wie der Microsoft Teams-Desktopclient aktualisiert wird.
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
# <a name="teams-update-process"></a>Aktualisierungsprozess von Teams

Die Teams Web App wird wöchentlich aktualisiert.

Updates für Den Desktopclient von Teams werden alle zwei Wochen nach strengen internen Tests und Überprüfungen über unser Technology Adoption Program (TAP) veröffentlicht. Das Update findet in der Regel an einem Dienstag statt. Wenn ein kritisches Update erforderlich ist, umgehen Teams diesen Zeitplan und veröffentlicht das Update, sobald es verfügbar ist.

Der Desktopclient wird automatisch aktualisiert. Teams sucht alle paar Stunden hinter den Kulissen nach Updates, lädt sie herunter und wartet dann, bis der Computer im Leerlauf ist, bevor das Update automatisch installiert wird.

Benutzer können Updates auch  manuell herunterladen,  indem sie oben rechts in der App im Dropdownmenü Profil auf Updates überprüfen klicken. Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können.

Ab dem 31. Juli 2019 verwenden Teams-Clientupdates während des Updates eine geringere Netzwerkbandbreite. Dieses Update ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Wie sieht es mit Updates für Microsoft 365-Apps für Unternehmen aus?

Teams wird standardmäßig mit neuen Installationen von Microsoft 365-Apps für Unternehmen installiert, wie unter Bereitstellen von [Microsoft Teams mit Microsoft 365-Apps für Unternehmen beschrieben.](/DeployOffice/teams-install)

Teams verfolgt einen eigenen Updateprozess, wie oben beschrieben. Teams folgt nicht dem Updateprozess für die anderen Offices-Apps, z. B. Word und Excel. Weitere Informationen finden Sie unter [Übersicht über Updatekanäle für Microsoft 365-Apps für Unternehmen.](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Wie sieht es mit Updates für Teams auf VDI aus?


Teams-Clients in virtual Desktop Infrastructure (VDI) werden nicht automatisch auf die Art und Weise aktualisiert, in der nicht VDI Teams-Clients sind. Sie müssen das VM-Image aktualisieren, indem Sie ein neues MSI installieren, wie in den Anweisungen zum Installieren von [Teams auf VDI beschrieben.](teams-for-vdi.md) Sie müssen zum Aktualisieren der Teams-App die aktuelle Version deinstallieren, um auf eine neuere Version aktualisieren zu können.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates anstelle der automatischen Aktualisierung von Teams bereitstellen?

Teams gibt Administratoren nicht die Möglichkeit, Updates über einen Übermittlungsmechanismus zu bereitstellen.

## <a name="servicing-agreement"></a>Wartungsvertrag

Als moderner Onlinedienst wird der Teams-Client alle zwei Wochen automatisch aktualisiert. Da Teams der Modern Lifecycle-Richtlinie unterliegt, wird erwartet, dass die Benutzer auf der neuesten Version des Desktopclients bleiben. Automatische Updates stellen sicher, dass Benutzer über die neuesten Funktionen, Leistungsverbesserungen, Sicherheit und Dienstzuverlässigkeit verfügen.

Um zu ermitteln, wann Desktopclients nicht mehr aktuell sind, wird eine In-App-Benachrichtigung angezeigt, wenn die aktuelle Version des Benutzers ein bis drei Monate alt ist und eine neue Version verfügbar ist. Diese In-App-Messaging ermutigt Benutzer, auf die neueste Version von Teams zu aktualisieren oder bei Bedarf an ihren IT-Administrator zu gelangen, um dies zu tun. Benutzern auf Teams-Desktopclients, die mehr als drei Monate alt sind, wird eine Sperrseite angezeigt, auf der die Optionen angezeigt werden, um jetzt zu aktualisieren, sich an ihren IT-Administrator zu erreichen oder mit Teams im Web fortzufahren.

Desktopclientversionen, die bei der ersten Installation und/oder ersten Ausführung von Teams mehr als drei Monate alt sind, verfügen über eine 28-tägige Nachfrist, bevor die oben genannten Wartungsinformationen angezeigt werden. Während dieses Zeitraums wird der Teams-Client durch den Automatischen Updatevorgang aktualisiert. Wenn sie nicht aktualisiert werden, wird eine In-App-Benachrichtigung angezeigt, in der sie dazu ermutigt werden, manuell auf die neueste Version von Teams zu aktualisieren. Die Benutzer werden möglicherweise aufgefordert, sich an ihren IT-Administrator zu wenden, um das Update zu machen. Dies schließt Benutzer ein, die den Microsoft 365-Desktopclient als Teil des Microsoft 365-Apps für Enterprise-Bündels verwenden.

Teams-Desktopclients in Government Clouds haben derzeit bis auf weiteres eine Ausnahme von diesem Wartungsvertrag.

Informationen zu neuen Versionen finden Sie im [Nachrichtencenter,](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) oder wechseln Sie zu **Hilfe** zu den  >   neuen Versionen im Client.
