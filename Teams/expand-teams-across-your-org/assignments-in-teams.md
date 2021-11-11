---
title: Zuweisungen für Teams
author: danieasmith
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
description: Erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Education.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59fb8e0b81195c696b7bd6142ecf031688207917
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909596"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Die Features "Aufgaben" und "Noten" in Teams für Education Lehrkräften das Zuweisen von Aufgaben, Arbeiten oder Quizzen zu ihren Schülern/Studierenden ermöglichen. Lehrkräfte können Zeitpläne für Aufgaben verwalten, Anweisungen, Ressourcen zum Turnen hinzufügen, mit Rubriken benoten und vieles mehr. Auf der Registerkarte "Noten" können sie auch den Fortschritt des Kurs- und des einzelnen Schülers/Studenten nachverfolgen.

[Weitere Informationen zu Aufgaben und Noten finden Sie in Teams für Education.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Details zu den Teams auf verschiedenen Plattformen finden Sie unter Teams [von Features nach Plattform.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrationen von Aufgaben im Microsoft Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Lehrkräfte in Ihrer Organisation und deren Schüler/Studenten aktivieren oder deaktivieren. Im Folgenden finden Sie Einstellungen im Zusammenhang mit "Aufgaben":

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Wöchentlicher E-Mail-Digest für Erziehungsberechtigte

Erziehungsberechtigte E-Mails werden an jedem Wochenende an Eltern oder Erziehungsberechtigte gesendet. Die E-Mail enthält Informationen zu Aufgaben der vorherigen und der nächsten Woche. Die Synchronisierung von Eltern und Erziehungsberechtigten kann mithilfe von [School Data Sync.](/schooldatasync/parent-contact-sync)

1. Importieren Sie Kontaktinformationen von Eltern über die Synchronisierung von Eltern und Erziehungsberechtigten in SDS. Anweisungen zum Aktivieren der Synchronisierung von Eltern und Erziehungsberechtigten finden Sie unter Aktivieren der Synchronisierung von Eltern [und Erziehungsberechtigten.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Aktivieren Sie im Microsoft Teams Admin Center die Einstellung für Erziehungsberechtigte, da die Einstellung standardmäßig deaktiviert ist. Auf diese Weise können Lehrkräfte eine wöchentliche Digest senden.

   > [!NOTE]
   > Lehrkräfte können die Digest-Benachrichtigung deaktivieren, indem sie die Einstellung in ihrem eigenen persönlichen Kursteam deaktivieren (Aufgaben- Einstellungen >-E-Mails für **Eltern/Erziehungsberechtigte).**

Um zu überprüfen, ob "Eltern" die E-Mail erhalten wird, müssen die folgenden drei Punkte zutreffen:

- E-Mail-Adresse, die an das Schülerprofil in SDS angefügt und als _Übergeordneter oder Erziehungsberechtigter_ _markiert ist._ Details finden Sie unter [Synchronisierungsdateiformat für Eltern und Erziehungsberechtigte.](/schooldatasync/parent-contact-sync-file-format)

- Schüler gehören mindestens einem Kurs an, in dem E-Mail-Nachrichten nicht vom Lehrer in den [Aufgabeneinstellungen deaktiviert werden.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

- Die E-Mails enthalten Informationen zu Aufgaben, deren Fälligkeitsdatum in der vorherigen oder in der kommenden Woche liegt.

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

[Turnitin](https://www.turnitin.com/) ist ein Dienst zur akademischen Integrität. Dies ist ein Drittanbieterdienst, der eigenen Bedingungen und den eigenen Datenschutzrichtlinien unterliegt. Sie sind für die Verwendung von Produkten und Diensten von Drittanbietern verantwortlich.

Die Standardeinstellung für dieses Feature ist - **Aus**.

Zum Aktivieren von Turnitin für Ihre Organisation benötigen Sie ein Turnitin-Abonnement. Anschließend können Sie die folgenden Informationen in Ihrer Turnitin-Verwaltungskonsole eingeben:

- **TurnitinApiKey:** Dies ist eine 32- zeichende GUID, die in der Verwaltungskonsole unter Integrationen zu finden ist.
- **TurnitinApiUrl:** Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.

Hier sind einige Anweisungen, die Ihnen helfen, diese Informationen zu erhalten.

Die **TurnitinApiUrl** ist die Hostadresse Ihrer Administratorkonsole.
Beispiel: `https://your-tenant-name.turnitin.com`

In der Administratorkonsole können Sie eine Integration und einen API-Schlüssel erstellen, die mit der Integration verknüpft sind.

Wählen **Sie im Seitenmenü** Integrationen und dann **Integration** hinzufügen aus, und geben Sie der Integration einen Namen.

![Screenshot, der zeigt, wie eine neue Integration hinzugefügt wird.](./educationImages/Assignments_mopo_turnitin2.png)

Der **TurnitinApiKey-Schlüssel** wird Ihnen nach dem Folgen der Eingabeaufforderungen angezeigt.
Kopieren Sie den API-Schlüssel, und fügen Sie ihn in Microsoft Teams Admin Center ein.  Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.

![Screenshot, der das Kopieren des API-Schlüssels zeigt.](./educationImages/Assignments_mopo_turnitin3.png)

Wenn Sie **für** diese Einstellung im Admin Center auf die Schaltfläche Speichern klicken, dauert es einige Stunden, bis diese Einstellungen wirksam werden.

## <a name="assignments-data"></a>Zuordnungsdaten

Aufgaben speichert Informationen, die von Lehrkräften und Schülern/Studenten generiert werden. Alle Daten werden gemeinsam zwischen dem Lehrer und dem jeweiligen Kursteilnehmer freigegeben, für den die Informationen im Kurs vorgesehen sind. Es gibt zwei Stores hier von SharePoint außerhalb SharePoint.

>[!NOTE]
>Die gleichen Regeln gelten auch für Erst-Party-Integrationen, z. B. Lesefortschritt.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Zuordnungsdaten in SharePoint Dokumentbibliotheken

Die Dateien der Kursteilnehmer, die einer Übermittlung für Aufgaben zugeordnet sind, werden in einer Dokumentbibliothek gespeichert (name: *Student Work*). Dateien, die Aufgaben zugeordnet sind, die von Lehrkräften erstellt werden und auf die die Kursteilnehmer zugreifen können, werden in einer anderen Dokumentbibliothek (mit Namen Kursdateien) auf der entsprechenden Kursteamwebsite SharePoint gespeichert. First-Party-Integrationen können auch Aufgabendaten auf der gleichen entsprechenden Kursteamwebsite speichern SharePoint (benannt: *Aufgabentitel + Zeitstempel*).

#### <a name="files-associated-with-the-student"></a>Dem Schüler/Studenten zugeordnete Dateien

IT-Administratoren können das Tool für die Inhaltssuche verwenden, um nach Kursteilnehmerdateien (Student *Work,* *Class Files* oder anderen Integrationsdateien von Drittanbietern) zu suchen, die sich auf Aufgabenübermittlungen und Dateien im Zusammenhang mit Aufgaben befinden. Beispielsweise könnte ein Administrator alle SharePoint-Websites in der Organisation durchsuchen und den Namen des Kursteilnehmers sowie den Kurs- oder Aufgabennamen in der Suchabfrage verwenden, um für eine Datensubjektanforderung (Data Subject Request, DSR) relevante Daten zu finden.

#### <a name="files-associated-with-the-teacher"></a>Dem Lehrer zugeordnete Dateien

IT-Administratoren können das Tool für die Inhaltssuche verwenden, um nach Lehrerdateien (Student *Work,* *Class Files* oder anderen Integrationsdateien von Drittanbietern) zu suchen, die mit Aufgaben in Zusammenhang stehen, sowie nach Dateien, die von den Lehrkräften eines Kurs zu Aufgaben an Kursteilnehmer verteilt wurden. Beispielsweise könnte ein Administrator alle SharePoint-Websites in der Organisation durchsuchen und den Namen des Lehrers sowie den Kurs- oder Aufgabennamen in der Suchabfrage verwenden, um für eine DSR relevante Daten zu finden.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Aufgabendaten außerhalb SharePoint Dokumentbibliotheken

Einige Daten im Zusammenhang mit "Aufgaben" werden nicht auf der Kursteamwebsite SharePoint gespeichert, d. h., sie können mit der Inhaltssuche nicht gefunden werden. Dies umfasst:

- Noten der Schüler und Feedback von der Lehrkraft
- Die Liste der Dokumente, die für eine Aufgabe von jedem Kursteilnehmer übermittelt wurden
- Aufgabendetails wie Fälligkeitsdatum usw.
- Integrationsdaten von Erstpartei wie Lesefortschritt passagen oder Aussprachedaten von Kursteilnehmern

Bei dieser Art von Daten muss ein IT-Administrator oder Datenbesitzer, z. B. ein Lehrer, möglicherweise der Aufgabe im Kursteam wechseln, um für einen DSR relevante Daten zu finden. Der Administrator kann sich selbst als Besitzer zum Kurs hinzufügen und alle Aufgaben für dieses Kursteam anzeigen.

>[!NOTE]
>Wenn ein Kursteilnehmer nicht mehr Teil der Klasse ist, sind seine Daten möglicherweise noch im Kurs vorhanden, da *er nicht mehr registriert ist.* Der Kursteilnehmer muss dem Mandantenadministrator die Liste solcher Kurse bereitstellen, an der sie jemals teilnehmen.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Massenexport von Zuordnungsdaten außerhalb SharePoint Dokumentbibliotheken

#### <a name="for-a-student"></a>Für einen Kursteilnehmer

Um einen Massenexport der Daten eines einzelnen Kursteilnehmers auszuführen, führen Sie vor dem Entfernen des Kursteilnehmers aus den [Klassen,](/microsoft-365/education/deploy/configure-assignments-for-teams) an dem er teil hat, das Skript aus, und stellen Sie das -Skript zur ``userId`` Verfügung. Wenn der Kursteilnehmer von der Website entfernt wurde, kann entweder der Administrator den Kursteilnehmer wieder zum Kurs hinzufügen, bevor er das Skript ausführen, oder der Administrator kann die und die bereitstellen, zu der der Kursteilnehmer jemals gehört ``userId`` ``classId`` hat.

Die Daten zu den Einreichungen der Schüler/Studenten werden exportiert.

#### <a name="for-a-teacher"></a>Für eine Lehrkraft

Massenexportierung von Aufgabendaten funktioniert für Kursteilnehmer auf die gleiche Weise, aber alle Übermittlungen, auf die der Lehrer Zugriff hat, werden exportiert.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Massenlöschen von Zuordnungsdaten außerhalb SharePoint Dokumentbibliotheken

#### <a name="for-a-student"></a>Für einen Kursteilnehmer

Zum Massenlöschen der Daten eines einzelnen Kursteilnehmers führen Sie vor [](/microsoft-365/education/deploy/configure-assignments-for-teams) dem Entfernen des Kursteilnehmers aus den Kursen, an dem er teil hat, das Skript aus, und stellen Sie das -Element zur ``userId`` Verfügung. Wenn der Kursteilnehmer von der Website entfernt wurde, kann entweder der Administrator den Kursteilnehmer wieder zum Kurs hinzufügen, bevor er das Skript ausführen, oder der Administrator kann die und die bereitstellen, zu der der Kursteilnehmer jemals gehört ``userId`` ``classId`` hat.

Wenn Sie ein -Element bereitstellen, kann der Administrator nur Informationen ``ClassId`` über den Kursteilnehmer aus einem bestimmten Kurs löschen.

#### <a name="for-a-teacher"></a>Für eine Lehrkraft

Da die Daten einer Aufgabe für einen Lehrer im Kurs freigegeben werden, gibt es keine Option zum Massenlöschen. Stattdessen kann sich der Administrator selbst zur -Klasse hinzufügen, zur App wechseln und die Aufgabe löschen.

Weitere Informationen finden Sie unter [Konfigurieren von Aufgaben für Teams.](/microsoft-365/education/deploy/configure-assignments-for-teams)

## <a name="removing-assignments-and-grades"></a>Entfernen von Aufgaben und Noten

Sie können auch die Teams verwenden, um Zuweisungen und Noten für einen bestimmten Benutzer oder für Ihren gesamten Mandanten zu entfernen.

Um Aufgaben und Noten für einen einzelnen Benutzer zu entfernen, wechseln Sie zum **Teams Admin Center,** und navigieren Sie zu Teams Apps **> Berechtigungsrichtlinien,** um eine neue Definition der App-Berechtigungsrichtlinie zu erstellen.  Legen Sie beim Erstellen der neuen Richtliniendefinition die **Richtlinie für Microsoft-Apps** auf Bestimmte Apps blockieren und alle anderen Apps blockieren sowie Zuweisungen zur Liste der blockierten Anwendungen hinzu.   Nachdem Sie die neue Richtliniendefinition gespeichert haben, weisen Sie sie den entsprechenden Benutzern zu.

Wenn Sie Aufgaben und Noten für den gesamten Mandanten entfernen möchten, wechseln Sie zum **Teams Admin Center**,  navigieren Sie zu **Teams-Apps >** Apps verwalten , und suchen Sie in der Anwendungsliste nach Aufgaben, und wählen Sie sie aus. Ändern Sie die Statuseinstellung auf der Seite Einstellungen der Aufgabenanwendung in _Blockiert._
