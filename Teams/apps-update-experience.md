---
title: App-Updateerfahrung in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: In diesem Artikel erfahren Sie, wie Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps in Microsoft Teams aktualisiert werden.
ms.openlocfilehash: cf4a062cd035feb0850a64c49a4c2363de0badce
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190311"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates für das [Microsoft Teams-Manifest](/microsoftteams/platform/resources/schema/manifest-schema), für die die Benutzerakzeptanz abgeschlossen werden muss:

* Ein Bot wurde hinzugefügt oder entfernt.
* Die Eigenschaft "botId" eines vorhandenen Bots wurde geändert.
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert.
* Die SupportsCalling-, SupportsVideo- und SupportsFiles-Funktion eines Bots wurde hinzugefügt.
* Eine Messaging-Erweiterung wurde hinzugefügt.
* Ein neuer Connector wurde hinzugefügt.
* Berechtigungen in "Autorisierung" wurden hinzugefügt oder geändert

![neue Version verfügbar.](media/manage-your-custom-apps-update1.png)

![Upgradeoption für eine App.](media/manage-your-custom-apps-update2.png)

> [!NOTE]
> Der Updateprozess gilt für alle App-Updates für Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps.
