---
title: App-Updateerfahrung in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
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
description: Hier erfahren Sie, wie Sie Apps in Microsoft Teams.
ms.openlocfilehash: 0755c505a25d4c858afd104331d193edd8b2b27c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726204"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates des Manifests Microsoft Teams, <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">die</a> die Benutzerakzeptanz erfordern, um abgeschlossen zu werden:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die IsNotificationOnly-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Funktionen SupportsCalling, SupportsVideo und SupportsFiles eines Bots wurden hinzugefügt.
* Eine Nachrichtenerweiterung wurde hinzugefügt.
* Ein neuer Connector wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" wurden geändert

![neue Version verfügbar.](media/manage-your-custom-apps-update1.png)

![Upgradeoption für eine App.](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> Der Updateprozess gilt für alle App-Updates für Microsoft-Apps, benutzerdefinierte Apps und Apps von Drittanbietern. 

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Apps](manage-apps.md)
