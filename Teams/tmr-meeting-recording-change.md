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
description: Erfahren Sie, wie Sie in Microsoft Teams von Stream zu OneDrive for Business- und SharePoint-Aufzeichnungsspeicher wechseln.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0431b7ebd385f2ad17d659e238f54b4ebb1ab20a
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569091"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Die Umstellung von Microsoft Stream auf OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen ist ein phasenweiser Ansatz.

|<div style="width:290px">Datum&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Ereignis&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5. Oktober 2020<br> <br>*(Abgeschlossen)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Sie aktivieren die #A0 zum Speichern von Besprechungsaufzeichnungen auf OneDrive for Business und SharePoint anstelle von Microsoft Stream (Klassisch)|
|Roll out ab 7. Januar 2021<br> <br>*(Abgeschlossen)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Alle neuen #A0 werden in OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Richtlinien für #A1 Ihrer Organisation ändern und explizit auf **Stream festlegen.** Die Richtlinienberichterstattung als Stream zu sehen, reicht nicht aus. Sie müssen den Richtlinienwert explizit auf **Stream festlegen.**|
|Roll out ab dem 11. Januar 2021<br> <br>*(Abgeschlossen)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC**<br> Während GCC-Kunden ab dem 5. Oktober abmelden können, können Sie sich nicht mehr dafür entscheiden. Dieses Feature wird ab dem 11. Januar 2021 für alle GCC-Kunden ausgeführt, es sei denn, Sie haben sich entschieden.<br>  <br>Ab dem 11. Januar 2021 werden alle neuen #A0 für #A1 in OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Teams-Besprechungsrichtlinien Ihrer Organisation ändern und explizit auf **Stream festlegen.** <br><br>Wenn Sie sich entschieden haben, aber bereit sind, dieses Feature zu aktivieren, können Sie dies tun, indem Sie Ihre #A0 explizit auf **OneDrive for Business festlegen.** |
|Roll out ab 1. März 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC-High und DoD**<br> Kunden können jetzt zum ersten Mal In-Cloud-Besprechungsaufzeichnungen in ihren Microsoft Teams aktivieren. Diese Aufzeichnungen werden standardmäßig auf OneDrive und SharePoint gespeichert und abgespielt. |
|Schrittweises Roll out ab dem 7. Juli 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br>Es können keine neuen Besprechungsaufzeichnungen in **Microsoft Stream (Classic)** gespeichert werden. Alle Kunden haben Besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint gespeichert, auch wenn sie ihre #A0 in Stream geändert haben.<br><br> Wir empfehlen Kunden, dieses Feature vor diesem Datum zu veröffentlichen, damit sie den Zeitpunkt der Veröffentlichung steuern können. |

> [!Note]
> Wir empfehlen Unternehmens- und Bildungskunden, sich für eine bessere Kontrolle der Änderung in Ihrer Organisation zu entscheiden, wenn Sie mit der Änderung gut zu verstehen sind, anstatt zu warten, bis die Änderung vor sich geht.

Microsoft Teams verfügt über eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase eines Übergangs von klassischem Microsoft Stream zum neuen [Stream](https://docs.microsoft.com/stream/streamnew/new-stream)speichert diese Methode Aufzeichnungen auf Microsoft OneDrive for Business und SharePoint in Microsoft 365 und bietet viele Vorteile.

Zu den Vorteilen der Verwendung von OneDrive for Business und SharePoint zum Speichern von Aufzeichnungen zählen:

- Aufbewahrungsrichtlinien für #A0 (TMR) (S+C E5-Autoretentionsbeschriftungen)
- Profitieren Sie von oneDrive for Business und SharePoint Information Governance
- Einfaches Festlegen von Berechtigungen und Freigaben
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) nur mit expliziter Freigabe
- Anfordern des Zugriffsflusses
- Bereitstellen freigegebener OneDrive for Business- und SharePoint-Links
- Besprechungsaufzeichnungen sind schneller verfügbar
- **Support für lokale** Mandanten
- Multi-Geo-Unterstützung – Aufzeichnungen werden in einer bestimmten Region für diesen Benutzer gespeichert.
- Bring your own key (BYOK) support

Es gibt einige Einschränkungen, die Sie berücksichtigen sollten:

- Es gibt nur englische Untertitel, und Sie können Beschriftungen deaktivieren/einschalten.
- Sie können *zunächst* keine vollständige Transkription anzeigen, bearbeiten und durchsuchen (wir arbeiten jedoch bald daran, diese Funktion zu hinzufügen).
- Sie können die Transkripte nicht bearbeiten, aber Sie können Beschriftungen deaktivieren/einschalten.
- Sie können steuern, für wen Sie die Aufzeichnung freigeben, aber Sie können nicht blockieren, dass Personen mit geteilten Zugriff die Aufzeichnung herunterladen.
- Wenn die Aufzeichnung mit dem Speichern abgeschlossen ist, erhalten Sie keine E-Mail, aber die Aufzeichnung wird im Besprechungschat angezeigt, sobald sie abgeschlossen ist. Dies geschieht viel schneller als zuvor in Stream.

Weitere Informationen finden Sie unter "Besprechungsaufzeichnung".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Einrichten der Option für die Besprechungsaufzeichnung für OneDrive for Business und SharePoint

Die Option für die Besprechungsaufzeichnung ist eine Einstellung auf Der Richtlinienebene von Teams. Im folgenden Beispiel wird gezeigt, wie Die globale Richtlinie festgelegt wird. Stellen Sie sicher, dass Sie die Option für die Besprechungsaufzeichnung für die Richtlinien oder Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.

> [!Note]
> Änderungen an den Besprechungsrichtlinien von Teams dauern eine Weile, bis sie weitervererbt werden. Schauen Sie nach ein paar Stunden nach dem Festlegen zurück, melden Sie sich ab, und melden Sie sich erneut an.

1. Installieren Sie Teams PowerShell PowerShell.

   > [!NOTE]
   > Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls. Wenn Sie die neueste öffentliche Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online Connector nicht installieren. Weitere [Informationen finden Sie unter Verwalten von Skype for Business Online mit PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

1. Starten Sie PowerShell als Administrator.

2. Installieren [Des Teams PowerShell-Moduls](https://docs.microsoft.com/microsoftteams/teams-powershell-install).

3. Importieren Sie das MicrosoftTeams-Modul, und melden Sie sich als Microsoft Teams-Administrator an.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

4. Verwenden [Sie Set-CsTeamsMeetingPolicy,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) um eine #A0 für den Übergang vom Streamspeicher zu OneDrive for Business und SharePoint zu festlegen.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Wenn einige Ihrer Benutzer eine Richtlinie pro Organisator oder Benutzer zugewiesen haben, müssen Sie diese Einstellung für diese Richtlinie festlegen, wenn sie die Besprechungsaufzeichnungen auch in OneDrive for Business und SharePoint speichern möchten. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Opt out of OneDrive for Business and SharePoint to continue using Stream

Selbst wenn eine Richtlinie sagt, dass sie auf **Stream festgelegt ist,** ist sie möglicherweise nicht festgelegt. Wenn die Richtlinie nicht festgelegt ist, ist die Standardeinstellung normalerweise **Stream**. Wenn Sie sich bei dieser neuen Änderung jedoch für die Verwendung von SharePoint oder OneDrive for Business entscheiden möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass **Stream** die Standardeinstellung ist.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Berechtigungen oder rollenbasierter Zugriff

> [!Note]
> Wir empfehlen, dass der Empfänger ein angemeldeter Benutzer sein muss, wenn er Teams-Besprechungsaufzeichnungen teilt. Wählen Sie **die Option Personen in (Ihre Organisation)** aus, wenn Sie die Datei wie in Share SharePoint-Dateien oder -Ordnern dokumentiert [freigeben.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) Die externe Freigabe ist nicht für die Verteilung großer Dateien oder einer großen Anzahl von Dateien ausgelegt. Um Betrugs- und Missbrauchsszenarien zu verhindern, können Probleme beim Freigeben einer großen Datenmenge für externe Benutzer auftreten.

|Besprechungstyp                               | Wer hat auf Datensatz geklickt?| Wo landet die Aufzeichnung?                               |Wer hat Zugriff? R/W, R oder Freigabe                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und hat alle Rechte. <br /><br />Der Anrufer (wenn er im gleichen Mandanten ist) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br /> Der Anrufer (falls in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss ihn für den Anrufer freigeben.|
|1:1-Anruf mit internen Parteien             |Callee                 |OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist Besitzer und hat alle Rechte. <br /><br />Anrufer (wenn der gleiche Mandant schreibgeschützt ist. Kein Freigabezugriff. <br /><br />Der Anrufer (falls in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss ihn für den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |OneDrive for #A0 des Anrufers                        |Der Anrufer ist Besitzer und hat alle Rechte.<br /> <br />Der Anrufer hat keinen Zugriff. Der Anrufer muss ihn für den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Callee                 |OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist Besitzer und hat alle Rechte.<br /><br />Der Anrufer hat keinen Zugriff. Der Anrufer muss ihn für den Anrufer freigeben.|
|Gruppenanruf                                 |Beliebiges Mitglied des Anrufs |Gruppenmitglied, das auf das OneDrive for #A0 des Datensatzes geklickt hat  |Mitglied, das auf Datensatz geklickt hat, hat alle Rechte. <br /><br /> Andere Fr aus demselben Mandanten verfügen über Leserechte. <br /><br /> Andere Gruppenmitglieder aus unterschiedlichen Mandanten haben keine Rechte.|
|Adhoc/Geplante Besprechung                    |Organisator              |OneDrive for #A0 des Organisators                     |Der Organisator hat alle Rechte an der Aufzeichnung. <br /><br /> Alle anderen Mitglieder der Besprechung haben Lesezugriff.|
|Adhoc/Geplante Besprechung                    |Anderes Besprechungsmitglied   |Besprechungsmitglied, das auf Datensatz geklickt hat                                  |Mitglied, das auf Datensatz geklickt hat, hat alle Rechte an der Aufzeichnung. <br /><br />Organizer verfügt über Bearbeitungsrechte und kann freigeben.<br /><br /> Alle anderen Besprechungsmitglieder haben Lesezugriff.|
|Adhoc/Geplante Besprechung mit externen Benutzern|Organisator              |OneDrive for #A0 des Organisators                     |Der Organisator hat alle Rechte an der Aufzeichnung.<br /> <br /> Alle anderen Mitglieder der Besprechung aus demselben Mandanten wie der Organisator haben Lesezugriff. <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Adhoc/Geplante Besprechung mit externen Benutzern|Anderes Besprechungsmitglied   |Mitglied, das auf Datensatz geklickt hat                                  |Mitglied, das auf Datensatz geklickt hat, hat alle Rechte an der Aufzeichnung. Organizer verfügt über Bearbeitungsrechte und kann freigeben. <br /><br /> Alle anderen Mitglieder der Besprechung aus demselben Mandanten wie der Organisator haben Lesezugriff. <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Kanal-Besprechung                            |Kanalmitglied         |Der SharePoint-Speicherort von Teams für diesen Kanal                   |Mitglied, das auf Aufzeichnen geklickt hat Bearbeitungsrechte für die Aufzeichnung. <br /> <br />Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint-Kanalberechtigungen.|

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo wird die Besprechungsaufzeichnung gespeichert?**

- Bei Besprechungen außerhalb des Kanals wird  die Aufzeichnung in einem Ordner namens Aufzeichnungen gespeichert, der sich auf der obersten Ebene von OneDrive for Business befindet, der zu der Person gehört, die die Besprechungsaufzeichnung gestartet hat. Beispiel:

  <i>OneDrive for Business des Recorders</i> / **Aufzeichnungen**

- Bei Kanalbesprechungen wird die Aufzeichnung in der Dokumentationsbibliothek der Teams-Website in einem Ordner namens **Aufzeichnungen gespeichert.** Beispiel:

  <i>Name von Teams – Kanalname</i> / **Dokumente** / **Aufzeichnungen**

**Wie wird entschieden, wohin Die Streamdateien (z. B. Aufzeichnungen) in SharePoint/OneDrive gespeichert werden? Hat der Administrator die Möglichkeit, den Ort des Wechsels zu ändern?**

Standardmäßig werden alle Aufzeichnungsdateien zum OneDrive-Konto des Benutzers verwendet, der Aufzeichnen **ausgewählt hat.** Bei Kanalbesprechungen wird die Aufzeichnung immer zur SharePoint-Website des Kanals verwendet. Der Administrator kann nicht ändern, wo die Aufzeichnung gespeichert ist.

**Wie verhandle ich Aufzeichnungen von ehemaligen Mitarbeitern?**

Da Videos wie jede andere Datei in OneDrive for Business und SharePoint sind, folgt die Behandlung von Besitz und Aufbewahrung nach dem Auszug eines Mitarbeiters dem normalen [OneDrive for Business- und SharePoint-Prozess.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Wer verfügt über die Berechtigungen zum Anzeigen der Besprechungsaufzeichnung?**

- Bei Besprechungen außerhalb des Kanals erhalten alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch einen persönlich freigegebenen Link. Externe Benutzer müssen vom Besprechungsorganisator oder der Person, die die Besprechungsaufzeichnung gestartet hat, explizit zur freigegebenen Liste hinzugefügt werden.

- Bei Kanalbesprechungen werden Berechtigungen von der Besitzer- und Mitgliederliste im Kanal geerbt.

**Wie kann ich Transkripte verwalten?**

Kunden, die sich für diese Vorschau entscheiden, verfügen nicht über Untertitel für ihre Teams-Besprechungsaufzeichnungen, die zu OneDrive for Business und SharePoint migriert werden.Wir arbeiten daran, Beschriftungen, beginnend mit Untertiteln in Englisch, zu Besprechungsaufzeichnungen in Q4 CY2020 hinzuzufügen.

Untertitel stehen in Teams Meeting Recordings für Kunden zur Verfügung, die sich dafür entschieden haben, Transkription zu erlauben, wie unter [Teams-Cloudaufzeichnungen beschrieben.](cloud-recording.md)

Beschriftungen helfen beim Erstellen integrativer Inhalte für Betrachter aller Fähigkeiten. Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Transkription in Teams weiterhin verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams. Erfahren [Sie, wie Sie Besprechungsaufzeichnungen aktivieren oder deaktivieren.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Untertitel werden für Die Aufzeichnungen von Teams-Besprechungen 60 Tage nach der Aufzeichnung der Besprechung unterstützt.

Untertitel werden nicht vollständig unterstützt, wenn die #A0 von ihrem ursprünglichen Speicherort auf OneDrive for Business oder SharePoint verschoben oder kopiert wird.

**Wie wird sich mein Speicherkontingent auswirken?**

Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services. Weitere [Informationen finden Sie unter SharePoint-Kontingent](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Mit [OneDrive for Business erhalten Sie](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) mehr Speicherplatz im Vergleich zu Stream und mehr speicherbare Speicher mit SharePoint.

**Wie kann ich eine Aufzeichnung einer Teams-Besprechung wiederspielen?**

Ihr Video wird auf dem Videoplayer von OneDrive for Business oder SharePoint angezeigt, je nachdem, wo Sie auf die Datei zugreifen.

**Wenn Sie planen, das Hinzufügen zu Stream zu veraltet zu machen, bleiben die vorhandenen Videos so, wie es ist und wie lange?**

Streamen als Plattform wird in naher Zukunft nicht mehr unterstützt. Die Videos, die derzeit in Stream live sind, bleiben dort, bis wir mit der Migration beginnen. Bei der Migration werden diese Videos ebenfalls zu OneDrive for Business oder SharePoint migriert. Weitere [Informationen finden Sie unter Klassische Migration](https://docs.microsoft.com/stream/streamnew/classic-migration) streamen.

**Wie kann ich eine Aufbewahrungsbezeichnung anwenden?**

Weitere [Informationen finden Sie unter Automatisches Anwenden einer Aufbewahrungsbeschriftung.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Wie weisen ich meinen Benutzern in Microsoft Teams Richtlinien zu, und welche Richtlinien haben Vorrang?**

Weitere Informationen [finden Sie unter Welche Richtlinie hat Vorrang?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
