---
title: App-Update-Erfahrung in Microsoft Teams
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
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958040"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die neue Version automatisch für Benutzer angezeigt, nachdem App-Entwickler ein App-Update veröffentlicht haben. Es gibt jedoch einige Updates für das [Microsoft Teams-Manifest](/microsoftteams/platform/resources/schema/manifest-schema) , für die die Benutzerakzeptanz abgeschlossen werden muss:

* Ein Bot wurde hinzugefügt oder entfernt.
* Die Eigenschaft "botId" eines vorhandenen Bots wurde geändert.
* Die Eigenschaft "isNotificationOnly" eines vorhandenen Bots wurde geändert.
* Die SupportsCalling-, SupportsVideo- und SupportsFiles-Funktion eines Bots wurde hinzugefügt.
* Eine Messaging-Erweiterung wurde hinzugefügt.
* Ein neuer Connector wurde hinzugefügt.
* Berechtigungen in "Authorization" wurden hinzugefügt oder geändert.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Neue Version verfügbar." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgradeoption für eine App." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Der Updateprozess gilt für alle App-Updates für Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps.
