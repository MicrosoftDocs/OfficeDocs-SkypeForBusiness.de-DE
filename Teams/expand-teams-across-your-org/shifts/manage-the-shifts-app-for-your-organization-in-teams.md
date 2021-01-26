---
title: Verwalten der App "Schichten" für Ihre Organisation
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erfahren Sie, wie Sie die App Schichten in Teams für Frontline workers in Ihrer Organisation einrichten und verwalten.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909089"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams

> [!IMPORTANT]
> Microsoft StaffHub wurde am 30. Juni 2020 eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub hat die Arbeit für alle Benutzer am 30. Juni 2020 beendet. Jeder, der staffHub zu öffnen versucht, wird in einer Meldung zum Herunterladen von Teams angezeigt. Weitere Informationen finden Sie unter [Microsoft StaffHub wurde eingestellt.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Übersicht über "Schichten"

Die App "Schichten" in Microsoft Teams sorgt dafür, dass Mitarbeiter an der Frontline verbunden und synchronisiert sind. Es wurde zuerst für das schnelle und effektive Zeitmanagement und die Kommunikation für Teams erstellt. Schichten ermöglicht es Frontline-Mitarbeitern und ihren Vorgesetzten, ihre mobilen Geräte zu verwenden, um Zeitpläne zu verwalten und in Kontakt zu bleiben.

- Vorgesetzte erstellen, aktualisieren und verwalten Schichtzeitpläne für Teams. Sie können Nachrichten an eine Person ("Der Boden ist schmutzig") oder an das gesamte Team ("Der regionale Geschäftsführer kommt in 20 Minuten") senden. Sie können auch Richtliniendokumente, Bekanntmachungen und Videos senden. 
- Mitarbeiter sehen ihre anstehenden Schichten, sehen, wer sonst noch für den Tag geplant ist, fordern einen Tausch an oder bieten eine Schicht an, und fordern Sie Freizeit an. 

Es ist wichtig zu wissen, dass "Schichten" zurzeit keine Gastbenutzer unterstützt. Dies bedeutet, dass Gäste eines Teams keinen Schichtplänen hinzugefügt werden können und diese auch nicht verwenden können, wenn der Gastzugriff in Microsoft Teams aktiviert ist. 

> [!Note]
> Details zu den Funktionen von Schichten auf verschiedenen Plattformen finden Sie unter ["Teams-Features nach Plattform".](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Verfügbarkeit der Schichten-App

"Schichten" ist in allen Enterprise-SKUs verfügbar, die Microsoft Teams umfassen.

## <a name="location-of-shifts-data"></a>Speicherort von Daten der Schichten-App

Daten der Schichten-App werden aktuell in Azure in Rechenzentren in Nordamerika, Westeuropa und im asiatisch-pazifischen Raum gespeichert. Weitere Informationen zum Speicherort von Daten finden Sie unter [Wo befinden sich meine Daten?](http://o365datacentermap.azurewebsites.net/).

## <a name="set-up-shifts"></a>Einrichten von "Schichten"

### <a name="enable-or-disable-shifts-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" in Ihrer Organisation

"Schichten" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](../../manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Gehen Sie in der Liste der Apps wie folgt vor:

    - Um Schichten für Ihre Organisation zu deaktivieren, suchen Sie nach der App "Schichten", wählen Sie sie aus, und wählen Sie dann **"Blockieren" aus.**
    - Um Schichten für Ihre Organisation zu aktivieren, suchen Sie nach der App "Schichten", wählen Sie sie aus, und wählen Sie dann **"Zulassen" aus.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" für bestimmte Benutzer in Ihrer Organisation

Wenn Sie die Nutzung von "Schichten" für bestimmte Benutzer in Ihrer Organisation zulassen oder blockieren möchten, stellen Sie sicher, dass die App für Ihre Organisation auf der Seite [Apps verwalten](../../manage-apps.md) aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese den betreffenden Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](../../teams-app-permission-policies.md).

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Verwenden der Setuprichtlinie der FrontlineWorker-App, um Schichten an Teams anheften

Mithilfe von App-Setup Richtlinien können Sie Microsoft Teams so anpassen, dass die Apps, die für die Benutzer in Ihrer Organisation am wichtigsten sind, hervorgehoben werden. Die in einer Richtlinie festgelegten Apps werden an die App-Leiste geheftet &mdash;das ist die seitliche Leiste bei Microsoft Teams-Desktop-Clients und am unteren Rand bei Microsoft Teams Mobile-Clients&mdash;, von wo die Benutzer schnell und einfach darauf zugreifen können.
 
Teams enthält eine integrierte Setuprichtlinie für die FrontlineWorker-App, die Sie Frontline-Mitarbeitern in Ihrer Organisation zuweisen können. Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe. 

Wenn Sie die Richtlinie "FrontlineWorker" anzeigen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien für **Teams-Apps.**  >  

![Screenshot der Setuprichtlinie für die FrontlineWorker-App](../../media/firstline-worker-app-setup-policy.png "Screenshot der Setuprichtlinie für die FrontlineWorker-App im Microsoft Teams Admin Center")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Zuweisen der Setuprichtlinie für die FrontlineWorker-App zu Benutzern

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Durchsuchen des Überwachungsprotokolls nach Schichtenereignissen

**(in der Vorschau)**

Sie können das Überwachungsprotokoll durchsuchen, um die Schichtaktivität in Ihrer Organisation anzeigen.  Weitere Informationen zum Durchsuchen des [Überwachungsprotokolls](../../audit-log-events.md#shifts-in-teams-activities) und zum Sehen einer Liste der Im Überwachungsprotokoll protokollierten Schichtaktivitäten finden Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen [in Teams.](../../audit-log-events.md)

Bevor Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center aktivieren.](https://protection.office.com) Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren [der Überwachungsprotokollsuche.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Beachten Sie, dass Überwachungsdaten nur ab dem Punkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="related-topics"></a>Verwandte Themen

- [Hilfe zu Schichten für Mitarbeiter an vorderer Front](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](../../assign-policies.md)
