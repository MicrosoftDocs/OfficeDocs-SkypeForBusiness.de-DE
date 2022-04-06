---
title: Verwalten des Zugriffs auf Teams Apps in Microsoft 365
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
description: Verwalten des Zugriffs auf Teams Apps in Microsoft 365.
ms.openlocfilehash: 336c550c4fdf506898d6471cb618652fada95a4f
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "64648984"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Verwalten des Zugriffs auf Teams Apps in Microsoft 365

App-Entwickler können ihre Microsoft Teams-Apps so verbessern, dass sie in Outlook und auf Office.com funktionieren, zusätzlich zur App, die in Teams funktioniert. Die Endbenutzer können die erweiterten Apps auf Teams, in Microsoft Outlook und Microsoft Office.com nach der Verbesserung verwenden. Derzeit können nur die Endbenutzer in targeted release diese spezifischen Apps in Teams, Outlook und Office.com anzeigen und verwenden. Die vorhandene Teams Administratorerfahrung gilt für die Steuerung des Zugriffs auf diese Apps. Eine Benachrichtigung über diese Änderung ist im [Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280) verfügbar. Als Teams-Administrator können Sie bestimmten Endbenutzern erlauben, die erweiterten Apps zu verwenden oder ihren Zugriff auf die erweiterten Apps in Teams, in Outlook und auf Office.com zu verwalten. Teams Administratoren verwenden das Teams Admin Center, um den App-Zugriff zu verwalten.

Für die Verwendung in Outlook und Office.com verwendet eine erweiterte App weiterhin die vorhandenen Berechtigungen, die in Teams erteilt wurden. Die [Berechtigungen der erweiterten App ändern sich nicht](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Es folgt eine Liste der erweiterten Apps:

* [Wandbild](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube?source=app-details-dialog)

Sie können den Endbenutzerzugriff auf die Teams Apps mithilfe der folgenden Methoden steuern. Wenn Sie ein Office Apps-Administrator sind, wenden Sie sich an Ihren globalen Administrator oder Teams Administrator, um den App-Zugriff zu verwalten.

| Optionen zum Verwalten des Zugriffs |Portal|Globaler Administrator|Teams-Administrator|
|--|---|---|--|
| Nur die Endbenutzer in targeted release können auf die neue App zugreifen. Verschieben sie die Benutzer in die Standardversion. Siehe ["Einrichten der Standard- oder Targeted Release-Optionen"](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 Admin Center | Ja | Nein |
| Verwalten des Zugriffs auf die neue App für bestimmte Endbenutzer. Siehe [Hinzufügen einer benutzerdefinierten Berechtigungsrichtlinie](teams-app-permission-policies.md#create-a-custom-app-permission-policy) und [Zuweisen der benutzerdefinierten Richtlinie zu einem Benutzer](policy-assignment-overview.md). | Teams Admin Center | Ja | Ja |
| Verwalten Sie den Zugriff auf die neuen Apps für alle Endbenutzer in Ihrer Organisation. Siehe ["Apps zulassen oder blockieren](manage-apps.md#allow-and-block-apps)". | Teams Admin Center | Ja | Ja |

> [!NOTE]
> Es wird empfohlen [, die Standardversionsoption](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) zum Verwalten des Endbenutzerzugriffs zu verwenden. Die anderen Optionen entfernen den Endbenutzerzugriff, und sie können die vorhandene App nicht mehr in Teams verwenden.

> [!NOTE]
> Benutzer, die ein vorhandenes Markt-Add-In derselben App in Outlook und Office installiert haben, verwenden diese App weiterhin. Die Add-Ins sind keine Teams Apps, und Teams Administratoren können den Zugriff nicht steuern.

## <a name="see-also"></a>Siehe auch

* [Microsoft Teams Apps, die für Microsoft 365 in der Vorschau auf Outlook und Office.com entwickelt wurden](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Grundlegendes zu Administratorrollen in Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Informationen zu Outlook-Add-Ins](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [So erweitern Entwickler Teams Apps so, dass sie Microsoft 365](/microsoftteams/platform/m365-apps/overview)