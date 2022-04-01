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
ms.openlocfilehash: a9a0eb67323874e725510342e1e6810dcc5c0b0d
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593000"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Verwalten des Zugriffs auf Teams-Apps Microsoft 365

App-Entwickler können ihre Microsoft Teams-Apps für die Arbeit in Outlook und auf Office.com sowie für die app-Arbeit in Teams. Die Endbenutzer können die verbesserten Apps auf Teams, in Microsoft Outlook und Microsoft Office.com nach der Erweiterung verwenden. Derzeit können nur die Endbenutzer in Targeted Release diese speziellen Apps in Teams, Outlook und Office.com anzeigen und verwenden. Die vorhandene Teams Administratorerfahrung gilt für den Zugriff auf diese Apps. Eine Benachrichtigung zu dieser Änderung ist im [Nachrichtencenter verfügbar](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Als Teams-Administrator können Sie es bestimmten Endbenutzern gestatten, die erweiterten Apps zu verwenden oder ihren Zugriff auf die erweiterten Apps in Teams, Outlook und auf Office.com zu verwalten. Teams Administratoren verwenden das Teams Admin Center, um den App-Zugriff zu verwalten.

Für die Verwendung in Outlook und Office.com verwendet eine erweiterte App weiterhin die in der App Teams. Die Berechtigungen [der erweiterten App wurden nicht geändert](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Im Folgenden finden Sie eine Liste der verbesserten Apps:

* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Tierho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)

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

## <a name="see-also"></a>Siehe auch

* [Microsoft Teams apps designed for Microsoft 365 coming in Preview to Outlook and Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Verständnis der Administratorrollen in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informationen Outlook-Add-Ins](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [So erweitern Entwickler Teams Apps für die übergreifend Microsoft 365](/microsoftteams/platform/m365-apps/overview)
