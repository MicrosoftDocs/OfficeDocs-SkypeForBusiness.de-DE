---
title: Aktualisierungsvorgang Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Hier erfahren Sie, wie der Teams Desktopclient aktualisiert wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829096"
---
# <a name="teams-update-process"></a>Aktualisierungsvorgang Teams

Die Teams Web App wird wöchentlich aktualisiert.

Teams Desktopclient Updates sind zwei Wochen nach strengen internen Tests und Validierung über unsere Technologie Annahme Program (TAP) zur Verfügung. Dies erfolgt in der Regel an einem Dienstag. Wenn ein wichtiges Update erforderlich ist, werden Teams dieser Zeitplan zu umgehen und das Update freigeben, sobald sie verfügbar ist.

Der Desktopclient aktualisiert sich automatisch aus. Teams überprüft, ob alle paar Stunden im Hintergrund aktualisiert, heruntergeladen und dann wartet darauf, dass der Computer im Leerlauf sein, bevor das Update automatisch installiert.

Benutzer können auch manuell Updates herunterladen, indem Sie die **nach Updates suchen** im **Profil** Dropdown-Menü oben rechts von der app. Wenn ein Update verfügbar ist, wird es heruntergeladen und im Hintergrund installiert, wenn der Computer inaktiv ist.

Benutzer müssen für Updates heruntergeladen werden angemeldet sein.

## <a name="what-about-updates-to-office-365-proplus"></a>Was geschieht mit Updates für Office 365 ProPlus?

Teams wird standardmäßig mit neuen Installationen von Office 365 ProPlus installiert, wie beschrieben in [Microsoft-Teams mit Office 365 ProPlus bereitstellen](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams folgt eine eigene Aktualisierungsprozess wie oben beschrieben, und nicht der Aktualisierungsprozess für die anderen Büros-apps, wie Word und Excel.

## <a name="what-about-updates-to-teams-on-vdi"></a>Was geschieht mit Updates Teams VDI?

Teams Clients auf Virtual Desktop Infrastructure (VDI) werden nicht die Möglichkeit, die nicht - VDI-Teams Clients sind, automatisch aktualisiert. Sie müssen das Bild VM aktualisieren, indem Sie eine neue MSI-Datei installieren, gemäß den Anweisungen zum [Installieren von Teams auf VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Sie müssen die aktuelle Version auf eine neuere Version aktualisieren deinstallieren.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Bereitstellen von Updates anstelle von Teams Automatisches Aktualisieren?

Teams wird kein ermöglicht Administratoren die Möglichkeit zum Bereitstellen von Updates durch jeder Mechanismus.
