---
title: Verwalten des Zugriffs auf Teams-Apps Microsoft 365
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
description: Verwalten Sie den Zugriff auf Teams-Apps in Microsoft 365.
ms.openlocfilehash: 3fe95852fe88f64539ffa562d64619c1300b083b
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689152"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Verwalten des Zugriffs auf Teams-Apps Microsoft 365

App-Entwickler können ihre Microsoft Teams-Apps so aktualisieren, dass sie in Outlook und auf Office.com funktionieren, sowie die App, die in Teams. Die Endbenutzer können die aktualisierten Apps auf Teams, in Microsoft Outlook und Microsoft Office.com nach dem Update verwenden. Derzeit können nur die Endbenutzer in Targeted Release diese speziellen Apps in Teams, Outlook und Office.com anzeigen und verwenden. Die vorhandene Teams Administratorerfahrung gilt für den Zugriff auf diese Apps. Eine Benachrichtigung zu dieser Änderung ist im [Nachrichtencenter verfügbar](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Als Teams-Administrator können Sie es bestimmten Endbenutzern gestatten, die aktualisierten Apps zu verwenden oder ihren Zugriff auf die aktualisierten Apps in Teams, Outlook und auf Office.com zu verwalten. Teams Administratoren verwenden das Teams Admin Center, um den App-Zugriff zu verwalten.

Für die Verwendung in Outlook und Office.com verwendet eine aktualisierte App weiterhin die in der App Teams. Die Berechtigungen [der aktualisierten App ändern sich nicht](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Mit den folgenden Methoden können Sie den Endbenutzerzugriff auf die Teams Steuern. Wenn Sie ein Administrator für Office Apps sind, wenden Sie sich an Ihren globalen Administrator oder Teams, um den App-Zugriff zu verwalten.

| Optionen zum Verwalten des Zugriffs |Portal|Globaler Administrator|Teams Administrator|
|--|---|---|--|
| Nur die Endbenutzer in Targeted Release können auf die neue App zugreifen. Verschieben Sie die Benutzer zu Standard Release. Weitere [Informationen finden Sie unter Einrichten der Standard- oder Targeted Release-Optionen.](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 Admin Center | Ja | Nein |
| Verwalten Sie den Zugriff auf die neue App für bestimmte Endbenutzer. Siehe [Hinzufügen einer benutzerdefinierten Berechtigungsrichtlinie](teams-app-permission-policies.md#create-a-custom-app-permission-policy) und [Zuweisen der benutzerdefinierten Richtlinie zu einem Benutzer](policy-assignment-overview.md). | Teams Admin Center | Ja | Ja |
| Verwalten Sie den Zugriff auf die neuen Apps für alle Endbenutzer in Ihrer Organisation. Weitere Informationen [finden Sie unter Zulassen oder Blockieren von Apps](manage-apps.md#allow-and-block-apps). | Teams Admin Center | Ja | Ja |

> [!NOTE]
> Wir empfehlen die Verwendung [der Standard Release-Option,](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) um den Endbenutzerzugriff zu verwalten. Mit den anderen Optionen wird der Endbenutzerzugriff entfernt, und er kann die vorhandene App nicht mehr in Teams.

> [!NOTE]
> Benutzer, die in Outlook und Office bereits vorhandene In-Market-Add-Ins derselben App installiert haben, verwenden diese App weiterhin. Die Add-Ins sind keine Teams und Teams den Zugriff nicht steuern können.

## <a name="see-also"></a>Mehr dazu

* [Verständnis der Administratorrollen in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informationen Outlook-Add-Ins](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [So erweitern Entwickler Teams Apps für die übergreifend Microsoft 365](/microsoftteams/platform/m365-apps/overview)
