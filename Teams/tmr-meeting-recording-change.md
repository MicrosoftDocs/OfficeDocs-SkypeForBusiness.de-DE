---
title: Verwenden von OneDrive for Business und SharePoint für Besprechungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie von Stream zu OneDrive for Business und SharePoint-Besprechungs Speicher in Microsoft Teams wechseln.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 452976ca2d88225fb239425861e1c97cd58a2b9f
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827749"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Die Änderung von der Verwendung von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen ist ein Phasen orientierter Ansatz.


|Datum|Ereignis|
|---|-----------------|
|Frühes Q4 CY20|**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint, die für Opt-in oder Opt-out verfügbar sind.**<br> Mandantenadministratoren können die OneDrive for Business-und SharePoint-Einstellungen für die Team Richtlinie in PowerShell aktivieren oder deaktivieren.|
|Mid Q4 CY20|**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint als Standardeinstellung für Mandanten, die sich nicht abmelden**<br> Dies ist der empfohlene Pfad für die meisten Kunden.|
|Q1 CY21|**Speichern der Besprechungsaufzeichnung für Teams im klassischen Datenstrom nicht mehr zulässig**<br>Alle Mandanten speichern die Besprechungsaufzeichnung für Teams in OneDrive for Business und SharePoint.|

Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase des Übergangs vom klassischen Microsoft-Stream auf den [neuen Datenstrom](https://docs.microsoft.com/stream/streamnew/new-stream)speichert diese Methode Aufzeichnungen zu Microsoft OneDrive for Business und SharePoint in Microsoft 365 und bietet zahlreiche Vorteile.

Zu den Vorteilen der Verwendung von OneDrive for Business und SharePoint für das Speichern von Aufzeichnungen gehören:

- Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S + C E5-autoaufbewahrungs Etiketten)
- Profitieren Sie von OneDrive for Business und SharePoint-Informations-Governance
- Einfaches Einrichten von Berechtigungen und Freigabe
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) mit expliziter Freigabe
- Zugriffs Fluss anfordern
- Bereitstellen von OneDrive for Business-und SharePoint-freigegebenen Links
- Höhere Kontingente
- Besprechungsaufzeichnungen sind schneller verfügbar
- Support für **lokale** Mandanten
- Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für diesen benutzerspezifischen Region gespeichert.
- Unterstützung für Ihren eigenen Schlüssel (BYOK)
- Verbesserte Transkriptions Qualität und Sprecher Zuordnung

Es gibt einige Einschränkungen, die berücksichtigt werden sollten:

- Es werden nur Englisch-Untertitel und-Transkripte vorhanden sein.
- Sie können keine Transkripte oder deren Inhalt durchsuchen.
- Sie können die Transkripte nicht bearbeiten, aber Sie können die Beschriftungen aus-und einschalten.
- Sie können steuern, mit wem Sie die Aufzeichnung freigeben, aber Sie können Personen mit freigegebenen Zugriff nicht blockieren, indem Sie die Aufzeichnung herunterladen.
- Wenn die Aufzeichnung die Speicherung beendet hat, wird keine e-Mail angezeigt, aber die Aufzeichnung wird nach Abschluss des Besprechungs Chats angezeigt. Dies geschieht viel schneller als in Stream zuvor.

Schauen Sie sich die "Besprechungsaufzeichnung" an, um weitere Informationen zu erhalten.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Einrichten der Option "Besprechungsaufzeichnung" für OneDrive for Business und SharePoint

> [!Note]
> Die Option "Besprechungsaufzeichnung" ist eine Einstellung auf der Richtlinienebene "Teams". Im folgenden Beispiel wird gezeigt, wie die globale Richtlinie eingerichtet wird. Stellen Sie sicher, dass Sie die Option für die Besprechungsaufzeichnung für die Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.
> Änderungen an den Gruppen Besprechungsrichtlinien dauern eine Weile. Schauen Sie nach ein paar Stunden nach der Festlegung zurück, und melden Sie sich erneut an.

1. Installieren Sie Skype for Business Online PowerShell.
**Hinweis** : Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    a. Laden Sie [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)herunter.

    b. Folgen Sie den Anweisungen, um Sie zu installieren.

    c. Starten Sie Ihren Computer neu.

2. Starten von PowerShell als Administrator

3. Importieren Sie den SkypeOnline-Connector, und melden Sie sich als Teamadministrator an.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Verwenden Sie " [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) ", um eine Team-Besprechungsrichtlinie für den Übergang vom Datenstrom Speicher zu OneDrive for Business und SharePoint einzurichten.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Deaktivieren von OneDrive for Business und SharePoint, um den Datenstrom weiterhin verwenden zu können

Auch wenn eine Richtlinie besagt, dass Sie auf **Stream** eingestellt ist, ist Sie möglicherweise nicht eingestellt. In der Regel ist die Standardeinstellung **Stream** , wenn die Richtlinie nicht festgelegt ist. Wenn Sie jedoch die Nutzung von SharePoint oder OneDrive for Business deaktivieren möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass Sie die Standardeinstellung ist.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Berechtigungen oder rollenbasierter Zugriff

|Besprechungstyp                               | Wer hat auf Record geklickt?| Wo landet die Aufzeichnung?                               |Wer hat Zugriff? R/W, r oder Freigabe                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist Besitzer, hat vollständige Rechte <br /><br />Der aufgerufene (im gleichen Mandanten) hat schreibgeschützten Zugriff, keinen Freigabe Zugriff <br /><br /> Der aufgerufene (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss ihn für den aufgerufenen freigeben.|
|1:1-Anruf mit internen Parteien             |Callee                 |OneDrive for Business-Konto des berufenen                        |Der angerufene ist Besitzer, hat vollständige Rechte <br /><br />Anrufer (wenn in demselben Mandanten schreibgeschützter Zugriff, kein Freigabe Zugriff <br /><br />Der Anrufer (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss ihn dem angerufenen freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist Besitzer, hat vollständige Rechte<br /> <br />Der aufgerufene hat keinen Zugriff. Der Anrufer muss ihn für den aufgerufenen freigeben.|
|1:1-Anruf mit einem externen Anruf             |Callee                 |OneDrive for Business-Konto des berufenen                        | Der angerufene ist Besitzer, hat vollständige Rechte<br /><br />Der Anrufer hat keinen Zugriff. Der Anrufer muss ihn an den Anrufer weiterleiten.|
|Gruppenanruf                                 |Ein beliebiges Mitglied des Anrufs |Mitglied, das auf das OneDrive for Business-Konto des Eintrags geklickt hat  |Member, auf den Datensatz geklickt hat, hat vollständige Rechte <br /><br /> Andere Mitglieder desselben Mandanten haben Lese Rechte <br /><br /> Andere Mitglieder eines anderen Mandanten haben keine Rechte daran.|
|Adhoc/geplante Besprechung                    |Organisator              |OneDrive for Business-Konto des Organisators                     | Organizer hat vollständige Rechte an der Aufzeichnung <br /><br /> Alle anderen Mitglieder der Besprechung haben Lesezugriff|
|Adhoc/geplante Besprechung                    |Anderes Besprechungs Mitglied   |Mitglied, das auf Datensatz geklickt hat                                  | Das Mitglied, das auf Record geklickt hat, hat vollständige Rechte an der Aufzeichnung. <br />Organizer hat Bearbeitungsrechte und kann freigeben <br /><br /> Alle anderen Mitglieder haben Lesezugriff|
|Adhoc/geplante Besprechung mit externen Benutzern|Organisator              |OneDrive for Business-Konto des Organisators                     |Organizer hat vollständige Rechte an der Aufzeichnung<br /> <br /> Alle anderen Mitglieder der Besprechung vom gleichen Mandanten wie der Organisator haben Lesezugriff <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss Sie an Sie weitergeben.|
|Adhoc/geplante Besprechung mit externen Benutzern|Anderes Besprechungs Mitglied   |Mitglied, das auf Datensatz geklickt hat                                  | Das Mitglied, das auf Record geklickt hat, hat vollständige Rechte an der Aufzeichnung – Organizer hat Bearbeitungsrechte und kann freigeben <br /><br /> Alle anderen Mitglieder der Besprechung vom gleichen Mandanten wie der Organisator haben Lesezugriff <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss Sie an Sie weitergeben.|
|Kanal Besprechung                            |Kanalmitglied         |SharePoint-Standort des Teams für diesen Kanal                   | Das Mitglied, das auf Record geklickt hat, hat Bearbeitungsrechte für die Aufzeichnung. <br /> <br />Die Berechtigungen aller anderen Mitglieder basieren auf der SharePoint-Kanal Berechtigung|


## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo werden die Besprechungsaufzeichnungen gespeichert?**

- Bei nicht Kanal Besprechungen wird die Aufzeichnung in einem Ordner mit dem Namen **Aufzeichnungen** gespeichert, der sich auf der obersten Ebene des OneDrive for Business befindet, das der Person gehört, die die Besprechungsaufzeichnung gestartet hat. Beispiel:

  <i>Recorder-OneDrive for Business</i> / **Aufnahmen**

- Bei Kanal Besprechungen wird die Aufzeichnung in der Bibliothek "Teams-Website Dokumentation" in einem Ordner mit dem Namen " **Aufzeichnungen** " gespeichert. Beispiel:

  <i>Name des Teams – Kanalname</i> / **Dokumente** / **Aufnahmen**

**Wie behandle ich Aufnahmen von ehemaligen Mitarbeitern?**

Da Videos genauso wie jede andere Datei in OneDrive for Business und SharePoint sind, werden die Behandlung von Besitz und Aufbewahrung nach dem Verlassen eines Mitarbeiters dem normalen [OneDrive for Business-und SharePoint-Prozess]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)folgen.

**Wer hat die Berechtigung zum Anzeigen der Besprechungsaufzeichnung?**

- Für Besprechungen ohne Kanal wird für alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch ein Link persönlich freigegeben abgerufen. Externe Benutzer müssen explizit der freigegebenen Liste vom Besprechungsorganisator oder der Person hinzugefügt werden, die die Besprechungsaufzeichnung gestartet hat.

- Bei Kanal Besprechungen werden Berechtigungen von der Liste Besitzer und Mitglieder des Kanals geerbt.

**Wie kann ich Protokolle verwalten?**

Kunden, die sich für diese Vorschau entscheiden, stehen in ihren Teams-Besprechungsaufzeichnungen, die zu OneDrive for Business und SharePoint migriert werden, keine Untertitel zur Verfügung.Wir arbeiten daran, Beschriftungen hinzuzufügen, beginnend mit Untertiteln in Englisch, bis zu Besprechungsaufzeichnungen im Oktober 2020.

In Teams-Besprechungsaufzeichnungen stehen Untertitel für Kunden zur Verfügung, die sich für das Zulassen von Abschriften entschieden haben, wie in [Teams Cloud-Aufzeichnungen](cloud-recording.md) beschrieben

Beschriftungen tragen dazu bei, den Betrachter aller Fähigkeiten inklusiven Inhalt zu erstellen. Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Aufzeichnung weiterhin für Teams verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams. Informationen [zum Aktivieren oder Deaktivieren von Besprechungsaufzeichnungen](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Untertitel werden für Teams-Besprechungsaufzeichnungen für 60 Tage ab dem Zeitpunkt, zu dem die Besprechung aufgezeichnet wird, unterstützt.

Untertitel werden nicht vollständig unterstützt, wenn die Besprechungsaufzeichnung für Teams von Ihrem ursprünglichen Speicherort auf OneDrive for Business oder SharePoint verschoben oder kopiert wird.

**Auswirkungen auf das Speicherkontingent**

Teams, die Dateien aufzeichnen, Leben in OneDrive for Business und SharePoint und sind in Ihrem Kontingent für diese Dienste enthalten. Siehe [SharePoint-Kontingent](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**Wie kann ich eine Besprechungsaufzeichnung für Teams wiedergeben?**

Ihr Video wird auf dem Video Player von OneDrive for Business oder SharePoint wiedergegeben, je nachdem, wo Sie auf die Datei zugreifen.

**Wenn Sie beabsichtigen, das Hinzufügen zu Datenstrom zu verwerfen, bleiben die vorhandenen Videos unverändert und für wie lange?**

Stream als Plattform wird in naher Zukunft nicht mehr als veraltet markiert. Die Videos, die aktuell in Stream vorhanden sind, bleiben dort, bis wir mit der Migration beginnen. Bei der Migration werden diese Videos auch nach OneDrive for Business oder SharePoint migriert. Weitere Informationen finden Sie [hier](https://docs.microsoft.com/stream/streamnew/classic-migration) .

**Wie kann ich eine Aufbewahrungs Bezeichnung anwenden?**

Hier erfahren Sie [, wie Sie eine Aufbewahrungs Beschriftung automatisch anwenden](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).
