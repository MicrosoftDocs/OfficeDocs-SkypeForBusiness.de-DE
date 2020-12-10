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
description: Hier erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Bildung verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616909"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Mit den Funktionen "Aufgaben" und "Noten" in "Teams für Bildung" können Pädagogen ihren Schülern Aufgaben, Arbeit oder Quizaufgaben zuweisen. Pädagogen können Zuordnungs Zeitpläne, Anweisungen, Hinzufügen von Ressourcen zum umwandeln, benoten mit Rubriken und vieles mehr verwalten. Sie können auch Kurs-und einzelne Kursteilnehmerstatus auf der Registerkarte "Noten" nachverfolgen.

[Weitere Informationen zu Aufgaben und Noten in Teams für Bildung](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Details zu Teams-Aufgaben auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Aufgaben Integrationen im Microsoft Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Pädagogen in Ihrer Organisation und deren Schüler aktivieren oder deaktivieren. Die folgenden Einstellungen beziehen sich auf Aufgaben:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Wöchentlicher Guardian-e-Mail-Digest


Guardian-e-Mails werden an alle Wochenenden an Eltern oder Erziehungsberechtigte gesendet. Die e-Mail enthält Informationen zu Aufgaben aus der vorherigen Woche und für die kommende Woche. Die übergeordnete und Guardian-Synchronisierung kann mithilfe von [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync)eingerichtet werden.

1. Importieren Sie über Eltern-und Guardian-Synchronisierung in SDS die übergeordneten Kontaktinformationen. Anweisungen zum Aktivieren der Synchronisierung von Eltern und Guardian finden Sie unter [Aktivieren der übergeordneten und Guardian-Synchronisierung](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Aktivieren Sie die Einstellung Guardian im Microsoft Teams Admin Center, da die Einstellung standardmäßig deaktiviert ist. Damit können Lehrer eine wöchentliche Zusammenfassung senden.

   > [!NOTE]
   > Lehrer können den Digest ablehnen, indem Sie die Einstellung in Ihrem eigenen persönlichen kursteam deaktivieren (**Zuordnungseinstellungen > Eltern/Betreuer-e-Mails**).

Um zu überprüfen, ob Eltern die e-Mail erhalten, müssen die folgenden drei Elemente wahr sein:

 - E-Mail-Adresse, die dem Kursteilnehmer Profil in SDS angefügt und als _Elternteil_ oder _Erziehungsberechtigter_ markiert ist. Ausführliche Informationen finden Sie unter [übergeordnetes und Guardian-Synchronisierungsdatei Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).

 - Die Kursteilnehmer gehören mindestens einer Klasse an, in der e-Mail-Nachrichten nicht vom Lehrer in den [Zuordnungseinstellungen](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)deaktiviert werden.

 - Die e-Mails enthalten Informationen zu Aufgaben, die ein Fälligkeitsdatum in der vorherigen Woche oder in der nächsten Woche hatten.

Die Standardeinstellung für dieses Feature ist- **aus**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode ist eine blockbasierte Codierungs Plattform, die die Computerwissenschaften für alle Kursteilnehmer zum Leben erweckt. 

MakeCode ist ein Microsoft-Produkt, das den Microsoft- [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und den [Datenschutz](https://go.microsoft.com/fwlink/?LinkId=521839) Richtlinien unterliegt.

Die Standardeinstellung für dieses Feature ist- **aus**.

Zum Aktivieren von MakeCode-Aufgaben in Teams wechseln Sie zum **Team Admin Center**, navigieren Sie zum Abschnitt **Aufgaben** , und aktivieren Sie die Option MakeCode-Umschaltfläche **auf ein**. Klicken Sie auf **Speichern**. Lassen Sie einige Stunden dauern, bis diese Einstellungen wirksam werden.

Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Video Demonstration](https://makecode.com/blog/teams/teams-assignments).

[Weitere Informationen zu MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) ist ein akademischer Integritätsdienst. Hierbei handelt es sich um ein Produkt oder einen Dienst eines Drittanbieters, der seinen eigenen Bedingungen und Datenschutzrichtlinien unterliegt. Sie sind für die Nutzung von Produkten und Dienstleistungen von Drittanbietern verantwortlich.

Die Standardeinstellung für dieses Feature ist- **aus**.

Zum Aktivieren von Turnitin für Ihre Organisation benötigen Sie ein Turnitin-Abonnement. Anschließend können Sie die folgenden Informationen eingeben, die in ihrer Turnitin-Verwaltungskonsole zu finden sind:

  * **TurnitinApiKey**: Hierbei handelt es sich um eine 32-Zeichen-GUID, die in der Admin-Konsole unter Integrationen gefunden wird.
  * **TurnitinApiUrl**: Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.

Hier sind einige Anweisungen, die Ihnen bei der Behebung dieser Informationen helfen.

Die **TurnitinApiUrl** ist die Hostadresse Ihrer Admin-Konsole.
Beispiel `https://your-tenant-name.turnitin.com`

In der Admin-Konsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.

Wählen Sie **Integrationen** aus dem Seitenmenü und dann **Integration hinzufügen** aus, und geben Sie der Integration einen Namen.

![Screenshot mit dem Hinzufügen einer neuen Integration](./educationImages/Assignments_mopo_turnitin2.png)

Nachdem Sie den Anweisungen folgen, wird Ihnen der **TurnitinApiKey** mitgeteilt. Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.  Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.

![Screenshot mit dem Kopieren des API-Schlüssels](./educationImages/Assignments_mopo_turnitin3.png)

Wenn Sie im Admin Center für diese Einstellung auf die Schaltfläche " **Speichern** " klicken, können diese Einstellungen einige Stunden in Kraft treten.

