---
title: Apps-Updateerfahrung in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
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
ms.openlocfilehash: 3d0264a31214b51e751d52ffe90411f227e46656
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837535"
---
# <a name="teams-app-updates-and-admin-role"></a>Teams-App-Updates und Administratorrolle

Teams-Administratoren können ihren Endbenutzern helfen, die neueste Version der Apps zu erhalten. Dazu führen sie eine oder beide der folgenden Aufgaben aus:

* [Aktualisieren Sie Apps von Drittanbietern](#updates-to-third-party-apps) , die im Teams Store verfügbar sind, wenn vom App-Entwickler oder -Anbieter eine neue Version bereitgestellt wird.
* [Aktualisieren Sie benutzerdefinierte Apps](#updates-to-custom-apps) , die nur in Ihrer Organisation verfügbar sind, wenn Ihr Entwickler eine neue Version übermittelt.

## <a name="updates-to-third-party-apps"></a>Aktualisierungen zu Drittanbieter-Apps

Damit Benutzer eine App installieren und verwenden können, müssen sie der App Berechtigungen erteilen, um auf die erforderlichen Dienste und Informationen zugreifen zu können. Wenn eine neue Version einer installierten App im Teams Store verfügbar ist, wird die App in den meisten Fällen automatisch für alle Benutzer aktualisiert. Einige spezifische Änderungen in der neuen Version der App erfordern jedoch erneut eine Benutzerberechtigung. Durch diese wiederholte Benutzerakzeptanz wird das Bewusstsein für die Änderungen wie Funktionalität oder Zugriff auf persönliche Informationen sichergestellt. Teams-Administratoren können [Berechtigungen für eine App im Namen der Benutzer bereitstellen](app-permissions-admin-center.md).

Wenn App-Entwickler eine oder mehrere der folgenden Änderungen an ihren Apps vornehmen, müssen die Endbenutzer das Update der App genehmigen.

* Hinzufügen oder Entfernen eines Bots. Ändern Sie die ID des Bots mithilfe der `botId` Eigenschaft.
* Ändern Sie die `isNotificationOnly` Eigenschaft eines vorhandenen Bots, der die Benachrichtigungen des Bots ändern kann.
* Ändern Sie `SupportsCalling`die `SupportsVideo`Eigenschaften eines vorhandenen Bots, `SupportsFiles` um Funktionen zum Aufrufen, Wiedergeben von Videos und Hochladen oder Herunterladen von Dateien hinzuzufügen.
* Hinzufügen oder Entfernen von Berechtigungen in der Autorisierung.
* Hinzufügen oder Entfernen einer Messaging-Erweiterung, Hinzufügen einer Gruppenregisterkarte, Hinzufügen eines Connectors oder Hinzufügen eines Kanals.
* Ändern Sie die Parameter in der [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) Manifestdatei.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Aktualisierungen für benutzerdefinierte Apps

Benutzerdefinierte Apps, die in Ihrer Organisation erstellt und bereitgestellt werden, stehen den Benutzern in Ihrem Mandanten oder Ihrer Organisation zur Verfügung. Der Teams-Administrator aktualisiert die benutzerdefinierten Apps auf neue Versionen, wie sie von Entwicklern innerhalb der Organisation bereitgestellt werden. Weitere Informationen finden Sie unter [Verwalten benutzerdefinierter Apps durch Administratoren](custom-app-overview.md).

## <a name="related-article"></a>Verwandter Artikel

* [Grundlegendes zum Manifestschema für Updates, die in Apps durchgeführt werden](/microsoftteams/platform/resources/schema/manifest-schema).
* [Informieren Sie sich über die benutzerdefinierte App-Verwaltung](custom-app-overview.md).
