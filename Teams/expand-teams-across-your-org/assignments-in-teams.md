---
title: Zuweisungen für Teams
author: DaniEASmith
ms.author: danismith
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
description: Erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Education verwalten.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91afcd8036cddfae2550aaddad776958ca413a78
ms.sourcegitcommit: 8b33cc2c2e8f43e6ab4b17715d6a42692351ccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2022
ms.locfileid: "67624295"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Die Aufgaben- und Notenfunktionen in Teams für Education lehrkräften das Zuweisen von Aufgaben, Arbeiten oder Quizfragen zu ihren Schülern ermöglichen. Lehrkräfte können Aufgabenzeitachsen, Anweisungen, Ressourcen zum Einreichen, Benotung mit Rubriken und vieles mehr verwalten. Sie können auch den Fortschritt von Kursteilnehmern und einzelnen Kursteilnehmern auf der Registerkarte "Noten" nachverfolgen.

[Erfahren Sie mehr über Aufgaben und Noten in Teams für Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Ausführliche Informationen zu Teams-Aufgaben auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Aufgabenintegrationen im Microsoft Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Lehrkräfte in Ihrer Organisation und deren Kursteilnehmer aktivieren oder deaktivieren. Die folgenden Einstellungen beziehen sich auf Zuweisungen:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Wöchentlicher E-Mail-Digest für Erziehungsberechtigte

Erziehungsberechtigte E-Mails werden jedes Wochenende an Eltern oder Erziehungsberechtigte gesendet. Die E-Mail enthält Informationen zu Aufgaben aus der vorherigen und für die kommende Woche. Die Synchronisierung von Eltern und Erziehungsberechtigten kann mit [School Data Sync](/schooldatasync/parent-contact-sync) eingerichtet werden.

1. Importieren Sie die Kontaktinformationen der Eltern über die Synchronisierung von Eltern und Erziehungsberechtigten in SDS. Anweisungen zum Aktivieren der Synchronisierung von Eltern und Erziehungsberechtigten finden Sie [unter Aktivieren der Synchronisierung von Eltern und Erziehungsberechtigten](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Aktivieren Sie die Einstellung "Guardian" im Microsoft Teams Admin Center, da die Einstellung standardmäßig deaktiviert ist. Dadurch können Lehrer einen wöchentlichen Digest senden.

   > [!NOTE]
   > Lehrer können den Digest deaktivieren, indem sie die Einstellung innerhalb ihres eigenen persönlichen Kursteams deaktivieren (**Aufgabeneinstellungen > E-Mails von Eltern/Erziehungsberechtigten**).

Um zu überprüfen, ob Eltern die E-Mail erhalten, müssen die folgenden drei Elemente wahr sein:

- Email Adresse, die an das Kursteilnehmerprofil in SDS angefügt und als _Eltern_ oder _Erziehungsberechtigter_ markiert ist. Ausführliche Informationen finden Sie im [Synchronisierungsdateiformat für Eltern und Erziehungsberechtigte](/schooldatasync/parent-contact-sync-file-format).

- Die Kursteilnehmer gehören mindestens einem Kurs an, in dem E-Mail vom Lehrer in den [Aufgabeneinstellungen](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77) nicht deaktiviert wird.

- Die E-Mails enthalten Informationen zu Aufgaben, die ein Fälligkeitsdatum aus der vorherigen Woche oder in der kommenden Woche haben.

Die Standardeinstellung für dieses Feature ist " **Aus**".

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode ist eine blockbasierte Codierungsplattform, die Informatik für alle Schüler zum Leben erweckt.

MakeCode ist ein Microsoft-Produkt, das den [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und [Datenschutzrichtlinien](https://go.microsoft.com/fwlink/?LinkId=521839) von Microsoft unterliegt.

Die Standardeinstellung für dieses Feature ist " **Aus**".

Um MakeCode-Aufgaben in Teams zu aktivieren, wechseln Sie zum **Teams Admin Center**, navigieren Sie zum Abschnitt **"Aufgaben**", und aktivieren Sie die Option "MakeCode **".** Klicken Sie auf **Speichern**. Lassen Sie einige Stunden zeit, bis diese Einstellungen wirksam werden.

Weitere Informationen zur Funktionsweise dieses Features erfahren Sie in dieser [Videodemonstration](https://makecode.com/blog/teams/teams-assignments).

[Erfahren Sie mehr über MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) ist ein Dienst für akademische Integrität. Dies ist ein Drittanbieterdienst, der seinen eigenen Bedingungen und Datenschutzrichtlinien unterliegt. Sie sind für die Nutzung von Produkten und Dienstleistungen von Drittanbietern verantwortlich.

Die Standardeinstellung für dieses Feature ist " **Aus**".

Um Turnitin für Ihre Organisation zu aktivieren, benötigen Sie ein Turnitin-Abonnement. Anschließend können Sie die folgenden Informationen eingeben, die sie in Ihrer Turnitin-Administratorkonsole finden:

- **TurnitinApiKey**: Dies ist eine 32-stellige GUID, die in der Verwaltungskonsole unter "Integrationen" zu finden ist.
- **TurnitinApiUrl**: Dies ist die HTTPS-URL Ihrer Turnitin-Administratorkonsole.

Hier sind einige Anweisungen, die Ihnen beim Abrufen dieser Informationen helfen sollen.

**TurnitinApiUrl** ist die Hostadresse Ihrer Administratorkonsole.
Beispiel: `https://your-tenant-name.turnitin.com`

In der Administratorkonsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.

Wählen Sie im Seitenmenü " **Integrationen** " und dann " **Integration hinzufügen"** aus, und geben Sie der Integration einen Namen.

![Screenshot, der das Hinzufügen einer neuen Integration zeigt.](./educationImages/Assignments_mopo_turnitin2.png)

Der **TurnitinApiKey** wird Ihnen übergeben, nachdem Sie den Anweisungen folgen.
Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.  Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.

![Screenshot, der das Kopieren des API-Schlüssels zeigt.](./educationImages/Assignments_mopo_turnitin3.png)

Wenn Sie für diese Einstellung auf die Schaltfläche " **Speichern** " im Admin Center klicken, lassen Sie einige Stunden zeit, bis diese Einstellungen wirksam werden.

## <a name="assignments-data"></a>Zuordnungsdaten

Aufgaben speichern Informationen, die sowohl von Lehrkräften als auch von Schülern/Studenten generiert werden. Alle Daten werden gemeinsam zwischen dem Lehrer und dem jeweiligen Kursteilnehmer freigegeben, für den die Informationen im Kurs bestimmt sind. Es gibt zwei Speicher dieser Daten, SharePoint und außerhalb von SharePoint.

>[!NOTE]
>Die gleichen Regeln gelten auch für Erstanbieterintegrationen wie Lesefortschritt.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Zuordnungsdaten in SharePoint-Dokumentbibliotheken

Die Dateien von Kursteilnehmern, die einer Übermittlung für aufgaben zugeordnet sind, werden in einer Dokumentbibliothek (mit dem Namen" *Student Work*) gespeichert. Dateien, die Aufgaben zugeordnet sind, die von Lehrern erstellt wurden und auf die kursteilnehmer zugreifen können, werden in einer anderen Dokumentbibliothek (mit dem Namen " *Kursdateien*") auf der entsprechenden SharePoint-Website des Kursteams gespeichert. Erstanbieterintegrationen können auch Aufgabendaten auf derselben entsprechenden SharePoint-Website des Kursteams speichern (benannt: *Aufgabentitel + Zeitstempel*).

#### <a name="files-associated-with-the-student"></a>Dateien, die dem Kursteilnehmer zugeordnet sind

IT-Administratoren können das Tool für die Inhaltssuche verwenden, um nach Kursteilnehmerdateien (*Schülerarbeit*, *Kursdateien* oder andere Integrationsdateien von Drittanbietern) zu suchen, die sich auf Aufgabenübermittlungen und Dateien beziehen, die sich auf Aufgaben beziehen. Beispielsweise könnte ein Administrator alle SharePoint-Websites in der Organisation durchsuchen und den Namen des Kursteilnehmers und den Kurs- oder Aufgabennamen in der Suchabfrage verwenden, um Daten zu finden, die für eine Anforderung betroffener Personen relevant sind.

#### <a name="files-associated-with-the-teacher"></a>Dem Lehrer zugeordnete Dateien

IT-Administratoren können das Tool für die Inhaltssuche verwenden, um nach Lehrerdateien (*Schülerarbeit*, *Kursdateien* oder andere Integrationsdateien von Drittanbietern) zu suchen, die sich auf Aufgaben und Dateien beziehen, die von den Lehrkräften innerhalb eines Kurses für Aufgaben an Kursteilnehmer verteilt werden. Beispielsweise könnte ein Administrator alle SharePoint-Websites in der Organisation durchsuchen und den Namen des Lehrers und den Kurs- oder Aufgabennamen in der Suchabfrage verwenden, um Daten zu finden, die für einen Antrag einer betroffenen Person relevant sind.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Zuordnungsdaten außerhalb von SharePoint-Dokumentbibliotheken

Einige Daten im Zusammenhang mit Aufgaben werden nicht auf der SharePoint-Website des Kursteams gespeichert, was bedeutet, dass sie bei der Inhaltssuche nicht auffindbar sind. Dazu gehören:

- Schülernoten und Feedback des Lehrers
- Die Liste der Dokumente, die von jedem Kursteilnehmer für eine Aufgabe eingereicht wurden
- Aufgabendetails wie Fälligkeitsdatum usw.
- Integrationsdaten von Erstanbietern wie Lesefortschrittspassagen oder Aussprachedaten für Schüler/Studenten

Für diese Art von Daten muss möglicherweise ein IT-Administrator oder Datenbesitzer, z. B. ein Lehrer, in die Aufgabe im Kursteam wechseln, um Daten zu finden, die für einen Antrag einer betroffenen Person relevant sind. Der Administrator kann sich selbst als Besitzer zum Kurs hinzufügen und alle Aufgaben für dieses Kursteam anzeigen.

>[!NOTE]
>Wenn ein Kursteilnehmer nicht mehr Teil des Kurses ist, sind seine Daten möglicherweise weiterhin im Kurs vorhanden, da er *nicht mehr registriert ist*. Der Kursteilnehmer muss dem Mandantenadministrator die Liste der Kurse bereitstellen, an denen er jemals teilgenommen hat.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Massenexport von Zuordnungsdaten außerhalb von SharePoint-Dokumentbibliotheken

#### <a name="for-a-student"></a>Für einen Kursteilnehmer

Um die Daten eines einzelnen Kursteilnehmers in einem Massenexport zu exportieren, führen Sie das Skript aus, und stellen Sie das Skript bereit, bevor Sie [den](/microsoft-365/education/deploy/configure-assignments-for-teams) Kursteilnehmer aus den Kursen entfernen, an dem ``userId``er teil ist. Wenn der Kursteilnehmer von der Website entfernt wurde, kann entweder der Administrator den Kursteilnehmer wieder zum Kurs hinzufügen, bevor er das Skript ausführt, oder der Administrator kann den ``userId`` und den Kursteilnehmer bereitstellen, an dem ``classId`` der Kursteilnehmer jemals teilgenommen hat.

Die Daten zu den Schüler-/Studentenübermittlungen werden exportiert.

#### <a name="for-a-teacher"></a>Für einen Lehrer

Massenexport von Aufgabendaten funktioniert für einen Kursteilnehmer auf die gleiche Weise, aber alle Übermittlungen, auf die der Lehrer Zugriff hat, werden exportiert.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Massenlöschen von Zuordnungsdaten außerhalb von SharePoint-Dokumentbibliotheken

#### <a name="for-a-student"></a>Für einen Kursteilnehmer

Um die Daten eines einzelnen Kursteilnehmers in einem Massenvorgang zu löschen, führen Sie das Skript aus, und stellen Sie das Skript bereit, bevor Sie [den](/microsoft-365/education/deploy/configure-assignments-for-teams) Kursteilnehmer aus den Kursen entfernen, an dem ``userId``er Teil ist. Wenn der Kursteilnehmer von der Website entfernt wurde, kann entweder der Administrator den Kursteilnehmer wieder zum Kurs hinzufügen, bevor er das Skript ausführt, oder der Administrator kann den ``userId`` und den Kursteilnehmer bereitstellen, an dem ``classId`` der Kursteilnehmer jemals teilgenommen hat.

Das Bereitstellen eines ``ClassId`` Benachrichtigungsmoduls ermöglicht es dem Administrator, nur Informationen über den Kursteilnehmer aus einem bestimmten Kurs zu löschen.

#### <a name="for-a-teacher"></a>Für einen Lehrer

Da die Daten einer Aufgabe für einen Lehrer für den gesamten Kurs freigegeben sind, gibt es keine Option zum Massenlöschen. Stattdessen kann der Administrator sich selbst zum Kurs hinzufügen, zur App wechseln und die Aufgabe löschen.

Weitere Informationen finden Sie unter [Konfigurieren von Aufgaben für Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Entfernen von Aufgaben und Noten

Sie können auch Teams-Richtlinien verwenden, um Aufgaben und Noten für einen bestimmten Benutzer oder für Ihren gesamten Mandanten zu entfernen.

Um Aufgaben und Noten für einen einzelnen Benutzer zu entfernen, wechseln Sie zum **Teams Admin Center**, und navigieren Sie zu **Teams-Apps > Berechtigungsrichtlinien**, um eine neue App-Berechtigungsrichtliniendefinition zu erstellen.  Legen Sie beim Erstellen der neuen Richtliniendefinition die **Microsoft-Apps-Richtlinie** auf _"Bestimmte Apps blockieren" fest, und lassen Sie alle anderen_ apps zu, und fügen Sie der Liste der **blockierten Anwendungen Aufgaben** und **Noten** hinzu. Sobald Die neue Richtliniendefinition gespeichert wurde, weisen Sie sie den entsprechenden Benutzern zu.

Um Aufgaben und Noten für Ihren gesamten Mandanten zu entfernen, wechseln Sie zum **Teams Admin Center**, navigieren Sie zu **Teams-Apps > Apps verwalten**, und suchen Sie in der Anwendungsliste nach **Aufgaben** und **Noten**, und wählen Sie sie aus. Ändern Sie die Statuseinstellung auf der Einstellungsseite der Anwendungen in _"Blockiert_".

## <a name="assignments-diagnostic-tool-for-users"></a>Diagnosetool für Zuweisungen für Benutzer

Microsoft-Support hat ein Tool zum Sammeln von Diagnosedaten für das Microsoft-Entwicklungsteam erstellt, um Probleme im Zusammenhang mit der Aufgabenfunktion zu untersuchen.

Auf dieses Tool kann innerhalb von Aufgaben auf jedem Bildschirm zugegriffen werden, auf dem ein Problem auftritt.

Zum Abrufen des Diagnosetools in Teams können Benutzer folgende Aktionen ausführen:

- **Auf Desktop und Web:**
  - Strg+/ auswählen
- **Auf mobilen Geräten:**
  - Berühren Sie den Bildschirm mit zwei Fingern, und drehen Sie die Finger um 45 Grad, oder
  - 15 Sekunden lang mit drei Fingern auf den Bildschirm tippen

Sobald das Diagnosetool angezeigt wird, wird benutzern eine Liste der Daten angezeigt, die möglicherweise vom technischen Support von Microsoft benötigt werden.

Die abgerufenen Daten können Folgendes umfassen:

- Gruppen-ID
- Mandanten-ID
- Sitzungs-ID
- Zuordnungs-ID
- Übermittlungs-ID
- Benutzer-ID

Diese Daten werden nicht automatisch an Microsoft gesendet. Benutzer müssen die Daten in Bezug auf ein Supportticket kopieren und in einen Microsoft-Supportmitarbeiter einfügen.

Wenn ein Benutzer das Diagnosetool abruft und es dann schließt, werden keine Daten gesendet.

Wenn die Daten an einen Microsoft-Supportmitarbeiter gesendet werden, werden sie als Supportdaten gemäß den Microsoft 365-Serviceverträgen Ihrer Organisation behandelt.

Anweisungen zur Verwendung dieses Diagnosetools, das Sie für Lehrkräfte und Schüler/Studenten freigeben können, finden [Sie unter "Abrufen von Diagnosedaten zur Problembehandlung bei Aufgaben](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)".
