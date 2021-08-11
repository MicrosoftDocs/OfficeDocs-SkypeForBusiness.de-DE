---
title: Nachrichtendelegierung
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Erfahren Sie, wie ein Benutzer mit Status „Abwesend“ oder „Nicht stören“ einen anderen Benutzer in seiner Statusmeldung explizit als Stellvertretung festlegen kann.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 967ed83f89d991ad001dbac9001d4d20b412efec80f0edb5bf4caca77e487a87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276530"
---
# <a name="message-delegation"></a>Nachrichtendelegierung

Ein Benutzer kann seinen Status bereits explizit auf „Abwesend“ oder „Nicht stören“ setzen und benutzerdefinierten Text bereitstellen. Das Feature für die Nachrichtendelegierung funktioniert wie folgt:

1. Ein Benutzer @Benutzername erwähnt einen anderen Benutzer als Teil der Textstatusmeldung, und schlägt vor, dass Personen, die Kontakt mit ihm (dem ersten Benutzer) aufnehmen möchten, sich stattdessen an den im @Benutzernamen erwähnten Benutzer wenden, solange er (der erste Benutzer) nicht verfügbar ist.
2. Die Person, die als Stellvertretung zugewiesen wurde, wird benachrichtigt, dass Sie von einer delegierenden Person nominiert wurden.
3. Jemand, der versucht, den ersten Benutzer zu kontaktieren, kann dann mit der Maus über den nominierten Stellvertreter fahren und diesem einfach eine Nachricht senden.  

Dies ist ein vom Benutzer initiierter Prozess im Client, und es ist keine Administratorbeteiligung erforderlich, um die Funktion zu aktivieren. 

## <a name="delegation-use-scenario-in-healthcare"></a>Verwendungsszenario für Stellvertretung im Gesundheitswesen

*Verwendungsbeispiel ohne die Stellvertretung festzulegen:*  Dr. Franco Piccio hat in der Radiologie Bereitschaftsdienst. Er erhält einen dringenden persönlichen Anruf und wird für die nächsten paar Stunden abwesend sein. Er bittet eine seiner Kolleginnen in der Radiologie, Dr. Lena Ehrle, ihn zu vertreten, während er weg ist. Er übergibt seinen Pager informell an Dr. Ehrle, die auf dringende Nachrichten und Pings auf dem Pager achtet und diese im Auftrag von Dr. Piccio zusätzlich zu ihren aktuellen Aufgaben beantwortet. Andere im Team erkennen möglicherweise nicht, dass die informelle Delegation stattgefunden hat, und es kann zu Verwirrung bei der Versorgung eines Patienten führen.

*Verwendungsbeispiel mit Festlegen der Stellvertretung:* Dr. Franco Piccio hat in der Radiologie Bereitschaftsdienst. Er erhält einen dringenden persönlichen Anruf und wird für die nächsten paar Stunden abwesend sein. Er bittet eine seiner Kolleginnen in der Radiologie, Dr. Lena Ehrle, ihn zu vertreten, während er weg ist. Er ändert seine benutzerdefinierte Statusmeldung, um etwas ähnliches zu sagen wie: „Ich bin für die nächsten Stunden nicht verfügbar. Bitte kontaktieren Sie in Notfällen @DrEhrle.“  Andere Mitglieder im Team erkennen, dass die Delegation passiert ist, wenn sie versuchen, Dr. Piccio zu kontaktieren, und wissen jetzt, dass sie in der Zwischenzeit Dr. Ehrle kontaktieren müssen. Es entsteht keine oder nur geringe Verwirrung bei der Versorgung von Patienten.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Auswirkung der Koexistenzmodi auf den Benutzerstatus im Teams-Client

Administratoren sollten sich darüber im Klaren sein, dass das Verhalten von Statusnotizen und Delegationserwähnungen teilweise vom Koexistenzmodus eines Benutzers abhängt. Diese Matrix zeigt die Möglichkeiten:

|Koexistenzmodus | Erwartetes Verhalten|
|---|---|
|TeamsOnly |Der Benutzer kann eine Notiz nur aus Teams festlegen. <br> Die Teams-Notiz des Benutzers ist in Teams und SfB ersichtlich. |
|Inseln | Die Notiz des Benutzers in Teams ist nur in Teams ersichtlich. <br> Die Notiz des Benutzers in SfB ist nur in SfB ersichtlich. |
|SfB*-Modi | Der Benutzer kann eine Notiz nur aus SfB festlegen. <br> Die SfB-Notiz des Benutzers ist in SfB und Teams ersichtlich.  |
|||

Ein Benutzer kann nur dann eine Notiz in Teams festlegen, wenn sein Modus „TeamsOnly“ oder „Inseln“ ist.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Anzeigen von Notizen, die in Skype for Business festgelegt wurden
  
Es gibt keinen visuellen Hinweis, dass eine Notiz in Skype for Business festgelegt wurde.

Skype for Business erzwingt keine Zeichenbegrenzung für Statusnachrichten. Microsoft Teams wird nur die ersten 280 Zeichen einer von Skype for Business gesendeten Notiz anzeigen. Eine Ellipse (...) am Ende einer Notiz zeigt das Abschneiden an.
  
Skype for Business unterstützt keine Ablaufzeiten für Notizen.

Die Migration von Notizen von Skype for Business zu Teams wird nicht unterstützt, wenn ein Benutzer in den TeamsOnly-Modus aktualisiert wird.

## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](../../coexistence-chat-calls-presence.md)
