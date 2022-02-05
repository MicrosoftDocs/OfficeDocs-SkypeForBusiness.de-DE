---
title: App-Updateerfahrung in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: 'Hier erfahren Sie, wie Sie Apps in Microsoft Teams.'
---

# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates des Manifests Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">, die die</a> Benutzerakzeptanz erfordern, um abgeschlossen zu werden:

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
