---
title: Nachrichtendelegierung
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Ein Benutzer kann einen anderen Benutzer explizit als Stellvertretung in seiner Statusmeldung einrichten.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570358"
---
# <a name="message-delegation"></a>Nachrichtendelegierung

Ein Benutzer kann seinen Status bereits explizit auf "Abwesend" oder "nicht stören" festlegen und benutzerdefinierten Text bereitstellen. Das Feature Nachrichten Delegierung funktioniert wie folgt:

1. Ein Benutzer @username einen anderen Benutzer in einem Teil einer Text Statusnachricht erwähnt, was darauf hindeutet, dass Personen, die Sie kontaktieren möchten, sich stattdessen an den @username genannten Nutzer wenden können.
2. Die Person, die als Stellvertretung zugewiesen wurde, wird benachrichtigt, dass Sie als Stellvertretung nominiert wurde.
3. Eine Person, die versucht, sich mit dem ersten Benutzer in Verbindung zu setzen, kann dann mit dem Mauszeiger auf den nominierten Stellvertreter zeigen  

Hierbei handelt es sich um einen vom Benutzer initiierten Prozess im Client, und es ist keine Einbindung des Administrators erforderlich, um das Feature zu aktivieren. 

## <a name="delegation-use-scenario-in-healthcare"></a>Szenario für die Delegierungs Nutzung in Healthcare

*Verwendungsbeispiel ohne Festlegen von Delegaten:*  Dr. Franco Piccio ist in der Radiologie-Abteilung auf Abruf. Er erhält einen dringenden persönlichen Anruf und muss für die nächsten paar Stunden fortfahren. Er bittet einen seiner Kollegen in der Radiologie-Abteilung, Dr. Lena Ehrle, ihn zu bedecken, während er verschwunden ist. Er händigt seinen Pager an Dr. Ehrle aus, der auf dringende Nachrichten und Pings auf den Pager wartet und Ihnen im Namen von Dr. Piccio zusätzlich zu ihren derzeitigen Aufgaben antwortet. Andere Personen im Team erkennen möglicherweise nicht, dass die informelle Delegation stattgefunden hat, und Verwirrung erfolgt mit der Fürsorge des Patienten.

*Verwendungsbeispiel mit Stellvertretungen:* Dr. Franco Piccio ist in der Radiologie-Abteilung auf Abruf. Er erhält einen dringenden persönlichen Anruf und muss für die nächsten paar Stunden fortfahren. Er fragt einen seiner Kollegen in der Radiologie-Abteilung, Dr. Lena Ehrle, um ihn zu bedecken, während er Weg ist. Er ändert seine benutzerdefinierte Statusnachricht, um etwas ähnliches wie "Ich bin für die nächsten Stunden nicht verfügbar" zu sagen. Bitte wenden Sie sich für Notfälle an @DrEhrle. "  Andere im Team erkennen, dass die Delegation beim Versuch, Dr. Piccio zu kontaktieren, passiert ist, damit Sie jetzt wissen, dass Sie in der Zwischenzeit mit Dr. Ehrle Kontakt aufnehmen möchten. Bei der Behandlung durch den Patienten entsteht kaum Verwirrung.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Auswirkungen der Koexistenzmodus auf den Benutzerstatus im Team-Client

Administratoren sollten beachten, dass Statushinweise und das Verhalten der Delegierungs Erwähnung teilweise vom Koexistenzmodus des Benutzers abhängig sind. Diese Matrix zeigt die folgenden Möglichkeiten:

|Koexistenzmodus | Erwartetes Verhalten|
|---|---|
|TeamsOnly |Benutzer können eine Notiz nur von Teams aus einrichten. <br> Die Notizen des Benutzers für Teams sind in Teams #a0 SFB sichtbar. |
|Inseln | Die Notiz des Benutzers wird in Teams, die nur in Teams sichtbar sind, festgesetzt. <br> Die Notizen des Benutzers, die in SFB festgesetzt sind, werden nur in SFB angezeigt |
|SFB *-Modi | Benutzer können eine Notiz nur in SFB einrichten. <br> Die SFB-Notiz des Benutzers ist in den SFB-#a0 Teams sichtbar.  |
|||

Ein Benutzer kann in Teams nur dann eine Notiz setzen, wenn sein Modus TeamsOnly oder Islands ist.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Anzeigen von Notizen, die in Skype for Business festgesetzt sind
  
Es gibt keinen visuellen Hinweis darauf, dass eine Notiz in Skype for Business festgesetzt wurde.

Skype for Business erzwingt keine Zeichenbeschränkung für Status Notizen. In Microsoft Teams werden nur die ersten 280-Zeichen einer Notizen Gruppe in Skype for Business angezeigt. Eine Ellipse (...) am Ende einer Notiz zeigt die Kürzung an.
  
Skype for Business unterstützt keine Ablaufzeiten für Notizen.

Die Migration von Notizen von Skype for Business zu Teams wird nicht unterstützt, wenn ein Benutzer auf den TeamsOnly-Modus aktualisiert wird.

## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](../../coexistence-chat-calls-presence.md)
