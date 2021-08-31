---
title: Zuweisungen für Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Education.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef615924a4c449a3b2b408d929cf3d2678e4a1e6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728674"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Die Features "Aufgaben" und "Noten" in Teams für Education Lehrkräften das Zuweisen von Aufgaben, Arbeiten oder Quizzen zu ihren Schülern/Studierenden ermöglichen. Lehrkräfte können Zeitpläne für Aufgaben verwalten, Anweisungen, Ressourcen zum Turnen hinzufügen, mit Rubriken benoten und vieles mehr. Auf der Registerkarte "Noten" können sie auch den Fortschritt des Kurs- und des einzelnen Schülers/Studenten nachverfolgen.

[Weitere Informationen zu Aufgaben und Noten finden Sie in Teams für Education.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Details zu den Teams auf verschiedenen Plattformen finden Sie unter Teams [von Features nach Plattform.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Aufgabenintegrationen im Microsoft Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Lehrkräfte in Ihrer Organisation und deren Schüler/Studenten aktivieren oder deaktivieren. Im Folgenden finden Sie Einstellungen im Zusammenhang mit "Aufgaben":

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Wöchentlicher E-Mail-Digest für Erziehungsberechtigte


Erziehungsberechtigte E-Mails werden an jedem Wochenende an Eltern oder Erziehungsberechtigte gesendet. Die E-Mail enthält Informationen zu Aufgaben der vorherigen und der nächsten Woche. Die Synchronisierung für Eltern und Erziehungsberechtigte kann mithilfe von [School Data Sync.](/schooldatasync/parent-contact-sync)

1. Importieren Sie Kontaktinformationen von Eltern über die Synchronisierung von Eltern und Erziehungsberechtigten in SDS. Anweisungen zum Aktivieren der Synchronisierung von Eltern und Erziehungsberechtigten finden Sie unter Aktivieren der Synchronisierung von Eltern [und Erziehungsberechtigten.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Aktivieren Sie im Microsoft Teams Admin Center die Einstellung für Erziehungsberechtigte, da die Einstellung standardmäßig deaktiviert ist. Auf diese Weise können Lehrkräfte eine wöchentliche Digest senden.

   > [!NOTE]
   > Lehrkräfte können die Digest-Benachrichtigung deaktivieren, indem sie die Einstellung innerhalb ihres eigenen persönlichen Kursteams deaktivieren (Einstellungen >-E-Mails für **Eltern/Erziehungsberechtigte).**

Um zu überprüfen, ob "Eltern" die E-Mail erhalten wird, müssen die folgenden drei Elemente wahr sein:

 - E-Mail-Adresse, die an das Schülerprofil in SDS angefügt und als _Übergeordneter oder Erziehungsberechtigter_ _markiert ist._ Details finden Sie unter [Synchronisierungsdateiformat für Eltern und Erziehungsberechtigte.](/schooldatasync/parent-contact-sync-file-format)

 - Schüler gehören mindestens einem Kurs an, in dem E-Mail-Nachrichten nicht vom Lehrer in den [Aufgabeneinstellungen deaktiviert werden.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Die E-Mails enthalten Informationen zu Aufgaben, deren Fälligkeitsdatum in der vorherigen oder in der anstehenden Woche war.

Die Standardeinstellung für dieses Feature ist - **Aus.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode ist eine blockbasierte Codierungsplattform, die Computerwissenschaften für alle Schüler und Studenten zum Leben erweckt. 

MakeCode ist ein Microsoft-Produkt, das den [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und Datenschutzrichtlinien von Microsoft [unterliegt.](https://go.microsoft.com/fwlink/?LinkId=521839)

Die Standardeinstellung für dieses Feature ist - **Aus.**

Um MakeCode-Aufgaben in Teams zu aktivieren, wechseln Sie zum Teams  **Admin Center,** navigieren Sie zum Abschnitt Aufgaben, und stellen Sie die Umschaltoption MakeCode auf **Ein um.** Klicken Sie auf **Speichern**. Es kann einige Stunden dauern, bis diese Einstellungen wirksam werden.

Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Videodemo.](https://makecode.com/blog/teams/teams-assignments)

[Weitere Informationen zu MakeCode.](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) ist ein Dienst zur akademischen Integrität. Dies ist ein Produkt oder Dienst eines Drittanbieters, das eigenen Bedingungen und der eigenen Datenschutzrichtlinie unterliegt. Sie sind für die Verwendung von Produkten und Diensten von Drittanbietern verantwortlich.

Die Standardeinstellung für dieses Feature ist - **Aus**.

Zum Aktivieren von Turnitin für Ihre Organisation benötigen Sie ein Turnitin-Abonnement. Anschließend können Sie die folgenden Informationen in Ihrer Turnitin-Verwaltungskonsole eingeben:

  * **TurnitinApiKey:** Dies ist eine 32- zeichende GUID, die in der Verwaltungskonsole unter Integrationen zu finden ist.
  * **TurnitinApiUrl:** Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.

Hier sind einige Anweisungen, die Ihnen helfen, diese Informationen zu erhalten.

Die **TurnitinApiUrl** ist die Hostadresse Ihrer Administratorkonsole.
Beispiel: `https://your-tenant-name.turnitin.com`

In der Administratorkonsole können Sie eine Integration und einen API-Schlüssel erstellen, die mit der Integration verknüpft sind.

Wählen **Sie im Seitenmenü** Integrationen und dann **Integration** hinzufügen aus, und geben Sie der Integration einen Namen.

![Screenshot, der zeigt, wie eine neue Integration hinzugefügt wird.](./educationImages/Assignments_mopo_turnitin2.png)

Der **TurnitinApiKey** wird Ihnen nach dem Folgen der Eingabeaufforderungen angezeigt. Kopieren Sie den API-Schlüssel, und fügen Sie ihn in Microsoft Teams Admin Center ein.  Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.

![Screenshot, der das Kopieren des API-Schlüssels zeigt.](./educationImages/Assignments_mopo_turnitin3.png)

Wenn Sie **für** diese Einstellung im Admin Center auf die Schaltfläche Speichern klicken, dauert es einige Stunden, bis diese Einstellungen wirksam werden.

### <a name="removing-assignments-and-grades"></a>Entfernen von Aufgaben und Noten
Mithilfe von Teams können Sie Zuweisungen und Noten für einen bestimmten Benutzer oder für Ihren gesamten Mandanten entfernen. 

Um Aufgaben und Noten für einen einzelnen Benutzer zu entfernen, wechseln Sie zum **Teams Admin Center,** und navigieren Sie zu **Teams-Apps > Berechtigungsrichtlinien,** um eine neue Definition der App-Berechtigungsrichtlinie zu erstellen.  Legen Sie beim Erstellen der neuen Richtliniendefinition die **Richtlinie für Microsoft-Apps** auf Bestimmte Apps blockieren und alle anderen Apps blockieren sowie Zuweisungen zur Liste der blockierten Anwendungen hinzu.   Nachdem Sie die neue Richtliniendefinition gespeichert haben, weisen Sie sie den entsprechenden Benutzern zu.

Wenn Sie Aufgaben und Noten für den gesamten Mandanten entfernen möchten, wechseln Sie zum **Teams Admin Center**, navigieren  Sie zu **Teams-Apps >** Apps verwalten , und suchen Sie in der Anwendungsliste nach Aufgaben, und wählen Sie diese aus. Ändern Sie die Statuseinstellung auf der Seite Einstellungen der Aufgabenanwendung in _Blockiert._ 
