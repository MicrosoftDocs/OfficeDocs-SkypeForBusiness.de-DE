---
title: Apps-Updateerfahrung in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: In diesem Artikel erfahren Sie, wie Microsoft-Apps, benutzerdefinierte Apps und Drittanbieter-Apps in Microsoft Teams aktualisiert werden und wie Administratoren dies erleichtern.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299044"
---
# <a name="update-apps-in-microsoft-teams"></a>Aktualisieren von Apps in Microsoft Teams

In den meisten Fällen wird die App automatisch für Benutzer aktualisiert, nachdem eine neue Version einer App im Teams Store verfügbar ist. Einige spezifische Änderungen in der neuen App-Version erfordern jedoch die Benutzerakzeptanz, damit die App aktualisiert werden kann. Die Benutzerakzeptanz sorgt für ein Bewusstsein für die Änderungen wie Funktionalität oder Zugriff. Wenn App-Entwickler die folgenden spezifischen Änderungen an den Microsoft Teams-Apps vornehmen, müssen Ihre Endbenutzer das App-Update genehmigen:

* Ein Bot wird hinzugefügt.
* Die `botId`-Eigenschaft oder `isNotificationOnly`-Eigenschaft eines bestehenden Bots wird geändert.
* Die Fähigkeiten `SupportsCalling`, `SupportsVideo`, und `SupportsFiles` eines Bots werden hinzugefügt.
* Eine Messaging-Erweiterung wurde hinzugefügt.
* Berechtigungen innerhalb der Autorisierung werden hinzugefügt oder geändert.
* `Id` oder `ApplicationPermissionsHash` oder beide werden innerhalb der `webApplicationInfo`geändert.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Verwandte Artikel

* [Grundlegendes zum Manifestschema für Updates, die in Apps durchgeführt werden](/microsoftteams/platform/resources/schema/manifest-schema).
