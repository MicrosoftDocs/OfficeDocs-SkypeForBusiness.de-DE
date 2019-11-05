---
title: Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Erfahren Sie mehr über das Verwalten von Richtlinien und deren Verwaltung in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81c42bbe4f6bfc9186365d43906fc9b7f31bf8d2
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968326"
---
# <a name="retention-policies-in-microsoft-teams"></a>Aufbewahrungsrichtlinien in Microsoft Teams

Teams-Unterhaltungen sind dauerhaft und werden standardmäßig für immer aufbewahrt. Mit der Einführung von Aufbewahrungsrichtlinien können Administratoren im Security #a0 Compliance Center für Teams-Chats und Kanal Nachrichtenaufbewahrungsrichtlinien (sowohl Konservierung als auch Löschung) konfigurieren. Dies hilft Organisationen, Daten für einen bestimmten Zeitraum für die Compliance (nämlich die Erhaltungs Richtlinie) zu speichern oder Daten (nämlich Löschrichtlinien) loszuwerden, wenn Sie nach einem bestimmten Zeitraum als verbindlich erachtet werden. Durch die Aufbewahrungsrichtlinien von Teams wird sichergestellt, dass Sie beim Löschen von Daten aus allen permanenten Datenspeicherorten des Teams-Diensts entfernt werden.

> [!NOTE]
> Wir unterstützen noch keine Konfiguration für die Aufbewahrung privater Kanal Nachrichten. Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.

Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams die Einstellungen und Cmdlets im Office 365 Security #a0 Compliance Center unter **Daten Governance** > -**Aufbewahrung**.

Die Aufbewahrungsrichtlinien von Teams unterstützen: 
    
- Konservierung: Verwalten von Teams-Daten für eine bestimmte Dauer und dann nichts
- Beibehalten und dann löschen: Verwalten von Teams-Daten für eine bestimmte Dauer und anschließendes Löschen
- Löschen: Löschen von Teams-Daten nach einer bestimmten Dauer

Teams-Aufbewahrungsrichtlinien unterstützen noch nicht:

- Erweiterte Aufbewahrungsrichtlinien gelten nicht für Team-Chats und Teams Kanal Nachrichtenspeicher Orte
- Dauer von weniger als 30 Tagen

Administratoren können separate Aufbewahrungsrichtlinien für private Microsoft-Chats (1:1 oder 1: viele Chats) und für Teams Kanal Nachrichten einrichten. In vielen Fällen sehen Organisationen private Chat-Daten eher als eine Haftung als Kanal Nachrichten an, die in der Regel mehr projektbezogene Unterhaltungen sind. Richten Sie diese Richtlinien im Security #a0 Compliance Center,**Aufbewahrung**von **Datenverwaltungen** > ein. Aktivieren Sie die **Channel-Nachrichten** und **Teams-Chats** von Teams, und definieren Sie dann Aufbewahrungsrichtlinien für diese Speicherorte (siehe Abbildung unten). 

Wenn Sie Channel- **Nachrichten für Teams**aktivieren, können Sie Teams angeben, für die diese Richtlinie gelten soll. Beispielsweise kann der Administrator für Teams X, Y und Z die Löschrichtlinien für ein Jahr festlegen (durch Auswahl dieser Teams einzeln) und eine 3-jährige Löschrichtlinie für die restlichen Teams anwenden. 

Sie können für **Teams-Chats** dasselbe tun, indem Sie bestimmte Benutzer auswählen und eindeutige Aufbewahrungsrichtlinien anwenden. 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Retention-Policies.png)


> [!IMPORTANT]
> In den Teams-Channel-Nachrichtenspeicher Orten und Teams-Chats werden nur die in Exchange Online-Postfächern gespeicherten Team Unterhaltungen (Benutzer-und Gruppen Postfächer) behandelt. Die Nachrichten werden aus allen relevanten Speicherorten, nämlich den Postfächern, dem Substrat und dem Chatdienst, gelöscht. 
> 
> Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams-Dateien, die in OneDrive for Business und SharePoint gespeichert sind, deren Aufbewahrungsrichtlinien.

Nach dem Entwurf werden Löschrichtlinien für Teams-Dateien über SharePoint Online und OneDrive for Business-Speicherorte konfiguriert. Daher ist es möglich, dass eine Richtlinie eine Datei löscht, auf die in einer Team-Chat-oder Kanal Nachricht verwiesen wird, bevor diese Nachrichten gelöscht werden. In diesem Fall wird die Datei weiterhin in der Nachricht "Teams" angezeigt, aber wenn Sie auf die Datei klicken, wird die Fehlermeldung "Datei nicht gefunden" angezeigt (Dies kann auch in Abwesenheit einer Richtlinie geschehen, wenn jemand eine Datei manuell aus SharePoint Online oder OneDrive for Business löscht).

Detaillierte Informationen zum Konfigurieren von Aufbewahrungsrichtlinien für Office 365 finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
