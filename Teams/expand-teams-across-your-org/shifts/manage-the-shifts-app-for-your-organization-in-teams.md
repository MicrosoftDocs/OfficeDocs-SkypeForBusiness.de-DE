---
title: Verwalten Sie die Schicht-App für Ihre Organisation
author: LanaChin
ms.author: v-lanachin
ms.reviewer: lisawu,gumariam
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erfahren Sie, wie Sie die Schichten-App in Ihrem Teams Mitarbeiter in der Frontlinie in Ihrer Organisation einrichten und verwalten.
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
ms.openlocfilehash: d474198bc644563007428ac50a85f8f839a9e1dc
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562928"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams

> [!IMPORTANT]
> Mit Wirkung zum 30. Juni 2020 wurde Microsoft StaffHub eingestellt. StaffHub-Funktionen werden in Microsoft Teams integriert. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wurde am 30. Juni 2020 für alle Benutzer eingestellt. Jedem, der versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, in der er aufgefordert wird, Teams herunterzuladen. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Übersicht über "Schichten"

Die Schichten-App in Microsoft Teams sorgt dafür, dass die Frontline-Workers verbunden und synchronisiert sind. Es wurde zuerst für das schnelle und effektive Zeitmanagement und die Kommunikation für Teams erstellt. Schichten ermöglichen Es Mitarbeitern in der Frontlinie und ihren Vorgesetzten, ihre mobilen Geräte zu verwenden, um Zeitpläne zu verwalten und in Kontakt zu bleiben.

- Vorgesetzte erstellen, aktualisieren und verwalten Schichtzeitpläne für Teams. Sie können Nachrichten an eine Person ("Der Boden ist schmutzig") oder an das gesamte Team ("Der regionale Geschäftsführer kommt in 20 Minuten") senden. Sie können auch Richtliniendokumente, Bekanntmachungen und Videos senden.
- Die Mitarbeiter sehen sich ihre bevorstehenden Schichten an, sehen, wer für den Tag noch geplant ist, fordern einen Austausch an oder bieten eine Schicht an und fordern eine Freistellung an.

Es ist wichtig zu wissen, dass Schichten Gäste zurzeit nicht unterstützen. Dies bedeutet, dass Gäste eines Teams keinen Schichtplänen hinzugefügt werden können und diese auch nicht verwenden können, wenn der Gastzugriff in Microsoft Teams aktiviert ist.

> [!Note]
> Ausführliche Informationen zu den Schichtfunktionen auf verschiedenen Plattformen finden Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Verfügbarkeit der Schichten-App

"Schichten" ist in allen Enterprise-SKUs verfügbar, die Microsoft Teams umfassen.

## <a name="location-of-shifts-data"></a>Speicherort von Daten der Schichten-App

Daten der Schichten-App werden aktuell in Azure in Rechenzentren in Nordamerika, Westeuropa und im asiatisch-pazifischen Raum gespeichert. Weitere Informationen zum Speicherort von Daten finden Sie unter [Wo befinden sich meine Daten?](http://o365datacentermap.azurewebsites.net/).

## <a name="set-up-shifts"></a>Einrichten von "Schichten"

### <a name="enable-or-disable-shifts-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" in Ihrer Organisation

"Schichten" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](../../manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie in der Liste der Apps eine der folgenden Aktionen aus:

    - Um Schichten für Ihre Organisation zu deaktivieren, suchen Sie nach der Schicht-App, wählen Sie sie aus und wählen Sie dann **Blockieren**.
    - Um Schichten für Ihre Organisation zu aktivieren, suchen Sie nach der Schicht-App, wählen Sie sie aus und wählen Sie dann **Zulassen**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" für bestimmte Benutzer in Ihrer Organisation

Wenn Sie zulassen oder blockieren möchten, dass bestimmte Benutzer in Ihrer Organisation Schichten verwenden können, stellen Sie sicher, dass Schichten für Ihre Organisation auf der Seite Apps [verwalten aktiviert](../../manage-apps.md) sind. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](../../teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Schichten an Teams

Mithilfe von App-Setup Richtlinien können Sie Microsoft Teams so anpassen, dass die Apps, die für die Benutzer in Ihrer Organisation am wichtigsten sind, hervorgehoben werden. Die in einer Richtlinie festgelegten Apps werden an die App-Leiste geheftet &mdash;das ist die seitliche Leiste bei Microsoft Teams-Desktop-Clients und am unteren Rand bei Microsoft Teams Mobile-Clients&mdash;, von wo die Benutzer schnell und einfach darauf zugreifen können.

Sie können eine benutzerdefinierte [App-Setuprichtlinie erstellen,](../../teams-app-setup-policies.md) indem Sie die Schichten-App hinzufügen und die Richtlinie dann [Ihren](../../assign-policies-users-and-groups.md) Benutzern zuweisen. Sie können auch die App-Setuprichtlinie verwenden, die in den Richtlinienpaketen "Frontline Worker" und "Frontline-Manager" enthalten ist.

Ein [Richtlinienpaket](../../manage-policy-packages.md) in Teams eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Zu den Richtlinien in den Richtlinienpaketen für Frontline-Worker und Frontline-Manager gehört eine Richtlinie für die App-Einrichtung, die die Schichten-App anheftt, sowie andere Apps, die Kommunikations- und Zusammenarbeitsaktivitäten für diese Rolle unterstützen.

Es wird empfohlen, die Richtlinienpakete für Frontline Worker und Frontline Manager zu verwenden, um sie zu vereinfachen, zu optimieren und für Konsistenz beim Verwalten von Richtlinien für Mitarbeiter an vorderer Front zu sorgen.

## <a name="search-the-audit-log-for-shifts-events"></a>Durchsuchen Sie das Überwachungsprotokoll nach Schichtereignissen

**(in der Vorschau)**

Sie können das Überwachungsprotokoll durchsuchen, um die Schichtaktivität in Ihrer Organisation anzuzeigen.  Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Anzeigen einer Liste der im Überwachungsprotokoll protokollierten [Schichtaktivitäten](../../audit-log-events.md#shifts-in-teams-activities) finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Teams](../../audit-log-events.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://protection.office.com) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="related-topics"></a>Verwandte Themen

- [Schichten-Hilfe für Mitarbeiter an vorderer Front](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](../../policy-assignment-overview.md)
