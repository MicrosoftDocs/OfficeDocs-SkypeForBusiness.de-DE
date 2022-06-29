---
title: Besprechungsrichtlinien und Ablauf von Besprechungen in Microsoft Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen verwenden, um den Ablauf von Besprechungen in Microsoft Teams zu steuern.
ms.openlocfilehash: 08ca5a75b8dd470b006d44e562eb795f814faba6
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529687"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Ablauf von Besprechungen in Microsoft Teams

[Besprechungsrichtlinien](meeting-policies-overview.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell-Cmdlets ["Get](/powershell/module/skype/get-csteamsmeetingpolicy)", ["New](/powershell/module/skype/new-csteamsmeetingpolicy)", ["Set](/powershell/module/skype/set-csteamsmeetingpolicy)", ["Remove](/powershell/module/skype/remove-csteamsmeetingpolicy)", ["Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy".

Die Besprechungsrichtlinieneinstellungen, die steuern, ob Benutzer Besprechungen starten und planen können, sowie den Ablauf von Besprechungen steuern, die von Benutzern geplant wurden. Wenn ein Besprechungsbeitrittslink und eine Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Die folgenden Besprechungsrichtlinieneinstellungen bestimmen, ob Benutzer Besprechungen in Teams starten und planen können. In diesem Artikel werden die Besprechungseinstellungen erläutert.

- [Jetzt in Kanälen](meeting-policies-in-teams-general.md#meet-now-in-channels) besprechen: Steuert, ob ein Benutzer eine spontane Besprechung in einem Kanal starten kann.
- [Planung von Kanalbesprechungen](meeting-policies-in-teams-general.md#channel-meeting-scheduling): Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planung privater Besprechungen](meeting-policies-in-teams-general.md#private-meeting-scheduling): Steuert, ob ein Benutzer eine private Besprechung in Teams planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Outlook-Add-In](meeting-policies-in-teams-general.md#outlook-add-in): Steuert, ob ein Benutzer eine private Besprechung von Outlook aus planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Besprechungen jetzt in privaten Besprechungen](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): Steuert, ob ein Benutzer eine spontane private Besprechung starten kann.

Diese Einstellungen sind standardmäßig aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, kann jeder Benutzer, dem die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen. Gleichzeitig treten die Besprechungslinks und Konferenz-IDs aller vorhandenen Besprechungen dieses Typs, die der Benutzer zuvor gestartet oder geplant hat, ab.

Wenn einem Benutzer z. B. eine Besprechungsrichtlinie zugewiesen wird, in der diese Besprechungsrichtlinieneinstellungen auf **"Ein**" festgelegt sind, und Sie dann die Einstellung " **Besprechung jetzt zulassen" in Kanälen** deaktivieren, kann dieser Benutzer keine spontanen Besprechungen mehr in Kanälen starten, und der Kanal "Besprechungen" tritt jetzt Links bei, die der Benutzer zuvor erstellt hat, ist abgelaufen. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Link zum Besprechungsbeitritt und die Konferenz-ID ablaufen?

Wenn der Besprechungsbeitrittslink und die Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung teilzunehmen, erhält er eine Meldung, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Transkriptionen und andere Inhalte im Zusammenhang mit der Besprechung werden beibehalten, und Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinieneinstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Aktivieren und Deaktivieren einer Besprechungsrichtlinieneinstellung

Wenn eine Besprechungsrichtlinieneinstellung auf " **Ein**" festgelegt ist, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Besprechungsrichtlinieneinstellung auf **"Aus**" setzen, können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungsbeitrittslinks und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, sind abgelaufen.

Denken Sie daran, dass der Benutzer weiterhin an Besprechungen teilnehmen kann, die von anderen Personen organisiert werden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Umschalten einer Besprechungsrichtlinieneinstellung von "Aus" auf "Ein"

Wenn Sie eine Besprechungsrichtlinieneinstellung von **"Aus** " in " **Ein**" ändern, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Besprechungsrichtlinieneinstellung für einen Benutzer deaktiviert und dann erneut aktiviert ist, werden alle zuvor geplanten (und abgelaufenen) Besprechungen, die vom Benutzer organisiert wurden, aktiv, und Personen können über den Besprechungsbeitrittslink oder per Telefon daran teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Ablaufszenarien für Besprechungen

Hier ist eine Zusammenfassung der Funktionsweise des Besprechungsablaufs für jede der in diesem Artikel erläuterten Besprechungsrichtlinieneinstellungen.

|Wenn Sie möchten...&nbsp;&nbsp; |Gehen Sie wie folgt vor:&nbsp;&nbsp;&nbsp;&nbsp;  |Besprechungsbeitrittsverhalten&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Ablaufen von privaten Besprechungen, die von einem Benutzer gestartet wurden&nbsp;&nbsp;|Deaktivieren **Sie "Jetzt besprechen" in privaten Besprechungen**.&nbsp;&nbsp;|Niemand kann an privaten Besprechungen teilnehmen **,** die vom Benutzer gestartet wurden.|
|Ablaufen von privaten Besprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **die Planung privater Besprechungen** _und_ das **Outlook-Add-In**. &nbsp;&nbsp;|Niemand kann an privaten Besprechungen teilnehmen, die vom Benutzer geplant wurden. Dadurch wird verhindert, dass Personen an den folgenden Besprechungen teilnehmen:<ul><li>Private Besprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von privaten Besprechungsserien.</li></ul><br>Sowohl **die Planung privater Besprechungen** als auch **das Outlook-Add-In** müssen deaktiviert sein, um private Besprechungen abläuft, die von einem Benutzer geplant wurden. Wenn eine Einstellung deaktiviert ist und die andere aktiviert ist, bleiben Besprechungsbeitrittslinks und Konferenz-IDs vorhandener Besprechungen aktiv und werden nicht abgelaufen.|
|Ablaufkanal **Besprechungen abläuft** , die von einem Benutzer gestartet wurden&nbsp;&nbsp;|Deaktivieren **Sie "Jetzt besprechen" in Kanälen**_, und_ deaktivieren Sie die **Planung von Kanalbesprechungen**.&nbsp;&nbsp;|Niemand kann an **Kanalbesprechungen teilnehmen,** die vom Benutzer gestartet wurden.|
|Ablaufen von Kanalbesprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **die Planung von Kanalbesprechungen**.&nbsp;&nbsp;|Niemand kann an vom Benutzer geplanten Kanalbesprechungen teilnehmen. Dadurch wird verhindert, dass Personen an den folgenden Besprechungen teilnehmen:<ul><li>Kanalbesprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Kanalbesprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von wiederkehrenden Kanalbesprechungen.</li></ul>|

Wenn Sie möchten, dass Personen auf Besprechungen zugreifen können, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, haben Sie folgende Möglichkeiten:

- Aktivieren Sie die Besprechungsrichtlinieneinstellung für diesen Benutzer.
- Deaktivieren Sie die Besprechungsrichtlinieneinstellung für diesen Benutzer, und lassen Sie einen anderen Benutzer, der die Richtlinieneinstellung aktiviert hat, eine neue Besprechung erstellen, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Namen einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Besprechungsrichtlinieneinstellung auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="changes-to-meeting-expiration"></a>Änderungen am Ablauf der Besprechung

Alle neu erstellten Teams-Besprechungsaufzeichnungen (TMRs) haben einen Standardablauf von 120 Tagen. Dies ist standardmäßig für alle Mandanten aktiviert. Dies bedeutet, dass standardmäßig alle TMRs, die *nach dem Aktivieren dieses Features* erstellt wurden, 120 Tage nach ihrem Erstellungsdatum gelöscht werden. Administratoren können auch festlegen, dass Besprechungen **nie automatisch ablaufen**. Das OneDrive- und SharePoint-System überwacht das Ablaufdatum, das auf allen TMRs festgelegt ist, und verschiebt tmRs automatisch an ihrem Ablaufdatum in den Papierkorb.

> [!NOTE]
> Eine Kopie des Besprechungsprotokolls wird in OneDrive SharePoint und eine zweite Kopie in Exchange im temporären Speicher gespeichert. Die OSDP-Kopie läuft ab, wenn die TMR automatisch abläuft.

Der automatische Ablauf von Besprechungen ist ein einfacher Mechanismus zur Aufbewahrung von Speicher, der von älteren TmRs erstellt wurde. Im Durchschnitt werden 96 % der TMRs nach 60 Tagen und 99 % nach 110 Tagen nicht mehr beobachtet. Wir glauben, dass fast alle Kunden von der reduzierten Speicherlast ihres Mandanten profitieren werden, indem Sie Aufzeichnungen entfernen, die wahrscheinlich nach 60 Tagen nicht mehr überwacht werden. Es ist unser Ziel, allen Kunden standardmäßig ein möglichst sauberes Erlebnis zu bieten.

Verwenden Sie den Besprechungsablauf, um den Von Teams-Besprechungsdatensätzen gesteuerten OneDrive- oder SharePoint-Speicherverbrauch in der Cloud einzuschränken. Eine typische Besprechungsaufzeichnung verbraucht etwa 400 MB pro Stunde.

> [!NOTE]
> Das maximale Standardablaufdatum für A1-Benutzer beträgt 30 Tage.

### <a name="expiration-date"></a>Ablaufdatum

- Das Ablaufdatum wird als der Tag berechnet, an dem **es erstellt wird** , plus der **Standardanzahl von Tagen, die in der Microsoft Teams-Richtlinie vom Administrator festgelegt wurden**.
- Die Wiedergabe wirkt sich nicht auf das Ablaufdatum aus.

### <a name="change-the-default-expiration-date"></a>Ändern des Standardablaufdatums

Administratoren können die Standardablaufeinstellung in PowerShell oder im Teams Admin Center bearbeiten. Alle Änderungen wirken sich ab diesem Zeitpunkt nur noch auf *neu erstellte* TMRs aus. Dies wirkt sich nicht auf Aufzeichnungen aus, die vor diesem Datum erstellt wurden. Administratoren können das Ablaufdatum für vorhandene TmRs nicht ändern. Dies geschieht, um die Entscheidung des Benutzers zu schützen, der besitzer des TMR ist. Sowohl Besprechungen als auch Anrufe können durch diese Einstellung gesteuert werden.

Der Ablaufdatumswert kann wie folgt festgelegt werden:

- Mindestwert: **1 Tag**
- Höchstwert: **99.999 Tage**
- Sie können das Ablaufdatum auch auf **-1** festlegen, damit die Aufzeichnungen nie ablaufen.

Beispiel für einen PowerShell-Befehl:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Sie können das Ablaufdatum im Teams Admin Center unter "**Besprechungsrichtlinien**" festlegen. Nachdem Sie **Besprechungen automatisch ablaufen lassen,** erhalten Sie die Möglichkeit, einen Aufzeichnungsablauf festzulegen.

![Admin Center-Screenshot der Ablaufrichtlinie für Besprechungen.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Sicherheit und Compliance

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Sollte ich mich auf dieses Feature verlassen, um strikte Sicherheits- und Compliance-Einhaltung zu gewährleisten?

Nein, Sie sollten sich aus Rechtlichem Schutz nicht darauf verlassen, da Endbenutzer das Ablaufdatum aller aufzeichnungen, die sie kontrollieren, ändern können.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Überschreibt eine Aufbewahrungs- und/oder Löschrichtlinie, die ich im Security & Compliance Center festgelegt habe, die Ablaufeinstellung für Teams-Besprechungsaufzeichnungen?

Ja, alle Richtlinien, die Sie im Compliance Center festgelegt haben, haben vorrang.

Zum Beispiel: 

- Wenn Sie über eine Richtlinie verfügen, die besagt, dass alle Dateien auf einer Website 100 Tage lang aufbewahrt werden müssen und die Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung 30 Tage beträgt, wird die Aufzeichnung für die gesamten 100 Tage aufbewahrt.
- Wenn Sie über eine Löschrichtlinie verfügen, die besagt, dass alle Teams-Besprechungsaufzeichnungen nach fünf Tagen gelöscht werden und Sie über eine Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung von 30 Tagen verfügen, wird die Aufzeichnung nach fünf Tagen gelöscht.

### <a name="will-this-feature-enforce-file-retention"></a>Wird durch dieses Feature die Dateiaufbewahrung erzwungen?

Nein, Dateien werden aufgrund dieses Features oder seiner Einstellungen nicht aufbewahrt. Wenn ein Benutzer mit Löschberechtigungen versucht, einen TmR zu löschen, der über eine Ablaufeinstellung verfügt, wird die Löschaktion dieses Benutzers ausgeführt.

### <a name="what-skus-are-required-for-this-feature"></a>Welche SKUs sind für dieses Feature erforderlich?

- Alle SKUs verfügen standardmäßig über dieses Feature.
- A1-Benutzer werden standardmäßig auf einen maximalen Ablaufzeitraum von 30 Tagen festgelegt, können das Ablaufdatum jedoch nach Bedarf ändern.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>Was geschieht, wenn ich möchte, dass der Administrator die volle Kontrolle über den Lebenszyklus von Besprechungsaufzeichnungen hat und Endbenutzern nicht die Möglichkeit geben möchte, das Ablaufdatum außer Kraft zu setzen?

Wir empfehlen die Verwendung der Aufbewahrungs- und/oder Löschrichtlinien für Sicherheit und Compliance. Dieses Angebot ist auf die Vereinfachung im Zusammenhang mit komplexen Richtlinien und SLA-abhängigen, administrativ-rechtlichen Aspekten ausgerichtet.

Das Feature für den automatischen Ablauf ist ausschließlich als einfacher Mechanismus für die Aufbewahrung gedacht, um die Speicher clutter zu reduzieren, die aus alten Teams-Besprechungsaufzeichnungen erstellt wurde.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>Werden zukünftige Microsoft Teams-Besprechungsaufzeichnungen, die nach der Veröffentlichung dieses Features aus dem klassischen Stream migriert werden, ebenfalls automatisch ablaufen?

Nein, für migrierte Microsoft Teams-Besprechungsaufzeichnungen wird kein Ablauf festgelegt. Wir empfehlen jedoch Administratoren, nur Microsoft Teams-Besprechungsaufzeichnungen zu migrieren, die sie beibehalten möchten. Weitere Informationen werden in der Migrationsdokumentation enthalten sein.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>Wie unterscheidet sich dieses Feature von der Ablaufnachricht, die angezeigt wird, wenn ein TMR-Upload auf OneDrive und SharePoint fehlschlägt?

Wenn eine Aufzeichnung nicht auf OneDrive oder SharePoint hochgeladen werden kann, zeigt die Teams-Anwendung im Chat eine Meldung an, dass Benutzer bis zu 21 Tage Zeit haben, die TmR herunterzuladen, bevor sie endgültig vom Teams-Server gelöscht wird. Diese vorhandene Ablauferfahrung aufgrund fehlgeschlagener TMR-Uploads bezieht sich nicht auf das Feature zum automatischen Ablaufen von OneDrive und SharePoint, das im Hilfedokument erläutert wird.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Gewusst wie die Verteilung von TMR-Wiedergaben kennen, damit ich weiß, wie der optimale Standard für den automatischen Ablauf für meinen Mandanten sein sollte?

1. Suchen Sie das Video in der Bibliothek.
1. Wählen Sie **...** >  **Details**
1. Wählen Sie die Anzahl der Ansichten oben im Detailbereich aus.

Es werden Dateistatistiken angezeigt, die Folgendes anzeigen:

- Die Anzahl der eindeutigen Benutzer
- Die Anzahl der Gesamtansichten
- Der Trend der Zuschauer und Ansichten tagweise für die letzten 90 Tage
- Aufbewahrung der Zuschauer (welcher Teil des Videos angezeigt oder nicht angezeigt wurde)

### <a name="when-will-the-file-be-deleted"></a>Wann wird die Datei gelöscht?

Die Aufzeichnung wird in der Regel innerhalb eines Tages nach dem Ablaufdatum gelöscht, in seltenen Fällen kann dies jedoch bis zu fünf Tage dauern. Der Dateibesitzer erhält eine E-Mail-Benachrichtigung, wenn die Aufzeichnung abläuft, und wird zum Papierkorb geleitet, um die Aufzeichnung wiederherzustellen.

> [!NOTE]
> Am Ablaufdatum wird die Aufzeichnung in den Papierkorb verschoben, und das Ablaufdatumsfeld wird gelöscht. Wenn Sie die Aufzeichnung aus dem Papierkorb wiederherstellen, wird sie von diesem Feature nicht erneut gelöscht, da das Ablaufdatum gelöscht wurde.

## <a name="related-topics"></a>Verwandte Themen

[Ändern des Ablaufdatums der Besprechung – Endbenutzersteuerelemente](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Limits und Spezifikationen für Microsoft Teams](/microsoftteams/limits-specifications-teams)
