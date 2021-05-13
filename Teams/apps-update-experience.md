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
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Apps in Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337825"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates des Manifests Microsoft Teams, <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">die</a> die Benutzerakzeptanz erfordern, um abgeschlossen zu werden:

* Ein Bot wurde hinzugefügt oder entfernt
* Die "botId"-Eigenschaft eines vorhandenen Bots wurde geändert
* Die IsNotificationOnly-Eigenschaft eines vorhandenen Bots wurde geändert
* Die Eigenschaft "supportsFiles" des Bots wurde geändert
* Eine Nachrichtenerweiterung wurde hinzugefügt oder entfernt.
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften in "webApplicationInfo" wurden geändert

![Neue Version verfügbar](media/manage-your-custom-apps-update1.png)

![Upgradeoption für eine App](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> Der Updateprozess gilt für alle App-Updates für Microsoft-Apps, benutzerdefinierte Apps und Apps von Drittanbietern. 

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Apps](manage-apps.md)