---
title: Besprechungsrichtlinien und Besprechungsablauf in Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
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
description: Erfahren Sie, wie Sie mithilfe von Besprechungsrichtlinieneinstellungen den Ablauf von Besprechungen in Microsoft Teams.
ms.openlocfilehash: 7912c57e12de83f112bb1c80b1c44d81d9d6b857
ms.sourcegitcommit: 32ba2ed0343e19f56e62fb3c507923c95f11b1bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2021
ms.locfileid: "61124262"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Besprechungsrichtlinien und Besprechungsablauf in Microsoft Teams

[Besprechungsrichtlinien](meeting-policies-overview.md) in Microsoft Teams werden verwendet, um zu steuern, ob Benutzer in Ihrer Organisation Besprechungen starten und planen können, sowie die Features, die für Besprechungsteilnehmer für Besprechungen zur Verfügung stehen, die von Benutzern geplant werden. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sie verwalten Besprechungsrichtlinien im Microsoft Teams Admin Center oder mithilfe von [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove,](/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell-Cmdlets.

Die Einstellungen der Besprechungsrichtlinie, die steuern, ob Benutzer Besprechungen starten und planen sowie den Ablauf von Besprechungen steuern können, die von Benutzern geplant werden. Wenn ein Teilnahmelink und eine Konferenz-ID für eine Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Die folgenden Einstellungen für Besprechungsrichtlinien bestimmen, ob Benutzer Besprechungen in einer Besprechung starten Teams. Die Besprechungseinstellungen werden in diesem Artikel erläutert.

- [Jetzt besprechungen in Kanälen](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)zulassen: Steuert, ob ein Benutzer eine Besprechung aus dem Ausweg in einem Kanal starten kann.
- [Planen von Kanal-Besprechungen](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)zulassen: Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- [Planen privater Besprechungen](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)zulassen: Steuert, ob ein Benutzer eine private Besprechung in einem Teams. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Zulassen, Outlook hinzufügen:](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)Steuert, ob ein Benutzer eine private Besprechung von einem anderen Outlook. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- [Sofortbesprechung in privaten Besprechungen](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)zulassen: Steuert, ob benutzerfreundliche private Besprechungen starten können.

Diese Einstellungen sind standardmäßig aktiviert. Wenn eine dieser Einstellungen deaktiviert ist, kann jeder Benutzer, dem die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen. Gleichzeitig treten der Besprechung Links und Konferenz-IDs aller vorhandenen Besprechungen des Typs bei, die der Benutzer zuvor begonnen oder geplant hat.

Wenn einem Benutzer beispielsweise eine Besprechungsrichtlinie zugewiesen ist, in der diese Einstellungen für die Besprechungsrichtlinie auf Ein festgelegt sind, und Sie dann die Einstellung Sofortbesprechung **in** Kanälen zulassen deaktivieren, kann dieser Benutzer keine Besprechungen in Kanälen aus dem Auslaufen mehr starten, und der Kanal "Jetzt beitreten"-Links, die der Benutzer zuvor erstellt hat, ist abgelaufen. Der Benutzer kann weiterhin andere Besprechungstypen starten und planen und an Besprechungen teilnehmen, die von anderen Personen organisiert werden.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Was geschieht, wenn der Teilnahmelink und die Konferenz-ID der Besprechung ablaufen?

Wenn der Teilnahmelink und die Konferenz-ID einer Besprechung abläuft, kann niemand an der Besprechung teilnehmen. Wenn ein Benutzer versucht, über den Link oder per Telefon an der Besprechung zu teilnehmen, wird eine Meldung angezeigt, dass die Besprechung nicht mehr verfügbar ist. Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Aufzeichnungen und andere mit der Besprechung zusammenhängende Inhalte bleiben erhalten, und die Benutzer können weiterhin darauf zugreifen.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Was geschieht, wenn Sie eine Besprechungsrichtlinieneinstellung aktivieren und deaktivieren?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Umschalten einer Besprechungsrichtlinieneinstellung von ein auf "aus"

Wenn eine Besprechungsrichtlinieneinstellung auf **Ein** festgelegt ist, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen, und jeder kann teilnehmen. Wenn Sie die Einstellung für die Besprechungsrichtlinie auf Aus **festlegen,** können Benutzer, denen die Richtlinie zugewiesen ist, keine neuen Besprechungen dieses Typs starten oder planen, und die Besprechungslinks und Konferenz-IDs vorhandener Besprechungen, die der Benutzer zuvor geplant hat, laufen ab.

Denken Sie daran, dass der Benutzer weiterhin an Besprechungen teilnehmen kann, die von anderen Personen organisiert wurden.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Ändern der Einstellung für eine Besprechungsrichtlinie von "Ein" auf "Ein"

Wenn Sie eine Besprechungsrichtlinieneinstellung von **Aus** in **Ein** ändern, können Benutzer, denen die Richtlinie zugewiesen ist, Besprechungen dieses Typs starten oder planen. Wenn eine Besprechungsrichtlinieneinstellung deaktiviert und dann für einen Benutzer erneut aktiviert ist, werden alle zuvor geplanten (und abgelaufenen) Besprechungen, die vom Benutzer organisiert wurden, aktiv, und personen können über den Teilnahmelink oder per Telefon an der Besprechung teilnehmen.  

## <a name="meeting-expiration-scenarios"></a>Szenarien für den Ablauf von Besprechungen

Hier ist eine Zusammenfassung der Funktionsweise des Ablaufs von Besprechungen für jede der in diesem Artikel erläuterten Besprechungsrichtlinieneinstellungen.

|Sie möchten...&nbsp;&nbsp; |So geht's&nbsp;&nbsp;&nbsp;&nbsp;  |Besprechungs-Joinverhalten&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Ablaufen von privaten "Jetzt treffen"-Besprechungen, die von einem Benutzer gestartet wurden&nbsp;&nbsp;|Deaktivieren Sie **"Sofortbesprechung in privaten Besprechungen zulassen"**.&nbsp;&nbsp;|Niemand kann an privaten **Besprechungen teilnehmen, die** vom Benutzer gestartet wurden.|
|Ablauf von privaten Besprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **Die Planung privater Besprechungen** _zulassen,_ und deaktivieren Sie **Outlook-Add-In zulassen.** &nbsp;&nbsp;|Niemand kann an privaten, vom Benutzer geplanten Besprechungen teilnehmen. Dadurch wird verhindert, dass Personen an folgenden Besprechungen teilnehmen:<ul><li>Private Besprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Private Besprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von besprechungsserien privaten Besprechungen.</li></ul><br>Sowohl **Das Planen privater Besprechungen** zulassen als Outlook das **Add-In** muss deaktiviert sein, damit private, von einem Benutzer geplante Besprechungen ablaufen. Wenn eine Einstellung deaktiviert und die andere aktiviert ist, bleiben Besprechungslinks und Konferenz-IDs vorhandener Besprechungen aktiv und laufen nicht ab.|
|Kanal läuft ab **Besprechungen jetzt** beginnen von einem Benutzer&nbsp;&nbsp;|Deaktivieren Sie **"Sofort besprechung in Kanälen zulassen"** _und_ deaktivieren Sie **Kanal-Besprechungsplanung zulassen.**&nbsp;&nbsp;|Niemand kann an **Kanalbesprechungen teilnehmen, die** vom Benutzer gestartet wurden.|
|Ablaufen von Kanalbesprechungen, die von einem Benutzer geplant wurden&nbsp;&nbsp;|Deaktivieren Sie **Kanal-Besprechungsplanung zulassen.**&nbsp;&nbsp;|Niemand kann an Kanalbesprechungen teilnehmen, die vom Benutzer geplant wurden. Dadurch wird verhindert, dass Personen an folgenden Besprechungen teilnehmen:<ul><li>Kanalbesprechungen, die in der Vergangenheit stattgefunden haben.</li><li>Kanalbesprechungen, die für die Zukunft geplant sind und noch nicht stattgefunden haben.</li><li>Zukünftige Instanzen von Besprechungsserien in Kanälen.</li></ul>|

Wenn Sie Personen den Zugriff auf Besprechungen wünschen, die zuvor von einem bestimmten Benutzer geplant oder gestartet wurden, können Sie:

- Aktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer.
- Deaktivieren Sie die Besprechungsrichtlinieneinstellung für den Benutzer, und lassen Sie einen anderen Benutzer, für den die Richtlinieneinstellung aktiviert ist, eine neue Besprechung erstellen, um die abgelaufene Besprechung zu ersetzen.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Auftrag einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Einstellung der Besprechungsrichtlinie auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="changes-to-meeting-expiration"></a>Änderungen am Ablauf von Besprechungen

Alle neu erstellten Teams (TMRs) haben einen Standardablauf von 60 Tagen. Diese ist standardmäßig für alle Mandanten aktiviert. Dies bedeutet, dass alle  TMRs, die nach dem Aktivieren dieses Features erstellt wurden, standardmäßig 60 Tage nach dem Erstellungsdatum gelöscht werden. Administratoren können Besprechungen auch so einrichten, dass **sie nie automatisch ablaufen.** Das OneDrive und SharePoint-System überwacht das für alle TMRs festgelegte Ablaufdatum und verschiebt TMRs automatisch am Ablaufdatum in den Papierkorb.

Der automatische Ablauf von Besprechungen ist ein einfacher Verwahrungsmechanismus, um die von älteren TMRs erstellte Speicher-Clutter zu verringern. Im Durchschnitt werden 99 % aller TMRs nach 60 Tagen nicht beobachtet. Wir sind der Meinung, dass fast alle Kunden von der verringerten Speicherauslastung ihres Mandanten profitieren werden, indem Aufzeichnungen entfernt werden, die nach 60 Tagen wahrscheinlich nicht mehr beobachtet werden. Es ist unser Ziel, standardmäßig für alle Kunden eine möglichst klare Erfahrung zu bieten.

Verwenden Sie besprechungsablauf, um die OneDrive oder SharePoint für die Cloudspeichernutzung zu beschränken, die von Teams Besprechungseinträgen gesteuert wird. Eine typische Besprechungsaufzeichnung verbraucht ca. 400 MB pro Stunde für die Aufzeichnung.

> [!NOTE]
> Das standardmäßige Standardablaufdatum für A1-Benutzer beträgt 30 Tage.

### <a name="expiration-date"></a>Ablaufdatum

- Das Ablaufdatum wird  als der Tag berechnet, an dem er erstellt wird, sowie als Standardanzahl von Tagen, die vom Administrator in der Teams **festgelegt wird.**
- Die Wiedergabe wirkt sich nicht auf das Ablaufdatum aus.

### <a name="change-the-default-expiration-date"></a>Ändern des Standardablaufdatums

Administratoren können die standardmäßige Ablaufeinstellung in PowerShell oder Teams Admin Center bearbeiten. Alle Änderungen wirken sich ab diesem *Zeitpunkt nur auf neu* erstellte TMRs aus. Dies hat keine Auswirkungen auf Aufzeichnungen, die vor diesem Datum erstellt wurden. Administratoren können das Ablaufdatum in vorhandenen TMRs nicht ändern. Dies geschieht, um die Entscheidung des Benutzers zu schützen, der die TMR besitzt. Sowohl Besprechungen als auch Anrufe können über diese Einstellung gesteuert werden.

Der Ablaufdatumswert kann wie folgt festgelegt werden:

- Minimalwert: **1 Tag**
- Maximalwert: **99.999 Tage**
- Sie können das Ablaufdatum auch auf **-1** festlegen, damit die Aufzeichnungen nie ablaufen.

Beispiel für einen PowerShell-Befehl:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Sie können das Ablaufdatum im Teams Admin Center unter **Besprechungsrichtlinien festlegen.** Nachdem Sie Besprechungen **aktiviert haben, die automatisch ablaufen,** haben Sie die Möglichkeit, einen Ablauf für die Aufzeichnung zu festlegen.

![Admin Center-Screenshot der Ablaufrichtlinie für Besprechungen.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Sicherheit und Compliance

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Sollte ich dieses Feature zur strikten Einhaltung von Sicherheit und Compliance verwenden?

Nein, Sie sollten sich aus rechtlichen Grund nicht darauf verlassen, da Endbenutzer das Ablaufdatum von Aufzeichnungen ändern können, die sie kontrollieren.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Setzt eine von mir im Security & Compliance Center festgelegte Aufbewahrungs- und/oder Löschrichtlinie die Ablaufeinstellung Teams Besprechungsaufzeichnung außer Kraft?

Ja, alle richtlinien, die Sie im Compliance Center festgelegt haben, haben die volle Priorität.

Zum Beispiel: 

- Wenn sie über eine Richtlinie verfügen, die anberaumt, dass alle Dateien auf einer Website 100 Tage aufbewahrt werden müssen und die Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung 30 Tage beträgt, wird die Aufzeichnung für die vollen 100 Tage aufbewahrt.
- Wenn Sie über eine Löschrichtlinie verfügen, die ankst, dass alle Teams-Besprechungsaufzeichnungen nach fünf Tagen gelöscht werden, und Sie eine Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung von 30 Tagen festlegen, wird die Aufzeichnung nach fünf Tagen gelöscht.

### <a name="will-this-feature-enforce-file-retention"></a>Wird durch dieses Feature die Dateiaufbewahrung erzwungen?

Nein, Dateien werden aufgrund dieses Features oder seiner Einstellungen nicht beibehalten. Wenn ein Benutzer mit Löschberechtigungen versucht, eine Microsoft Teams-Besprechungsaufzeichnung mit aktiver Ablaufeinstellung zu löschen, wird die Aufzeichnung gelöscht.

### <a name="what-skus-are-required-for-this-feature"></a>Welche SKUs sind für dieses Feature erforderlich?

- Alle SKUs verfügen standardmäßig über dieses Feature.
- A1-Benutzer werden standardmäßig auf einen maximalen Ablaufzeitraum von 30 Tage festgelegt, können das Ablaufdatum jedoch bei Bedarf ändern.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>Was muss ich tun, wenn der Administrator über Vollsteuerung des Lebenszyklus von Besprechungsaufzeichnungen verfügen soll und den Endbenutzern nicht die Möglichkeit geben möchte, das Ablaufdatum außer Kraft zu setzen?

Es wird empfohlen, die Aufbewahrungs- und/oder Löschrichtlinien für Sicherheit und Compliance zu verwenden. Dieses Angebot ist auf die Vereinfachung im Zusammenhang mit komplexen Richtlinien und SLA-abhängigen, administrativ-rechtlichen Aspekten ausgerichtet.

Die Automatische Ablauffunktion ist ausschließlich als einfacher Verwahrungsmechanismus gedacht, um die aus alten Besprechungsaufzeichnungen Teams Speicher unübersichtlich zu machen.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>Werden zukünftige Microsoft Teams-Besprechungsaufzeichnungen, die nach der Veröffentlichung dieses Features aus dem klassischen Stream migriert werden, ebenfalls automatisch ablaufen?

Nein, für migrierte Microsoft Teams-Besprechungsaufzeichnungen wird kein Ablauf festgelegt. Wir empfehlen jedoch Administratoren, nur Microsoft Teams-Besprechungsaufzeichnungen zu migrieren, die sie beibehalten möchten. Weitere Informationen werden in der Migrationsdokumentation enthalten sein.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>Inwiefern ist dieses Feature anders als die Ablaufmeldung, die angezeigt wird, wenn ein TMR-Upload auf OneDrive und SharePoint schlägt?

Wenn eine Aufzeichnung nicht auf OneDrive oder SharePoint hochgeladen werden kann, zeigt die Teams-Anwendung im Chat eine Meldung an, dass Benutzer bis zu 21 Tage Zeit haben, die TMR herunterzuladen, bevor sie dauerhaft vom Teams-Server gelöscht wird. Diese vorhandene Ablauferfahrung aufgrund fehlgeschlagener TMR-Uploads steht in keinem Zusammenhang mit OneDrive und SharePoint automatische Ablauffunktion, die im Hilfedokument erläutert wird.

## <a name="related-topics"></a>Verwandte Themen

[Ändern des Ablaufdatums einer Besprechung – Endbenutzersteuerelemente](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)


