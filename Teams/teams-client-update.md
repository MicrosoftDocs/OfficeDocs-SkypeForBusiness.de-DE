---
title: Teams-Updates
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie mehr über den Prozess hinter dem Aktualisieren des Microsoft Teams-Desktop Clients.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 107ef412c7c4faa3e4e0ae3ad9a8539c3bf70dec
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903150"
---
# <a name="teams-update-process"></a>Updateprozess für Teams

Die Team-Web-App wird wöchentlich aktualisiert.

Updates für Teams-Desktop Clients werden alle zwei Wochen nach rigoroser interner Prüfung und Validierung über unser Technologie Adoptionsprogramm (Tap) veröffentlicht. Dies erfolgt in der Regel an einem Dienstag. Wenn ein wichtiges Update erforderlich ist, werden die Teams diesen Zeitplan umgehen und das Update freigeben, sobald es verfügbar ist.

Der Desktop-Client wird automatisch aktualisiert. Teams überprüft alle paar Stunden hinter den Kulissen, ob Updates vorhanden sind, lädt Sie herunter, und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.

Benutzer können Updates auch manuell herunterladen, indem Sie im Dropdownmenü **Profil** oben rechts in der APP auf auf **Updates überprüfen** klicken. Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können. 

Ab dem 31. Juli 2019 verwenden Teams-Clientupdates während des Updates deutlich geringere Netzwerkbandbreite. Dies ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Was ist mit Updates für Microsoft 365-Apps für Unternehmen?

Teams wird standardmäßig mit neuen Installationen von Microsoft 365-Apps für Unternehmen installiert, wie unter [Bereitstellen von Microsoft Teams mit Microsoft 365-Apps für Unternehmen](https://docs.microsoft.com/DeployOffice/teams-install)beschrieben. 

Teams folgt seinen eigenen Aktualisierungsprozess, wie oben beschrieben, und nicht den Updateprozess für die anderen Office-Apps wie Word und Excel. Weitere Informationen finden Sie unter [Übersicht über die Update Kanäle für Microsoft 365-Apps für Unternehmen](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .

## <a name="what-about-updates-to-teams-on-vdi"></a>Was ist mit Updates für Teams auf VDI?

Teams-Clients in der Virtual Desktop Infrastructure (VDI) werden nicht automatisch so aktualisiert, wie es Clients von nicht-VDI-Teams sind. Sie müssen das VM-Abbild aktualisieren, indem Sie eine neue MSI-Datei installieren, wie in den Anleitungen zum [Installieren von Teams auf VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)beschrieben. Sie müssen die aktuelle Version deinstallieren, um Sie auf eine neuere Version zu aktualisieren.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates anstelle der automatischen Aktualisierung von Teams bereitstellen?

Teams bietet Administratoren keine Möglichkeit zum Bereitstellen von Updates über einen beliebigen Übermittlungsmechanismus.

## <a name="servicing-agreement"></a>Wartungsvereinbarung

Als moderner Onlinedienst wird der Client für Teams alle zwei Wochen automatisch aktualisiert. Da Teams der modernen Lebenszyklusrichtlinie unterliegen, wird davon ausgegangen, dass die Benutzer auf der aktuellsten Version des Desktop Clients verbleiben. Dadurch wird sichergestellt, dass die Benutzer über die neuesten Funktionen, Leistungsverbesserungen, Sicherheit und Zuverlässigkeit des Diensts verfügen.

Um zu helfen, zu ermitteln, wann Desktop Clients veraltet sind, wird eine in-App-Benachrichtigung angezeigt, wenn die aktuelle Version des Benutzers zwischen einem und drei Monaten alt ist und wenn eine neue Version verfügbar ist. Dieses in-App-Messaging ermutigt Benutzer dazu, auf die neueste Version von Teams zu aktualisieren oder, falls erforderlich, den IT-Administrator zu erreichen. Benutzer von Microsoft Teams-Desktop Clients, die älter als drei Monate sind, sehen eine blockierungsseite, auf der die Optionen zum sofortigen aktualisieren angezeigt werden, um sich an Ihren IT-Administrator zu wenden oder um mit Teams im Web fortzufahren.

Desktop Clientversionen, die bei der ersten Installation und/oder der ersten Ausführung von Teams mehr als drei Monate alt sind, haben eine Frist von 28 Tagen, bevor Sie auf die oben genannten Wartungsinformationen stoßen. Während dieses Zeitraums aktualisiert der automatische Aktualisierungsprozess den Client für Teams. Wenn Sie nicht aktualisiert werden, wird den Benutzern eine in-App-Benachrichtigung angezeigt, in der Sie dazu ermutigt werden, manuell auf die neueste Version von Teams zu aktualisieren oder, falls erforderlich, den IT-Administrator zu erreichen. Dazu gehören Benutzer, die den Team-Desktop Client als Teil des Microsoft 365-Pakets für Apps für Unternehmen verwenden.

Teams-Desktop Clients in Regierungs Clouds haben derzeit eine Ausnahme von dieser Wartungsvereinbarung bis auf weiteres.

Informationen zu neuen Versions Versionen finden Sie im [Nachrichten Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) oder unter **Hilfe** > zu den**Neuerungen** im Client.
