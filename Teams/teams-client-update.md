---
title: Teams-Updates
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Erfahren Sie, wie der Desktop Client von Teams aktualisiert wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 436a2a3175cd057082c0e658ea5ab6d3db0364cc
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588183"
---
# <a name="teams-update-process"></a>Updateprozess für Teams

Die Team-Web-App wird wöchentlich aktualisiert.

Updates für Teams-Desktop Clients werden alle zwei Wochen nach rigoroser interner Prüfung und Validierung über unser Technologie Adoptionsprogramm (Tap) veröffentlicht. Dies erfolgt in der Regel an einem Dienstag. Wenn ein wichtiges Update erforderlich ist, werden die Teams diesen Zeitplan umgehen und das Update freigeben, sobald es verfügbar ist.

Der Desktop-Client wird automatisch aktualisiert. Teams überprüft alle paar Stunden hinter den Kulissen, ob Updates vorhanden sind, lädt Sie herunter, und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.

Benutzer können Updates auch manuell herunterladen, indem Sie im Dropdownmenü **Profil** oben rechts in der APP auf auf **Updates überprüfen** klicken. Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können. Ab dem 9. Juli 2019 verwenden Teams-Clientupdates während des Updates deutlich geringere Netzwerkbandbreite. Dies ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.


## <a name="what-about-updates-to-office-365-proplus"></a>Was ist mit Updates für Office 365 ProPlus?

Teams wird standardmäßig mit neuen Installationen von Office 365 ProPlus installiert, wie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)beschrieben. 

Teams folgt seinen eigenen Aktualisierungsprozess, wie oben beschrieben, und nicht den Updateprozess für die anderen Office-Apps wie Word und Excel. Weitere Informationen finden Sie unter [Übersicht über die Update Kanäle für Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .

## <a name="what-about-updates-to-teams-on-vdi"></a>Was ist mit Updates für Teams auf VDI?

Teams-Clients in der Virtual Desktop Infrastructure (VDI) werden nicht automatisch so aktualisiert, wie es Clients von nicht-VDI-Teams sind. Sie müssen das VM-Abbild aktualisieren, indem Sie eine neue MSI-Datei installieren, wie in den Anleitungen zum [Installieren von Teams auf VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)beschrieben. Sie müssen die aktuelle Version deinstallieren, um Sie auf eine neuere Version zu aktualisieren.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates anstelle der automatischen Aktualisierung von Teams bereitstellen?

Teams bietet Administratoren keine Möglichkeit zum Bereitstellen von Updates über einen beliebigen Übermittlungsmechanismus.
