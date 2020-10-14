---
title: Verwenden von OneDrive und SharePoint für Besprechungsaufzeichnungen
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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444231"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Die Änderung von der Verwendung von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen ist ein Phasen orientierter Ansatz.

|||
|---|-----------------|
|Datum|Ereignis|
|Frühes Q4 CY20|**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint, die für Opt-in oder Opt-out verfügbar sind.**<br> Mandantenadministratoren können die OneDrive for Business-und SharePoint-Einstellungen für die Team Richtlinie in PowerShell aktivieren oder deaktivieren.|
|Mid Q4 CY20|**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint als Standardeinstellung für Mandanten, die sich nicht abmelden**<br> Dies ist der empfohlene Pfad für die meisten Kunden.|
Q1 CY21|**Speichern der Besprechungsaufzeichnung für Teams im klassischen Datenstrom nicht mehr zulässig**<br>Alle Mandanten speichern die Besprechungsaufzeichnung für Teams in OneDrive for Business und SharePoint.|
|||

Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase des Übergangs vom klassischen Microsoft-Stream auf den [neuen Datenstrom](https://docs.microsoft.com/stream/streamnew/new-stream)speichert diese Methode Aufnahmen auf Microsoft OneDrive und SharePoint in Microsoft 365 und bietet zahlreiche Vorteile.

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

1. Installieren Sie die PowerShell-Verwaltungskonsole von Skype for Business Online.

    a. Laden Sie [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)herunter.

    b. Folgen Sie den Anweisungen, um Sie zu installieren.

    c. Starten Sie Ihren Computer neu.

2. Starten von PowerShell als Administrator

3. Importieren Sie den SkypeOnline-Connector, und melden Sie sich als Teamadministrator an.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. Verwenden Sie " [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) ", um eine Team-Besprechungsrichtlinie für den Übergang vom Datenstrom Speicher auf ODSP einzurichten.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Deaktivieren von OneDrive for Business und SharePoint, um den Datenstrom weiterhin verwenden zu können

Auch wenn eine Richtlinie besagt, dass Sie auf **Stream**eingestellt ist, ist Sie möglicherweise nicht eingestellt. In der Regel ist die Standardeinstellung **Stream**, wenn die Richtlinie nicht festgelegt ist. Wenn Sie jedoch die Verwendung von SharePoint oder OneDrive deaktivieren möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass Sie die Standardeinstellung ist, wenn Sie diese neue Änderung verwenden möchten.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo werden die Besprechungsaufzeichnungen gespeichert?**

- Bei nicht Kanal Besprechungen wird die Aufzeichnung in einem Ordner mit dem Namen **Aufzeichnungen** gespeichert, der sich auf der obersten Ebene des OneDrive befindet, das der Person gehört, die die Besprechungsaufzeichnung gestartet hat. Beispiel:

  <i>Recorder-OneDrive for Business</i> / **Aufnahmen**

- Bei Kanal Besprechungen wird die Aufzeichnung in der Bibliothek "Teams-Website Dokumentation" in einem Ordner mit dem Namen " **Aufzeichnungen**" gespeichert. Beispiel:

  <i>Name des Teams – Kanalname</i> / **Dokumente** / **Aufnahmen**

**Wie behandle ich Aufnahmen von ehemaligen Mitarbeitern?**

Da Videos genauso wie jede andere Datei in OneDrive und SharePoint sind, folgt die Behandlung von Besitz und Aufbewahrung nach dem Verlassen eines Mitarbeiters dem normalen [OneDrive-und SharePoint-Prozess]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**Wer hat die Berechtigung zum Anzeigen der Besprechungsaufzeichnung?**

- Für Besprechungen ohne Kanal wird für alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch ein Link persönlich freigegeben abgerufen. Externe Benutzer müssen explizit der freigegebenen Liste vom Besprechungsorganisator oder der Person hinzugefügt werden, die die Besprechungsaufzeichnung gestartet hat.

- Bei Kanal Besprechungen werden Berechtigungen von der Liste Besitzer und Mitglieder des Kanals geerbt.

**Wie kann ich Protokolle verwalten?**

Kunden, die sich für diese Vorschau entscheiden, stehen in Ihren Team-Besprechungsaufzeichnungen, die zu OneDrive und SharePoint migriert werden, keine Untertitel zur Verfügung.Wir arbeiten daran, Beschriftungen hinzuzufügen, beginnend mit Untertiteln in Englisch, bis zu Besprechungsaufzeichnungen im Oktober 2020.

In Teams-Besprechungsaufzeichnungen stehen Untertitel für Kunden zur Verfügung, die sich für das Zulassen von Abschriften entschieden haben, wie in [Teams Cloud-Aufzeichnungen](cloud-recording.md) beschrieben

Beschriftungen tragen dazu bei, den Betrachter aller Fähigkeiten inklusiven Inhalt zu erstellen. Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Aufzeichnung weiterhin für Teams verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams. Informationen [zum Aktivieren oder Deaktivieren von Besprechungsaufzeichnungen](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Untertitel werden für Teams-Besprechungsaufzeichnungen für 60 Tage ab dem Zeitpunkt, zu dem die Besprechung aufgezeichnet wird, unterstützt.

**Auswirkungen auf das Speicherkontingent**

Teams, die Dateien aufzeichnen, Leben in OneDrive for Business und SharePoint und sind in Ihrem Kontingent für diese Dienste enthalten. Siehe [SharePoint-Kontingent](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**Wie kann ich eine Besprechungsaufzeichnung für Teams wiedergeben?**

Ihr Video wird auf dem Video Player von OneDrive for Business oder SharePoint wiedergegeben, je nachdem, wo Sie auf die Datei zugreifen.

**Wenn Sie beabsichtigen, das Hinzufügen zu Datenstrom zu verwerfen, bleiben die vorhandenen Videos unverändert und für wie lange?**

Stream als Plattform wird in naher Zukunft nicht mehr als veraltet markiert. Die Videos, die aktuell in Stream vorhanden sind, bleiben dort, bis wir mit der Migration beginnen. Bei der Migration werden diese Videos ebenfalls nach ODSP migriert. Weitere Informationen finden Sie [hier](https://docs.microsoft.com/stream/streamnew/classic-migration) .
