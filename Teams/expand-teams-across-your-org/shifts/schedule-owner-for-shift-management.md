---
title: Verwalten von Zeitplanbesitzern für die Schichtverwaltung
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erfahren Sie, wie Sie Schichtbesitzer für die Zeitplanverwaltung verwalten. Sie können eine Richtlinie festlegen, um die Berechtigung eines Teammitglieds auf einen Zeitplanbesitzer zu erhöhen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 702ca0fd5b392755b1966d16024d5ecf10cdacab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627537"
---
# <a name="schedule-owner-for-shift-management"></a>Zeitplanbesitzer für Schichtverwaltung

## <a name="overview"></a>Übersicht

Terminplanungsbesitzer ist ein Feature, mit dem Sie die Berechtigungen eines Teammitglieds zu einem Zeitplanbesitzer höher machen können, ohne den Mitarbeiter zum Teambesitzer zu machen. Dies bedeutet, dass der Mitarbeiter berechtigt ist, den Zeitplan des Teams zu verwalten, ohne andere Teameigenschaften wie das Aktualisieren, Bearbeiten oder Löschen von Teamkanälen ändern zu können.

Was kann ein Benutzer mit Terminplanbesitzerberechtigungen tun?

- Sie können Zeitpläne erstellen, bearbeiten und veröffentlichen, um die Schichtzuweisungen ihres Teams zu verwalten.
- Anzeigen und Genehmigen von Schichtanforderungen, einschließlich Anfragen zum Tausch von Schichten und zum Übernehmen von offenen Schichten.
- Verwalten Sie Einstellungen in Schichten, um bestimmte Features für das Team zu aktivieren.
- Zeigen Sie die Arbeitszeittabelle ihres Teams an, und ändern Sie sie, um Mitarbeiterabrechnungen zu verarbeiten.

## <a name="why-schedule-owner"></a>Warum der Besitzer des Terminplans?

Ohne das Feature "Besitzer planen" könnten die täglichen Geschäftsfunktionen unterbrochen werden. Während der Teambesitzer hilft, das Team zu führen, ist er möglicherweise nicht unbedingt die Person, die für die Tagesplanung zuständig ist. In diesem Fall wird durch die Übertragung der Verantwortlichkeit für die Zeitplanverwaltung auf ein anderes Teammitglied der tägliche Betrieb innerhalb des Teams optimiert, und die Verwirrung zwischen zwei Teammitgliedern, die über die gleichen Zugriffsrechte verfügen, wird beseitigt.

## <a name="scenario"></a>Szenario

Hier ist ein Beispiel dafür, wie Die Funktion "Besitzer planen" in Ihrer Organisation verwendet werden kann.

Sie arbeiten in einer großen Organisation, in der Abteilungsleiter Direktbericht an den Geschäftsführer des Ladengeschäfts erstellen. Der Geschäftsführer des Ladengeschäfts verfügt innerhalb Ihres Unternehmens über mehr Autorität und ist der Teambesitzer in Schichten. Abteilungsleiter hingegen werden Schichten nur einmal als Teammitglieder hinzugefügt. Zwar verfügen Ladenmanager über mehr Seniority als Abteilungsleiter, für Abteilungsmanager ist es aber sinnvoller, die Tagesplanung der Mitarbeiter ihres Teams zu übernehmen.

*Ohne Zeitplanbesitzer* müssen Abteilungsleiter genau die gleichen Berechtigungen wie der Teambesitzer erhalten. Kürzlich haben Abteilungsleiter Informationen verschieben und den Namen von Kanälen geändert, was zu Komplikationen bei der Arbeit des Ladenleiters führte. Der Geschäftsführer des Ladengeschäfts möchte, dass die Abteilungsleiter in der Lage sind, ihre Zeitpläne zu organisieren, möchte aber nicht, dass sie weitere Änderungen im Team außerhalb von Schichten möglich machen.

*Bei der Berechtigung*"Terminplanungsbesitzer" können abteilungsmanagern Planungsberechtigungen ohne weitere Berechtigungen des Teambesitzers gegeben werden.

## <a name="manage-schedule-ownership"></a>Verwalten des Besitzers des Zeitplans

Als Administrator steuern Sie mithilfe von Richtlinien die Besitzrechte für die Zeitplanverwaltung in Ihrer Organisation. Sie verwalten diese Richtlinien mithilfe der folgenden PowerShell-Cmdlets:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Beispiel 1

Hier erstellen wir eine neue Richtlinie mit dem Namen ScheduleOwnerPolicy, bei der das Feature "Terminplanbesitzer" aktiviert ist.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Beispiel 2

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "ScheduleOwnerPolicy" eine Richtlinie namens "remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der "Schichten"-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Verwalten Sie den schichtbasierten Zugriff für Mitarbeiter an vorder frontline in Teams](manage-shift-based-access-flw.md) 
