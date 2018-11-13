---
title: Einrichten von für live Ereignisse in der Microsoft-Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Informationen Sie zu den Schritten für Ereignisse in der Microsoft-Teams, einschließlich der Vorbereitung Ihres Netzwerks Zuweisen von Lizenzen, Aktivieren von live-Ereignis für Benutzer planen und Einrichten von einem Anbieter eCDN live einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296380"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Einrichten von für live Ereignisse in der Microsoft-Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Beim Einrichten für live Ereignisse sind mehrere Schritte, die Sie durchführen müssen:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Schritt 1: Richten Sie Ihres Netzwerks für live Ereignisse in der Microsoft-Teams ein
Die Schnellstart live Ereignisse müssen Sie zum [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Sicherzustellen, dass der richtige Lizenz Zuordnungen für [Erstellen und Planen Sie live Ereignisse zu können?](#who-can-create-and-schedule-live-events) und [können, die live Ereignisse überwachen?](#who-can-watch-live-events).

## <a name="step-3-enable-live-event-scheduling-for-users"></a>Schritt 3: Aktivieren von live-Ereignis planen für Benutzer
Planen von Live-Ereignis ist standardmäßig aktiviert, für Teams Benutzer, aber Sie möchten Benutzer externe Encoder Ereignisse planen, sind zusätzliche Schritte, die Sie durchführen müssen.

### <a name="for-quick-start-events"></a>Schnellstart-Ereignisse
Verwenden Sie die Einstellung *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in PowerShell Teams können Sie steuern, ob der Benutzer live Ereignisse in Teams oder nicht erstellen kann. Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingBroadcastPolicy [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Wenn Sie eine benutzerdefinierte Richtlinie an, die Benutzern zugewiesen zugewiesen haben, erhalten die Benutzer die *globale* Richtlinie ein, die Aufzeichnung, die in der Standardeinstellung aktiviert hat.

Stellen Sie sicher, dass *AllowBroadcastScheduling* -Parameter auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie den Benutzer die *globale* Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a>Benutzerszenarien
**Sollen alle Benutzer in Ihrem Unternehmen live Ereignisse erstellen können.**

Wenn Benutzer die *globalen* Richtlinie zugewiesen sind, ausführen, und stellen Sie sicher, *AllowBroadcastScheduling* * auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Wenn der Benutzer eine Richtlinie als die *globale* Richtlinie zugewiesen sind, führen Sie folgenden Befehl ein, und stellen Sie sicher, dass *- AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Live-Ereignis Planung in Ihrer Organisation 100 % deaktiviert werden soll.**

Führen Sie deaktivieren broadcast planen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die *globale* Richtlinie, führen weisen Sie alle Benutzer in Ihrer Organisation zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Sie möchten eine große Anzahl von Benutzern live Ereignisse erstellen können, aber verhindern, dass eine Gruppe von Benutzern erstellen möchten.**

Weisen Sie die *globale* Richtlinie mit dem **Grant-CsTeamsMeetingBroadcastPolicy** für einige Benutzer (, die Sie aktivieren möchten), aber zuerst führen Sie folgenden Befehl, und stellen Sie sicher, dass *AllowBroadcastScheduling* auf *True*festgelegt ist:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Weisen Sie mindestens ein Benutzer die *globale* Richtlinie, ausführen:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen und Zuweisen einer Richtlinie für die Deaktivierung planen, mit dem Cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** an andere Benutzer ein (deaktiviert). 

Erstellen Sie die neue Richtlinie deaktiviert, ausführen:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Deaktivieren Sie planen, ausführen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Sie live Ereignisse für eine große Anzahl von Benutzern deaktiviert werden soll, jedoch eine Gruppe von Benutzern, deren Erstellung zu zulassen möchten.**

Führen Sie deaktivieren broadcast planen:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Die *globale* Richtlinie, führen Sie anschließend weisen Sie diese Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Erstellen und Zuweisen einer Richtlinie für die Aktivierung planen, ausführen:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Führen Sie Zeitplan aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a>Für externe Encoder-Ereignisse
Sie müssen Folgendes ein, um die Planung für diese Benutzer live Ereignis zu aktivieren.

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Schritt 1: Aktivieren von Microsoft-Stream für Benutzer in Ihrer Organisation **
Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst. Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/stream/license-overview) .

> ! [HINWEIS] Microsoft-Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten.  

Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht ausgeschlossen wird, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Schritt 2: Stellen Sie sicher, dass Benutzer über Berechtigungen zum Erstellen live-Ereignis in Microsoft Stream ** verfügen
In der Standardeinstellung können Administratoren externe Encoder live Ereignisse erstellen. Microsoft-Stream-Administrator können in Stream-Objekt [für die Erstellung des live-Ereignis weitere Benutzer aktivieren](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) .  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Schritt 3: Stellen Sie sicher, die Organisatoren die Unternehmensrichtlinie festlegen, indem Stream Admin ** zugestimmt haben live-Ereignis
Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Teams. Sicherstellen Sie bevor Sie Einführung das Feature live Ereignisse in der Organisation, dass Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt haben. 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Schritt 4: Einrichten von eCDN-Anbieter für live Ereignisse in der Microsoft-Teams 
Wiedergabe von Videos live-Ereignis verwendet adaptive Bitrate (ABR) streaming, aber es ist eine Unicast-Stream, was bedeutet, dass jeder Viewer eigene Videostream aus dem Internet abrufen ist. Für live Ereignisse oder Videos an große Teile Ihrer Organisation gesendet kann sehr viel Internetbandbreite Identitätsdaten durch Viewer handeln. Für Organisationen, die diesen Internet-Datenverkehr für live Ereignisse reduzieren möchten, vertrauenswürdige live Ereignisse, die von Microsoft Solutions integriert sind video Delivery Partner, anbietet Software Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) definiert. Diese SDN / eCDN Plattformen können Organisationen zum Optimieren der Netzwerkbandbreite ohne Beeinträchtigung Endbenutzer Erfahrungen anzeigen. Unsere Partner helfen, eine skalierbare und effiziente video Verteilung über Ihr Unternehmensnetzwerk zu aktivieren.

**Purchase & Setup Ihrer Lösung außerhalb von Microsoft-Teams,** Hier erhalten Sie Hilfe Experten video Übermittlung durch die Nutzung von Microsoft vertrauenswürdigen video Delivery Partner skalieren. Bevor Sie einen video Delivery-Anbieter mit Teams aktivieren können, müssen Sie erwerben und setup die Lösung SDN/eCDN äußeren und getrennt von Teams.

SDN/eCDN Folgendes können bereits integriert werden und Setup mit Microsoft-Streams verwendet werden.

- **Streaming Struktur** bietet eine einfache und leistungsstarke Lösung für die Live- und on-Demand Enterprise video Verteilung. Struktur ist eine softwarebasierte Lösung, die erfordert keine zusätzliche Hardware oder Bandbreite und auf sichere Weise Tausende von gleichzeitigen video Viewer ohne Auswirkung auf das Netzwerk zu aktivieren. Für Kunden, die zum Verständnis, dass das Video Auswirkung in ihrem Netzwerk vor dem Kauf einer Lösung SDN/eCDN hat bietet Streaming Struktur auch eine browserbasierte Analytics Lösung zur Microsoft-Kunden. [Erfahren Sie mehr](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** ist eine Cloud-basierten, intelligente Peers Verteilung Plattform, die nutzt die vorhandene Netzwerkinfrastruktur zum Übermitteln von Inhalten, in vielen Formen, (live Videostreams, bei Bedarf Video, Softwareupdates, Sicherheitspatches usw.), schneller zuverlässig und mit weniger Bandbreite. Unsere sichere Plattform ist vertrauenswürdig, von der weltweit größten Finanzinstituten und mit keine zusätzliche Hardware, Installation und Wartung einfach sind. [Erfahren Sie mehr](http://www.kollective.com).
 
- **Lernen OmniCache** ermöglicht die Verteilung der nächsten Generation Netzwerk und sorgt für nahtlose Bereitstellung von Videoinhalten auf globale WANs, Netzwerkbandbreite zu optimieren und unterstützen erfolgreiches Ereignis live Übertragungen und on-Demand Ereignis Hersteller helfen Streaming. Die Unterstützung für lernen OmniCache Schnellstart live Ereignisse wird in Kürze bereitgestellt.  [Erfahren Sie mehr](http://www.ramp.com). 
 
> [!NOTE] 
> Ihre Lösung gewählten eCDN unterliegt den ausgewählten **3. Anbieters Bedingungen Service und der Datenschutzrichtlinie**, Ihre Verwendung des Anbieters eCDN Lösung, welche wird steuert. Ihre Verwendung des Anbieters eCDN Lösung werden nicht unter der Microsoft Volume licensing Begriffe oder Online Services-Ausdrücken. Wenn Sie nicht den **3. Anbieters Begriffe**zustimmen, aktivieren Sie dann nicht die eCDN-Lösung in Teams. 

**Richten Sie ein eCDN für "Schnellstart" live Ereignisse** Sie können eCDN-Anbieter für live Ereignisse in Teams von PowerShell konfigurieren. 

> [!NOTE] 
> Ein einzelnes eCDN Anbieter kann für Ihre Organisation konfiguriert werden. 

***Struktur*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Erhalten Sie zuerst die Lizenz-ID und API-Vorlagen-URL aus der Struktur Kontakt führen Sie die folgenden:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren. Zunächst erhalten Sie das Token API und die URL der API-Vorlage aus dem Kollective Kontakt, und führen Sie folgenden Befehl:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Richten Sie ein eCDN für "Externe Encoder" live-Ereignisse** 

Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie ebenfalls [Konfigurieren des Anbieters eCDN mit Microsoft-Stream](https://docs.microsoft.com/stream/network-caching) . 

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [Konfigurieren Teams live Ereignisse](configure-teams-live-events.md).
