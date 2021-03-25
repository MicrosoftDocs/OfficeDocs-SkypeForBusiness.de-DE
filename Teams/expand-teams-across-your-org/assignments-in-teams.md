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
description: Erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams for Education verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121373"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Die Funktionen "Aufgaben und Noten" in Teams for Education ermöglichen Es Lehrkräften, ihren Schülern Aufgaben, Arbeit oder Quizze zuzuordnen. Lehrkräfte können Zeitachsen, Anweisungen für Aufgaben verwalten, Ressourcen zum Einwechseln hinzufügen, mit Rubriken benoten und vieles mehr. Sie können auch den Kurs- und individuellen Fortschritt der Kursteilnehmer auf der Registerkarte Noten nachverfolgen.

[Weitere Informationen zu Aufgaben und Noten finden Sie in Teams for Education.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Details zu Teams-Aufgaben auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Aufgabenintegrationen im Microsoft Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Lehrkräfte in Ihrer Organisation und deren Kursteilnehmer aktivieren oder deaktivieren. Die folgenden Einstellungen sind im Zusammenhang mit "Aufgaben" zu finden:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Wöchentlicher Guardian-E-Mail-Digest


Guardian-E-Mails werden jedes Wochenende an Eltern oder Erziehungsberechtigte gesendet. Die E-Mail enthält Informationen zu Aufgaben aus der vorherigen Woche und der kommenden Woche. Die Synchronisierung von Eltern und Erziehungsberechtigten kann mithilfe von [School Data Sync eingerichtet werden.](/schooldatasync/parent-contact-sync)

1. Importieren Sie übergeordnete Kontaktinformationen über parent and Guardian Sync in SDS. Anweisungen zum Aktivieren der Synchronisierung von Eltern und Erziehungsberechtigten finden Sie unter Aktivieren der Synchronisierung von Eltern [und Erziehungsberechtigten.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Aktivieren Sie die Guardian-Einstellung im Microsoft Teams Admin Center, da die Einstellung standardmäßig deaktiviert ist. Auf diese Weise können Lehrkräfte wöchentlich einen Digest senden.

   > [!NOTE]
   > Lehrkräfte können den Digest deaktivieren, indem sie die Einstellung innerhalb ihres eigenen persönlichen Kursteams (Aufgabeneinstellungen >**Eltern-/Erziehungsberechtigten-E-Mails) deaktivieren.**

Um zu überprüfen, ob Eltern die E-Mail erhalten, müssen die folgenden drei Elemente wahr sein:

 - E-Mail-Adresse, die an das Studentenprofil in SDS angefügt und als _"Elternteil"_ oder "Erziehungsberechtigter" _gekennzeichnet ist._ Details finden Sie unter [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).

 - Die Kursteilnehmer gehören mindestens einer Klasse an, in der E-Mail vom Lehrer in den [Aufgabeneinstellungen nicht deaktiviert wird.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Die E-Mails enthalten Informationen zu Aufgaben, die in der vorherigen Oder in der kommenden Woche ein Fälligkeitsdatum hatten.

Die Standardeinstellung für dieses Feature ist : **Aus**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode ist eine blockbasierte Codierungsplattform, die die Computerwissenschaft für alle Kursteilnehmer zum Leben erweckt. 

MakeCode ist ein Microsoft-Produkt, [](https://go.microsoft.com/fwlink/?LinkID=206977) das den Microsoft-Nutzungsbedingungen und den [Datenschutzrichtlinien](https://go.microsoft.com/fwlink/?LinkId=521839) unterliegt.

Die Standardeinstellung für dieses Feature ist : **Aus**.

Um MakeCode-Zuordnungen in Teams zu aktivieren, wechseln  Sie zum **Teams Admin Center,** navigieren Sie zum Abschnitt Aufgaben, und aktivieren Sie die Umschaltoption MakeCode auf **Ein.** Klicken Sie auf **Speichern**. Lassen Sie ein paar Stunden, bis diese Einstellungen wirksam werden.

Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Videodemonstration.](https://makecode.com/blog/teams/teams-assignments)

[Weitere Informationen zu MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) ist ein Dienst für akademische Integrität. Dies ist ein Produkt oder eine Dienstleistung eines Drittanbieters, das eigenen Bedingungen und Datenschutzrichtlinien unterliegt. Sie sind für die Verwendung von Produkten und Diensten von Drittanbietern verantwortlich.

Die Standardeinstellung für dieses Feature ist : **Aus**.

Um Turnitin für Ihre Organisation zu aktivieren, benötigen Sie ein Turnitin-Abonnement. Anschließend können Sie die folgenden Informationen eingeben, die sie in Ihrer Turnitin Admin Console finden:

  * **TurnitinApiKey:** Dies ist eine GUID mit 32 Zeichen, die in der Administratorkonsole unter Integrationen gefunden wurde.
  * **TurnitinApiUrl:** Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.

Hier sind einige Anweisungen, die Ihnen beim Abrufen dieser Informationen helfen.

Die **TurnitinApiUrl** ist die Hostadresse Ihrer Administratorkonsole.
Beispiel: `https://your-tenant-name.turnitin.com`

In der Administratorkonsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.

Wählen **Sie im** Seitenmenü Integrationen und dann Integration hinzufügen **aus,** und geben Sie der Integration einen Namen.

![Screenshot mit dem Hinzufügen einer neuen Integration](./educationImages/Assignments_mopo_turnitin2.png)

Der **TurnitinApiKey** wird Ihnen angezeigt, nachdem Sie den Eingabeaufforderungen folgen. Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.  Dies ist der einzige Zeitpunkt, zu dem Sie den Schlüssel anzeigen können.

![Screenshot des Kopierens des API-Schlüssels](./educationImages/Assignments_mopo_turnitin3.png)

Nachdem Sie **im** Admin Center für diese Einstellung auf die Schaltfläche Speichern geklickt haben, lassen Sie einige Stunden zu, bis diese Einstellungen wirksam werden.