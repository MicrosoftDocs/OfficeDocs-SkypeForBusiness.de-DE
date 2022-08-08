---
title: Apps-Updateerfahrung in Microsoft Teams
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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: In diesem Artikel erfahren Sie, wie Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps in Microsoft Teams aktualisiert werden.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272060"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates für das [Microsoft Teams-Manifest](/microsoftteams/platform/resources/schema/manifest-schema), für welche die Zustimmung des Benutzers erforderlich ist:

* Ein Bot wurde hinzugefügt oder entfernt.
* Die „botId“-Eigenschaft eines vorhandenen Bots wurde verändert.
* Die „isNotificationOnly“-Eigenschaft eines vorhandenen Bots wurde verändert.
* Die SupportsCalling-, SupportsVideo- und SupportsFiles-Funktion eines Bots wurde hinzugefügt.
* Eine Messaging-Erweiterung wurde hinzugefügt.
* Ein neuer Connector wurde hinzugefügt.
* Berechtigungen innerhalb von „Autorisierung“ wurden hinzugefügt oder geändert.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Neue Version verfügbar." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade-Option für eine App." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Der Updatevorgang gilt für alle App-Updates für Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps.
