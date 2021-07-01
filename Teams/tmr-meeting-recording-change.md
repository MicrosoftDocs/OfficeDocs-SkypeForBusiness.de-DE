---
title: Verwenden von OneDrive for Business und SharePoint für Sitzungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie in Microsoft Teams von Stream zu OneDrive for Business und zum Aufzeichnungsspeicher von SharePoint-Besprechungen wechseln.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbff25ff4f241b18baa6b313977c687c73c8262
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219122"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Der Wechsel von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen erfolgt schrittweise.

|<div style="width:290px">Datum&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Ereignis&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5. Oktober 2020<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Sie aktivieren die Richtlinie für Teams-Besprechungen so, dass Besprechungsaufzeichnungen auf OneDrive for Business und SharePoint statt in Microsoft Stream (klassisch) gespeichert werden.|
|Einführung ab dem 7. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Alle neuen Teams-Besprechungsaufzeichnungen werden auf OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Richtlinien für Teams-Besprechungen in Ihrer Organisation ändern und diese explizit auf **Stream-Besprechung** festlegen. Es reicht nicht aus, die Richtlinienberichte als Stream zu sehen. Sie müssen den Richtlinienwert explizit auf **Stream** festlegen.|
|Einführung ab dem 11. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC**<br> GCC-Kunden können die Option zwar ab dem 5. Oktober deaktivieren können, Sie können Sie jedoch nicht aktivieren. Dieses Feature wird ab dem 11. Januar 2021 für alle GCC-Kunden zur Verfügung stellen, sofern Sie das Feature nicht deaktivieren.<br>  <br>Ab 11. Januar 2021 werden alle neuen Teams-Besprechungsaufzeichnungen für GCC-Kunden auf OneDrive for Business und SharePoint gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Richtlinien für Teams-Besprechungen in Ihrer Organisation ändern und diese explizit auf **Stream-Besprechung** festlegen. <br><br>Wenn Sie das Feature deaktiviert haben, es nun aber aktivieren möchten, können Sie dazu Ihre Richtlinie für Teams-Besprechungen explizit auf **OneDrive for Business** setzen. |
|Einführung ab dem 1. März 2021 <br> *(Complete)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High und DoD**<br> Kunden können nun zum ersten Mal Cloud-Besprechungsaufzeichnungen in Microsoft Teams aktivieren. Diese Aufzeichnungen werden standardmäßig auf OneDrive und SharePoint gespeichert und abgespielt. |
|Wird ab dem 7. Juli 2021 veröffentlicht<br> *(Complete)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br> Für eine Teams-Besprechung, die in OneDrive und SharePoint aufgezeichnet und während der Besprechung auch live aufgezeichnet wurde, können Sie jetzt in Microsoft Search suchen, um die Aufzeichnungsdatei der Besprechung basierend auf dem Transkript zu finden. |
|Inkrementell ab dem 16. August 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br>Es können keine neuen Besprechungsaufzeichnungen in Microsoft Stream (klassisch) gespeichert werden. Bei allen Kunden werden Besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint gespeichert, selbst wenn sie ihre Teams-Besprechungsrichtlinien in "Stream" geändert haben.<br><br> Um den Wandel in Ihrem Unternehmen besser kontrollieren zu können, empfehlen wir unseren Kunden, sich für den Wechsel zu entscheiden, wann immer Sie denken, es ist der richtige Zeitpunkt, anstatt darauf zu warten, dass der Wechsel stattfindet. |

Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase eines Übergangs vom klassischen Microsoft Stream zum [neuen Stream](/stream/streamnew/new-stream) speichert diese Methode Aufzeichnungen auf Microsoft OneDrive for Business und SharePoint in Microsoft 365 und bietet viele Vorteile.

> [!NOTE]
> Wenn eine Teams-Besprechungsaufzeichnung nicht erfolgreich auf OneDrive/SharePoint hochgeladen werden kann, wird die Aufzeichnung stattdessen vorübergehend in Azure Media Services (AMS) gespeichert. Nachdem die Aufzeichnung in AMS gespeichert wurde, werden keine Wiederholungsversuche ausgeführt, um die Aufzeichnung automatisch auf OneDrive/SharePoint oder Stream hochzuladen.

In AMS gespeicherte Besprechungsaufzeichnungen sind 21 Tage lang verfügbar, bevor sie automatisch gelöscht werden. Benutzer können das Video von AMS herunterladen, wenn sie eine Kopie behalten müssen.

Die Verwendung von OneDrive for Business und SharePoint zum Speichern von Aufzeichnungen bietet folgende Vorteile:

- Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S+C E5 Beschriftungen zur automatischen Aufbewahrung)
- Vorteile der Informationsgovernance in OneDrive for Business und SharePoint
- Einfach eingestellte Berechtigungen und Freigabe
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) nur mit expliziter Freigabe
- Ablauf von „Zugriff anfordern“
- Bereitstellen von freigegebenen OneDrive for Business- und SharePoint-Links
- Besprechungsaufzeichnungen sind schneller verfügbar
- Aufzeichnung des Aufzeichnungsergebniss der Suchbasis in Ihrer Besprechung
- **Nach lokal verschieben** Mandantenunterstützung
- Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für den Benutzer spezifischen Region gespeichert
- Unterstützung von "Bring your own key" (BYOK)

Hier finden Sie eine vollständige Liste der heute verfügbaren Features [und was im Laufe der Zeit zu erwarten ist.](/stream/streamnew/features-new-version-stream) 

Weitere Informationen finden Sie unter "Microsoft Teams für Besprechungsaufzeichnungen".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Einrichten der Option zur Besprechungsaufzeichnung für OneDrive for Business und SharePoint

Die Option zur Besprechungsaufzeichnung ist eine Einstellung auf der Richtlinienebene von Teams. Das folgende Beispiel zeigt, wie Sie die globale Richtlinie festlegen können. Stellen Sie sicher, dass Sie die Option zur Besprechungsaufzeichnung für die Richtlinie oder Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.

> [!Note]
> Teams der Aktualisierung von Besprechungsrichtlinien dauert es eine Weile, bis sie weitervererbt wurden. Schauen Sie nach ein paar Stunden nach dem Festlegen wieder nach, melden Sie sich ab und wieder bei der Teams Desktop-App an, oder starten Sie Ihren Computer einfach neu.

1. Teams PowerShell installieren.

   > [!NOTE]
   > Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren. Siehe [Verwalten von Skype for Business Online mit PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Öffnen Sie PowerShell als Administrator.

3. Installieren Sie das [PowerShell-Modul von Teams](./teams-powershell-install.md).

4. Importieren Sie das MicrosoftTeams-Modul, und melden Sie sich als Teamadministrator an.


   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Verwenden Sie [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) zum Festlegen einer Teams-Besprechungsrichtlinie für den Übergang vom Streamspeicher zu OneDrive for Business und SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Wenn einige Ihrer Benutzer eine Richtlinie pro Organisator oder Benutzer zugewiesen haben, müssen Sie diese Einstellung für diese Richtlinie festlegen, wenn Sie möchten, dass diese Benutzer die Besprechungsaufzeichnungen auch in OneDrive for Business und SharePoint speichern. Weitere Informationen finden Sie unter [Besprechungsrichtlinien in Teams verwalten](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Deaktivieren von OneDrive for Business und SharePoint, um Stream weiterhin nutzen zu können

Selbst wenn eine Richtlinie besagt, dass sie auf **Stream** festgelegt ist, ist sie möglicherweise nicht festgelegt. Wenn die Richtlinie nicht festgelegt ist, ist die Standardeinstellung **Stream**. Wenn Sie jedoch SharePoint oder OneDrive for Business bei dieser neuen Änderung deaktivieren möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass **Stream** die Standardeinstellung ist.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Berechtigungen oder rollenbasierter Zugriff

> [!Note]
> Wir empfehlen, dass der Empfänger zum Freigeben von Teams-Besprechungsaufzeichnungen ein angemeldeter Benutzer sein muss. Wählen Sie die Option **Personen in (Ihrer Organisation)** aus, wenn Sie die Datei freigeben, wie unter [SharePoint-Dateien oder -Ordner freigeben](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) dokumentiert. Die externe Freigabe ist nicht für die Verteilung großer Dateien oder einer großen Anzahl von Dateien ausgelegt. Um Betrugs- und Missbrauchsszenarien zu verhindern, kann es Probleme beim Freigeben einer großen Datenmenge für externe Benutzer geben.

|Besprechungstyp                               | Wer hat auf "Aufzeichnen" geklickt?| Wo landet die Aufzeichnung?                               |Wer hat Zugriff? Lese/Schreibzugriff, Lesezugriff oder Freigabe                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |Das OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte. <br /><br />Der Angerufene (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br /> Der Angerufene (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit internen Parteien             |Angerufener                 |Das OneDrive for Business-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte. <br /><br />Der Anrufer (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br />Der Anrufer (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |Das OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte.<br /> <br />Der Angerufene hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit einem externen Anruf             |Angerufener                 |Das OneDrive for Business-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte.<br /><br />Der Anrufer hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|Gruppenanruf                                 |Jedes Mitglied des Anrufs |Gruppenmitglied, das auf das OneDrive for Business-Konto der Aufzeichnung geklickt hat  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte. <br /><br /> Andere Mitglieder aus demselben Mandanten haben Leserechte. <br /><br /> Andere Gruppenmitglieder aus verschiedenen Mandanten haben keine Rechte an der Gruppe.|
|Spontane/Geplante Besprechung                    |Organisator              |Das OneDrive for Business-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung. <br /><br /> Alle anderen Mitglieder verfügen über Lesezugriff.|
|Spontane/Geplante Besprechung                    |Anderes Besprechungsmitglied   |Besprechungsmitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. <br /><br />Der Organisator verfügt über Bearbeitungsrechte und kann freigeben.<br /><br /> Alle anderen Besprechungsmitglieder verfügen über Lesezugriff.|
|Spontane/Geplante Besprechung mit externen Benutzern|Organisator              |Das OneDrive for Business-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung.<br /> <br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff. <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Spontane/Geplante Besprechung mit externen Benutzern|Anderes Besprechungsmitglied   |Mitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. Der Organisator verfügt über Bearbeitungsrechte und kann freigeben. <br /><br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff. <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Kanalbesprechung                            |Kanalmitglied         |SharePoint-Speicherort von Teams für diesen Kanal                   |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über Bearbeitungsrechte auf die Aufzeichnung. <br /> <br />Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint-Berechtigungen des Kanals.|

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo wird die Besprechungsaufzeichnung gespeichert?**

- Bei Besprechungen außerhalb des Kanals wird die Aufzeichnung in einem Ordner namens **Aufzeichnungen** gespeichert, der sich auf der obersten Ebene von OneDrive for Business befindet, das zu der Person gehört, die die Besprechungsaufzeichnung gestartet hat. Beispiel:

  **Aufzeichnungen**/<i>im OneDrive for Business des Aufzeichners</i>

- Bei Kanalbesprechungen wird die Aufzeichnung in der Teamwebsite-Dokumentationsbibliothek in einem Ordner namens **Aufzeichnungen** gespeichert. Beispiel:

  <i>Name des Teams – Kanalname</i>/**Dokumente**/**Aufzeichnungen**

**Wenn Stream-Dateien (z. B. Aufzeichnungen) in SharePoint/OneDrive gespeichert werden, wie wird dann entschieden, wohin sie sollen? Hat der Administrator die Möglichkeit, den Ort zu ändern, an den sie gehen sollen?**

Standardmäßig gehen alle Aufzeichnungsdateien an das OneDrive-Konto des Benutzers, der die Option **Aufzeichnen** ausgewählt hat. Bei Kanalbesprechungen wird die Aufzeichnung immer zur SharePoint-Website des Kanals übertragen. Der Administrator kann den Ort, an dem die Aufzeichnung gespeichert ist, nicht ändern.

**Was mache ich mit Aufzeichnungen von ehemaligen Mitarbeitern?**

Da Videos wie jede andere Datei in OneDrive for Business und SharePoint behandelt werden, folgen Besitz und Aufbewahrung nach dem Verlassen eines Mitarbeiters dem normalen [OneDrive for Business- und SharePoint-Prozess](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**Wer besitzt die Berechtigungen zur Ansicht der Besprechungsaufzeichnung?**

- Bei Besprechungen außerhalb des Kanals erhalten alle eingeladenen Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch einen persönlich freigegebenen Link. Externe Benutzer müssen der freigegebenen Liste vom Besprechungsorganisator oder der Person, die die Besprechungsaufzeichnung gestartet hat, explizit hinzugefügt werden.

- Bei Kanalbesprechungen werden Berechtigungen von der Liste "Besitzer" und "Mitglieder" im Kanal geerbt.

> [!NOTE]
> Sie erhalten nach dem Speichern der Aufzeichnung keine E-Mail, die Aufzeichnung wird jedoch im Besprechungschat angezeigt, sobald sie abgeschlossen ist. Dies geschieht wesentlich schneller als zuvor in Stream.

**Wie kann ich Untertitel verwalten?**

Untertitel für Teams-Besprechungsaufzeichnungen sind während der Wiedergabe nur verfügbar, wenn der Benutzer die Transkription zum Zeitpunkt der Aufzeichnung aktiviert hatte. Administratoren müssen die [Aufzeichnungstranskription über Richtlinien aktivieren](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) um sicherzustellen, dass ihre Benutzer die Möglichkeit haben, Besprechungen mit Transkription aufzeichnen zu können.

Untertitel helfen dabei, Inhalte für Betrachter aller Fähigkeiten inklusiv zu gestalten. Als Besitzer können Sie Untertitel in der Besprechungsaufzeichnung ausblenden, obwohl die Besprechungstranskription in Teams weiterhin verfügbar ist, sofern Sie sie dort nicht löschen. 

Untertitel werden bei Teams-Besprechungsaufzeichnungen 60 Tage ab der Aufzeichnung der Besprechung unterstützt.

Untertitel für Hörgeschädigte werden nicht vollständig unterstützt, wenn die Teams-Besprechungsaufzeichnung von ihrem ursprünglichen Speicherort auf OneDrive for Business oder SharePoint verschoben oder kopiert wird.

> [!NOTE]
> Es gibt nur englische Untertitel (die Transkription von Besprechungen ist in englischen GCC).

**Wie wirkt sich dies auf mein Speicherkontingent aus?**

Die Aufzeichnungsdateien für Teams-Besprechungen befinden sich in OneDrive for Business und SharePoint und sind in Ihrem Kontingent für diese Dienste enthalten. Siehe [SharePoint-Kontingent](/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent](/onedrive/set-default-storage-space).

Sie erhalten mit [OneDrive for Business](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) mehr Speicherplatz im Vergleich zu Stream und mehr fungiblen Speicher mit SharePoint.

**Wie kann ich eine Team-Besprechungsaufzeichnung abspielen?**

Das Video wird im Videoplayer von OneDrive for Business oder SharePoint abgespielt, je nachdem, wo Sie auf die Datei zugreifen.

**Wenn man plant, das Hinzufügen zu Stream zu einzustellen, bleiben dann die vorhandenen Videos erhalten und für wie lange?**

Stream als Plattform wird in naher Zukunft nicht eingestellt. Die Videos, die sich aktuell in Stream befinden, bleiben dort, bis wir mit der Migration beginnen. Bei der Migration werden diese Videos auch nach OneDrive for Business oder SharePoint migriert. Weitere Informationen finden Sie unter [klassische Migration von Stream](/stream/streamnew/classic-migration).

**Wie kann ich eine Aufbewahrungsbezeichnung auf Microsoft Teams anwenden?**

Siehe [Aufbewahrungsbezeichnungen automatisch anwenden](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

**Wie weise ich meinen Benutzern in Microsoft Teams Richtlinien zu, und welche Richtlinien haben Vorrang?**

Siehe [Welche Richtlinie hat Vorrang?](./assign-policies.md#which-policy-takes-precedence).

**Wo wird die Aufzeichnung gespeichert, wenn der Benutzer nicht über OneDrive for Business Oder SharePoint oder das Speicherkontingent voll ist?**

Die Aufzeichnung wird an unserem temporären Speicherort landen, wo sie 21 Tage lang gespeichert wird. Während dieser Zeit muss der Organisator die Aufzeichnung herunterladen. Wenn die Aufzeichnung nicht innerhalb von 21 Tagen heruntergeladen wurde, wird sie gelöscht.
