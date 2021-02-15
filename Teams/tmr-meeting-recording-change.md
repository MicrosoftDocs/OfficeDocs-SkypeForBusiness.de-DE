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
description: 'Erfahren Sie, wie Sie in Microsoft Teams vom Stream zum OneDrive for Business- und #A0 wechseln.'
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3172250c1bf6fe914c331712db74a83ebe98a6d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196349"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Der Wechsel von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen ist ein phasenweiser Ansatz.

|<div style="width:290px">Datum&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Ereignis&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5. Oktober 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Sie können die #A0 aktivieren, damit Besprechungsaufzeichnungen in OneDrive for Business und SharePoint statt in Microsoft Stream (klassisch) gespeichert werden|
|Roll out starting January 7, 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Alle neuen #A0 werden auf OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die #A1 Ihrer Organisation ändern und explizit auf **Stream festlegen.** Die Richtlinienberichterstattung als Stream zu sehen, reicht nicht aus. Sie müssen den Richtlinienwert explizit auf Stream **festlegen.**|
|Roll out starting January 11, 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC**<br> Während Kunden von GCC ab dem 5. Oktober die Option abmelden können, können Sie sich nicht mehr dafür entscheiden. Dieses Feature wird ab dem 11. Januar 2021 für alle Kunden von GCC zur Verfügung stellen, es sei denn, Sie haben sich abmelden müssen.<br>  <br>Ab dem 11. Januar 2021 werden alle neuen #A0 für #A1 auf OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die #A2 Ihrer Organisation ändern und explizit auf **Stream** festlegen. <br><br>Wenn Sie sich abmelden, aber bereit sind, dieses Feature zu aktivieren, können Sie dies tun, indem Sie Ihre #A0 explizit auf **OneDrive for Business festlegen.** |
|Roll out starting March 1, 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Kunden von Enterprise & GCC**<br>In **Microsoft Stream (klassisch)** können keine neuen Besprechungsaufzeichnungen gespeichert werden. Alle Kunden haben Besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint gespeichert, auch wenn sie ihre #A0 in Stream geändert haben.<br><br> Es wird empfohlen, dass Kunden dieses Feature vor diesem Datum rollouten, damit sie den Zeitlichen Ablauf der Veröffentlichung steuern können. |
|Roll out starting July 7, 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Kunden von Education**<br>In **Microsoft Stream (klassisch)** können keine neuen Besprechungsaufzeichnungen gespeichert werden. Alle Kunden haben besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint gespeichert, auch wenn sie ihre #A0 in Stream geändert haben.<br><br> Es wird empfohlen, dass Kunden dieses Feature vor diesem Datum rollouten, damit sie die Anzeigedauer der Veröffentlichung steuern können. Wir haben diesen Zeitplan aktualisiert, um Bildungskunden die Möglichkeit zu bieten, in Bearbeitungssemester zu beginnen. |

> [!Note]
> Wir empfehlen Unternehmens- und Bildungskunden, sich für eine bessere Steuerung der Änderung in Ihrer Organisation zu entscheiden, wenn Sie mit der Änderung komfortabel sind, anstatt warten zu müssen.

Microsoft Teams verfügt über eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase des Übergangs vom klassischen Microsoft Stream zum neuen [Stream](https://docs.microsoft.com/stream/streamnew/new-stream)speichert diese Methode Aufzeichnungen auf Microsoft OneDrive for Business und SharePoint in Microsoft 365 und bietet viele Vorteile.

Die Verwendung von OneDrive for Business und SharePoint zum Speichern von Aufzeichnungen bietet folgende Vorteile:

- Aufbewahrungsrichtlinien für #A0 (TMR) (S+C E5-Beschriftungen)
- Vorteile der OneDrive for Business- und #A0
- Einfaches Festlegen von Berechtigungen und Freigeben
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) nur mit expliziter Freigabe
- Anfordern des Zugriffsflusses
- Bereitstellen freigegebener OneDrive for Business- und #A0
- Höheres Kontingent
- Besprechungsaufzeichnungen sind schneller verfügbar
- **Support für lokale** Mandanten
- Unterstützung für mehrere Geos – Aufzeichnungen werden in einer Region gespeichert, die für diesen Benutzer spezifisch ist.
- Bringen Sie Ihren eigenen Schlüssel (BYOK)-Support mit

Es gibt einige Einschränkungen, die Sie berücksichtigen sollten:

- Es gibt nur englische Untertitel, und Sie können Beschriftungen deaktivieren/einschalten.
- Sie können *zunächst* keine vollständigen Aufzeichnungen anzeigen, bearbeiten und durchsuchen (wir arbeiten jedoch daran, diese Funktion in Kürze hinzufügen).
- Sie können die Aufzeichnungen nicht bearbeiten, aber Sie können Beschriftungen deaktivieren/einschalten.
- Sie können steuern, für wen Sie die Aufzeichnung freigeben, aber Sie können das Herunterladen der Aufzeichnung für Personen mit freigegebenen Zugriffen nicht blockieren.
- Sie erhalten keine E-Mail, wenn das Speichern der Aufzeichnung abgeschlossen ist, aber die Aufzeichnung wird im Besprechungschat angezeigt, sobald sie abgeschlossen ist. Dies geschieht viel schneller als zuvor in Stream.

Weitere Informationen finden Sie unter "Besprechungsaufzeichnung".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Einrichten der Option "Besprechungsaufzeichnung" für OneDrive for Business und SharePoint

Die Option "Besprechungsaufzeichnung" ist eine Einstellung auf Der Richtlinienebene von Teams. Das folgende Beispiel zeigt, wie Sie die globale Richtlinie festlegen. Stellen Sie sicher, dass Sie die Option "Besprechungsaufzeichnung" für die Richtlinie oder Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.

> [!Note]
> Es dauert eine Weile, bis Die Änderungen an der Besprechungsrichtlinie in Teams weitervererbt wurden. Schauen Sie nach ein paar Stunden nach der Einstellung wieder nach, melden Sie sich ab, und melden Sie sich erneut an.

1. Installieren Sie Skype for Business Online PowerShell.
**Hinweis:** Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls. Wenn Sie die neueste öffentliche Version von Teams PowerShell verwenden, müssen Sie Skype for Business Online Connector nicht installieren. Weitere [Informationen finden Sie unter "Verwalten von Skype for Business Online mit PowerShell".](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. Laden [Sie Skype for Business Online PowerShell herunter.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. Folgen Sie den Anweisungen, um die App zu installieren.

    c. Starten Sie den Computer neu.

2. Starten von PowerShell als Administrator

3. Importieren Sie SkypeOnline Connector, und melden Sie sich als Teamadministrator an.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Verwenden [Sie Set-CsTeamsMeetingPolicy,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) um eine #A0 für den Übergang vom Streamspeicher zu OneDrive for Business und SharePoint festlegen.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Wenn einige Ihrer Benutzer eine Richtlinie pro Organisator oder pro Benutzer zugewiesen haben, müssen Sie diese Einstellung für diese Richtlinie festlegen, wenn sie möchten, dass diese auch die Besprechungsaufzeichnungen in OneDrive for Business und SharePoint speichern. Weitere Informationen finden Sie unter ["Verwalten von Besprechungsrichtlinien in Teams".](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>OneDrive for Business und SharePoint abmelden, um Stream weiterhin zu verwenden

Selbst wenn eine Richtlinie sagt, dass sie auf **Stream festgelegt ist,** ist sie möglicherweise nicht festgelegt. Wenn die Richtlinie nicht festgelegt ist, ist die Standardeinstellung **normalerweise** Stream. Wenn Sie jedoch bei dieser neuen Änderung die Verwendung von SharePoint oder OneDrive for Business melden möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass **Stream** die Standardeinstellung ist.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Berechtigungen oder rollenbasierter Zugriff

> [!Note]
> Wir empfehlen, dass der Empfänger beim Freigeben von Team-Besprechungsaufzeichnungen ein angemeldeter Benutzer sein muss. Wählen Sie **die Option "Personen in (Ihrer Organisation)"** aus, wenn Sie die Datei so freigeben, wie sie in SharePoint-Dateien oder [-Ordnern dokumentiert ist.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) Die externe Freigabe ist nicht für die Verteilung großer Dateien oder einer großen Anzahl von Dateien ausgelegt. Um Betrugs- und Missbrauchsszenarien zu verhindern, können Probleme auftreten, wenn Sie große Datenmenge für externe Benutzer freigeben.

|Besprechungstyp                               | Wer hat auf "Datensatz" geklickt?| Wo wird die Aufzeichnung landen?                               |Wer hat Zugriff? R/W, R oder Freigabe                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und besitzt alle Rechte. <br /><br />Der Anrufer (in demselben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br /> Der Anrufer (wenn er sich in einem anderen Mandanten ausdingt) hat keinen Zugriff. Der Anrufer muss ihn an den Anrufer freigeben.|
|1:1-Anruf mit internen Parteien             |Callee                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und besitzt alle Rechte. <br /><br />Anrufer (wenn der gleiche Mandant über schreibgeschützten Zugriff verfügt. Kein Freigabezugriff. <br /><br />Der Anrufer (wenn er sich in einem anderen Mandanten ausdingt) hat keinen Zugriff. Der Anrufer muss ihn dem Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und besitzt alle Rechte.<br /> <br />Der Anrufer hat keinen Zugriff. Der Anrufer muss ihn an den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Callee                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und besitzt alle Rechte.<br /><br />Der Anrufer hat keinen Zugriff. Der Anrufer muss es dem Anrufer freigeben.|
|Gruppenanruf                                 |Ein beliebiges Gesprächsmitglied |Mitglied, das auf das OneDrive for #A0 des Datensatzes geklickt hat  |Mitglied, das auf "Datensatz" geklickt hat, hat die vollen Rechte. <br /><br /> Andere Mitglieder aus demselben Mandanten verfügen über Leserechte. <br /><br /> Andere Mitglieder aus einem anderen Mandanten haben keine Rechte.|
|Adhoc/Scheduled meeting                    |Organisator              |OneDrive for #A0 des Organisators                     |Der Organisator hat alle Rechte auf die Aufzeichnung. <br /><br /> Alle anderen Besprechungsmitglieder haben Lesezugriff.|
|Adhoc/Scheduled meeting                    |Anderes Besprechungsmitglied   |Mitglied, das auf "Datensatz" geklickt hat                                  |Das Mitglied, das auf "Datensatz" geklickt hat, verfügt über vollständige Rechte für die Aufzeichnung. <br /><br />Der Organisator hat Bearbeitungsrechte und kann freigeben.<br /><br /> Alle anderen Mitglieder haben Lesezugriff.|
|Adhoc/Scheduled meeting with external users|Organisator              |OneDrive for #A0 des Organisators                     |Der Organisator hat alle Rechte auf die Aufzeichnung.<br /> <br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator haben Lesezugriff. <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Adhoc/Scheduled meeting with external users|Anderes Besprechungsmitglied   |Mitglied, das auf "Datensatz" geklickt hat                                  |Das Mitglied, das auf "Datensatz" geklickt hat, verfügt über vollständige Rechte für die Aufzeichnung. Der Organisator hat Bearbeitungsrechte und kann freigeben. <br /><br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator haben Lesezugriff. <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Kanal-Besprechung                            |Kanalmitglied         |Der SharePoint-Speicherort von Teams für diesen Kanal                   |Das Mitglied, das auf "Datensatz" geklickt hat, hat Bearbeitungsrechte für die Aufzeichnung. <br /> <br />Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint-Kanalberechtigungen.|

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo wird die Besprechungsaufzeichnung gespeichert?**

- Bei Besprechungen außerhalb des Kanals wird  die Aufzeichnung in einem Ordner namens "Aufzeichnungen" gespeichert, der sich auf der obersten Ebene von OneDrive for Business befindet und zu der Person gehört, die die Besprechungsaufzeichnung gestartet hat. Beispiel:

  <i>OneDrive for Business</i> / von Recorder **Aufzeichnungen**

- Bei Kanalbesprechungen wird die Aufzeichnung in der Dokumentationsbibliothek der Website von Teams in einem Ordner namens **"Aufzeichnungen" gespeichert.** Beispiel:

  <i>Name von Teams – Kanalname</i> / **Dokumente** / **Aufzeichnungen**

**Wie wird entschieden, wo sich Streamdateien (z. B. Aufzeichnungen) in SharePoint/OneDrive befinden? Hat der Administrator die Möglichkeit, den Zielbereich zu ändern?**

Standardmäßig werden alle Aufzeichnungsdateien an das #A0 des Benutzers übertragen, der **"Aufzeichnen" ausgewählt hat.** Bei Kanalbesprechungen wird die Aufzeichnung immer auf die SharePoint-Website des Kanals übertragen. Der Administrator kann nicht ändern, wo die Aufzeichnung gespeichert ist.

**Wie behandle ich Aufzeichnungen von ehemaligen Mitarbeitern?**

Da Videos wie jede andere Datei in OneDrive for Business und SharePoint aussehen, wird beim Behandeln von Besitz und Aufbewahrung, nachdem ein Mitarbeiter das Unternehmen verlässt, der normale [OneDrive for Business-]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)und #A0 verwendet.

**Wer verfügt über die Berechtigungen zum Anzeigen der Besprechungsaufzeichnung?**

- Bei Besprechungen außerhalb des Kanals erhalten alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch einen persönlich freigegebenen Link. Externe Benutzer müssen der freigegebenen Liste vom Besprechungsorganisator oder der Person, die die Besprechungsaufzeichnung gestartet hat, explizit hinzugefügt werden.

- Bei Kanalbesprechungen werden Berechtigungen von der Besitzer- und Mitgliederliste im Kanal geerbt.

**Wie kann ich Transkriptionen verwalten?**

Kunden, die sich für diese Vorschau entscheiden, stehen in ihren Teambesprechungsaufzeichnungen, die nach OneDrive for Business und SharePoint migriert werden, nicht mit Untertiteln zur Verfügung.Wir arbeiten daran, Den Besprechungsaufzeichnungen in Q4 CY2020 Untertitel ( beginnend mit Untertiteln in Englisch) hinzuzufügen.

Für Kunden, die sich angemeldet haben, Transkription zu erlauben, wie in den Cloudaufzeichnungen von Teams beschrieben, stehen Untertitel für Teams Meeting Recordings [zur Verfügung.](cloud-recording.md)

Mithilfe von Beschriftungen können Sie integrative Inhalte für Benutzer mit allen Fähigkeiten erstellen. Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Aufzeichnung in Teams weiterhin verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams. Erfahren [Sie, wie Sie Besprechungsaufzeichnungen aktivieren oder deaktivieren.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Für Aufzeichnungen von Teambesprechungen werden Untertitel 60 Tage ab dem Tag der Aufzeichnung der Besprechung unterstützt.

Untertitel werden nicht vollständig unterstützt, wenn die #A0 vom ursprünglichen Speicherort auf OneDrive for Business oder SharePoint verschoben oder kopiert wird.

**Wie wirkt sich mein Speicherkontingent aus?**

Teams Meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services. Sehen [Sie sich das #A0](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und das [OneDrive for #A1 an.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Mit [OneDrive for Business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) erhalten Sie mehr Speicher im Vergleich zu Stream und mit SharePoint mehr speicherplatz.

**Wie kann ich eine Aufzeichnung einer Teams-Besprechung wieder geben?**

Ihr Video wird auf dem Videoplayer von OneDrive for Business oder SharePoint abspielen, je nachdem, wo Sie auf die Datei zugreifen.

**Wenn Sie das Hinzufügen zu Stream als veraltet einplanen, bleiben die vorhandenen Videos so, wie es ist und wie lange?**

Streamen als Plattform wird in naher Zukunft nicht mehr unterstützt. Die Videos, die aktuell in Stream laufen, bleiben dort, bis wir mit der Migration beginnen. Bei der Migration werden diese Videos auch nach OneDrive for Business oder SharePoint migriert. Weitere [Informationen finden Sie unter "Klassische Migration](https://docs.microsoft.com/stream/streamnew/classic-migration) von Stream".

**Wie kann ich eine Aufbewahrungsbezeichnung anwenden?**

Informationen [zum automatischen Anwenden einer Aufbewahrungsbezeichnung](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Wie kann ich meinen Benutzern in Microsoft Teams Richtlinien zuweisen, und welche Richtlinien haben Vorrang?**

Sehen Sie [sich an, welche Richtlinie Vorrang hat?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)
