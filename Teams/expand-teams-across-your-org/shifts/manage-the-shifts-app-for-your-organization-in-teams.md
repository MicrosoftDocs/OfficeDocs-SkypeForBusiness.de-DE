---
title: Verwalten Sie die Schicht-App für Ihre Organisation
author: LanaChin
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
- Microsoft Cloud for Retail
description: Erfahren Sie, wie Sie die Schichten-App in Teams für Mitarbeiter in Service und Produktion in Ihrer Organisation einrichten und verwalten.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97e90a3a6e97bd2637d63cf3ee0d0bceb57dc15
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819410"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams

## <a name="overview-of-shifts"></a>Übersicht über "Schichten"

Die Schichten-App in Microsoft Teams sorgt für die Verbindung und Synchronisierung von Mitarbeitern in Service und Produktion. Es wurde zuerst für schnelles und effektives Zeitmanagement und Kommunikation für Teams entwickelt. Schichten ermöglichen Mitarbeitern in Service und Produktion die Verwendung ihrer mobilen Geräte, um Zeitpläne zu verwalten und in Kontakt zu bleiben.

- Vorgesetzte erstellen, aktualisieren und verwalten Schichtzeitpläne für Teams. Sie können Nachrichten an eine Person ("Der Boden ist schmutzig") oder an das gesamte Team ("Der regionale Geschäftsführer kommt in 20 Minuten") senden. Sie können auch Richtliniendokumente, Bekanntmachungen und Videos senden.
- Die Mitarbeiter sehen sich ihre bevorstehenden Schichten an, sehen, wer für den Tag noch geplant ist, fordern einen Austausch an oder bieten eine Schicht an und fordern eine Freistellung an.

Es ist wichtig zu wissen, dass Schichten derzeit keine Gäste unterstützen. Dies bedeutet, dass Gäste eines Teams keinen Schichtplänen hinzugefügt werden können und diese auch nicht verwenden können, wenn der Gastzugriff in Microsoft Teams aktiviert ist.

> [!Note]
> Ausführliche Informationen zu den Schichtfunktionen auf verschiedenen Plattformen finden Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Verfügbarkeit der Schichten-App

"Schichten" ist in allen Enterprise-SKUs verfügbar, die Microsoft Teams umfassen.

> [!NOTE]
> Schichten sind in GCC-Umgebungen (Government Community Cloud), aber nicht in GCC High- oder DoD-Umgebungen verfügbar.

## <a name="location-of-shifts-data"></a>Speicherort von Daten der Schichten-App

Schichtdaten werden derzeit in Azure in Rechenzentren im asiatisch-pazifischen Raum (APAC), der Europäischen Union (EU) und Nordamerika gespeichert. Weitere Informationen zum Speicherort von Daten finden Sie unter [Wo befinden sich meine Daten?](http://o365datacentermap.azurewebsites.net/).

Weitere Informationen zu Schichtdaten, einschließlich Speicherung, Aufbewahrung, Abruf und Verschlüsselung von Schichtdaten, finden Sie unter Häufig gestellte [Fragen zu Schichtdaten](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Einrichten von "Schichten"

### <a name="enable-or-disable-shifts-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" in Ihrer Organisation

"Schichten" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](../../manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie in der Liste der Apps nach der Schichten-App, wählen Sie sie aus, und wechseln Sie dann auf " **Status** " auf " **Blockiert** " oder " **Zulässig**".

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Schichten" für bestimmte Benutzer in Ihrer Organisation

Um bestimmten Benutzern in Ihrer Organisation die Verwendung von Schichten zu ermöglichen oder zu blockieren, stellen Sie sicher, dass "Schichten" für Ihre Organisation auf der Seite ["Apps verwalten"](../../manage-apps.md) aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](../../teams-app-permission-policies.md).

### <a name="pin-shifts-to-teams"></a>Anheften von Schichten an Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>Verwenden der benutzerdefinierten Frontline-App zum Anheften von Schichten und anderen Apps an Teams

Die maßgeschneiderte Frontline-App-Erfahrung in Teams heftet die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) verfügen. Angeheftete Apps umfassen Schichten, Walkie-Talkie, Aufgaben und Genehmigungen. Standardmäßig ist dieses Feature aktiviert, sodass Ihre Mitarbeiter in Service und Produktion eine out-of-the-box-Erfahrung erhalten, die auf ihre Anforderungen zugeschnitten ist.

Die Apps sind an die App-Leiste angeheftet – die Leiste auf der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients, auf die Benutzer schnell und einfach zugreifen können.

Weitere Informationen, einschließlich der Funktionsweise der Umgebung mit von Ihnen festgelegten App-Richtlinien, finden Sie unter ["Anpassen von Teams-Apps für Mitarbeiter in Service und Produktion](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)".  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Schichten an Teams

Mithilfe von App-Setuprichtlinien können Sie Teams so anpassen, dass die Apps angeheftet werden, die für Ihre Benutzer am wichtigsten sind.

Sie können eine [benutzerdefinierte App-Setuprichtlinie](../../teams-app-setup-policies.md) erstellen, indem Sie die Schichten-App hinzufügen und [die Richtlinie](../../assign-policies-users-and-groups.md) dann Ihren Benutzern zuweisen. Sie können auch die App-Setuprichtlinie verwenden, die Teil der Richtlinienpakete "Mitarbeiter in Service und Produktion" ist.

Ein [Richtlinienpaket](../../manage-policy-packages.md) in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern mit ähnlichen Rollen in Ihrer Organisation zuweisen können. Der Richtliniensatz in den Richtlinienpaketen "Frontline Worker" und "Frontline Manager" enthält eine App-Setuprichtlinie, die die Schichten-App und andere Apps anheftet, die Kommunikations- und Zusammenarbeitsaktivitäten für diese Rolle unterstützen.

Es wird empfohlen, die Richtlinienpakete "Mitarbeiter in Service und Produktion" zu verwenden, da sie die Verwaltung von Richtlinien für Ihre Mitarbeiter in Service und Produktion vereinfachen, rationalisieren und für Konsistenz sorgen.

## <a name="search-the-audit-log-for-shifts-events"></a>Durchsuchen Sie das Überwachungsprotokoll nach Schichtereignissen

**(In der Vorschau)**

Sie können das Überwachungsprotokoll durchsuchen, um die Schichtaktivität in Ihrer Organisation anzuzeigen.  Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Anzeigen einer Liste der im Überwachungsprotokoll protokollierten [Schichtaktivitäten](../../audit-log-events.md#shifts-in-teams-activities) finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Teams](../../audit-log-events.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://protection.office.com) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="related-articles"></a>Verwandte Artikel

- [Schichten für Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Häufig gestellte Fragen zu Schichten von Daten](shifts-data-faq.md)
- [Schichtenverbinder](/microsoft-365/frontline/shifts-connectors)
- [Schichthilfe für Mitarbeiter in Service und Produktion](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](../../policy-assignment-overview.md)
