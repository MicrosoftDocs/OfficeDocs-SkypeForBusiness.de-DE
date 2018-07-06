---
title: Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205078"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?

**Obwohl Sonderzeichen für das Erstellen von Teams Richtlinien mit PowerShell verwendet werden können, werden Sie bei der Verwaltung diese Richtlinien eingeschränkt werden.  Daher wird dringend empfohlen, dass die Richtliniennamen keine Sonderzeichen enthalten.**

Richtliniennamen, die Sie beim Erstellen von PowerShell für Besprechungen und Chatten in Teams haben Sonderzeichen wie @, #, $. Jedoch, wenn Sie die Richtlinie in der Microsoft-Teams und Skype für die Business-Verwaltungskonsole bearbeiten möchte, Sie kann nicht zu werden. Sie müssen die Windows PowerShell und die richtige Richtlinie-Cmdlet verwenden, um Änderungen vorzunehmen.

Wenn Sie ein Gruppenrichtlinienobjekt mit Sonderzeichen haben und Sie Sonderzeichen entfernen, um die Richtlinie für die Business-Verwaltungskonsole in der Microsoft-Teams und Skype besser verwalten möchten, müssen Sie mit dem folgenden Verfahren. 

Hinweis: Das Verfahren formuliert wird hier als Beispiel eine Messaging-Richtlinie.  Das gleiche Verfahren würde von Subsituting die relevanten Cmdlets für eine andere Richtlinie (beispielsweise in Besprechungen) verwendet werden. 

1) rufen Sie Get-CSMessagingPolicy-Identity < Old_policy_name > und erfasst die Ausgabe der Richtlinie.
2) rufen Sie Set-CSMessagingPolicy-Identity < New_policy_name > zum Erstellen einer neuen Richtlinie mit der Konfiguration als die ursprüngliche Richtlinie, aber ohne Sonderzeichen im Namen.
3.) aufrufen Delete-CSMessagingPolicy-Identity < Old_policy_name >, um die Richtlinie zu löschen.  Wenn dieser Befehl erfolgreich ist, fertig sind, und Sie können Sie die neue Richtlinie mithilfe von PowerShell oder der Microsoft-Teams und Skype für Business Administrationscenter Benutzer zuweisen beginnen.
4.) Wenn der obige Befehl nicht erfolgreich ist, ist es, weil ein Benutzer die alte Richtlinie zugewiesen wurde.  Aufheben der Zuweisung von Run-Cmdlet zum Aufheben der Zuweisung der Richtlinie zu Benutzer, neue Richtlinie zuweisen und dann Dwlete erneut ausführen.


