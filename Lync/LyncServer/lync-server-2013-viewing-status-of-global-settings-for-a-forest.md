---
title: 'Lync Server 2013: Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-20_

Administratoren sollten die globalen Einstellungen für eine lync Server 2013-Bereitstellung monatlich überprüfen. Das Ziel besteht darin, die implementierten Einstellungen für eine Reihe bekannter Konfigurationen zu überprüfen – eine Baseline-Konfiguration, um sicherzustellen, dass die Einstellungen gültig sind, und um festzustellen, ob die Baseline-Dokumentation aktualisiert werden soll. Änderungen an der globalen Einstellung sollten über einen Änderungskontrollprozess implementiert werden, der die Dokumentation der neuen Einstellungen umfasst.

Die globalen Einstellungen, die überprüft werden sollten, werden in den folgenden Abschnitten beschrieben:

<div>

## <a name="check-general-settings"></a>Allgemeine Einstellungen überprüfen

Überprüfen Sie die allgemeinen Einstellungen, einschließlich der unterstützten SIP-Domänen (Session Initiation Protocol) für lync Server 2013.

SIP-Domäneninformationen können mithilfe von Windows PowerShell und dem Cmdlet **Get-CsSipDomain** zurückgegeben werden. Wenn Sie diese Informationen zurückgeben möchten `Get-CsSipDomain` , führen Sie den Windows PowerShell-Befehl aus.

"Get-CsSipDomain" gibt ähnliche Informationen für alle autorisierten SIP-Domänen zurück:

Identitäts Name IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Wenn die IsDefault-Eigenschaft auf true festgelegt ist, ist die entsprechende Domäne Ihre standardmäßige SIP-Domäne. Sie können das Cmdlet "Satz-CsSipDomain" verwenden, um die SIP-Standarddomäne für Ihre Organisation zu ändern. Sie können die standardmäßige SIP-Domäne jedoch nicht einfach löschen, da Sie ohne eine Standarddomäne verbleibt. Wenn Sie die fabrikam.com-Domäne löschen möchten (wie im vorherigen Beispiel gezeigt), müssen Sie na.fabrikam.com zunächst so konfigurieren, dass es sich um Ihre Standarddomäne handelt.

</div>

<div>

## <a name="check-meeting-settings"></a>Überprüfen von Besprechungseinstellungen

Zu den Besprechungseinstellungen gehören Richtlinien Definitionen für Besprechungen und die Unterstützung für die Teilnahme anonymer Benutzer an Besprechungen.

Die Einstellungen für die besprechungskonfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-CsMeetingConfiguration** abgerufen werden. Dieser Befehl gibt beispielsweise Informationen zu den Konfigurationseinstellungen für globale Besprechungen zurück:

Get-CsMeetingConfiguration – Identity "Global" die Konfigurationseinstellungen für Besprechungen können auch im Website Bereich konfiguriert werden. Aus diesem Grund sollten Sie den folgenden Befehl verwenden, der Informationen zu allen Besprechungs Konfigurationseinstellungen zurückgibt:

`Get-CsMeetingConfiguration`

Das Cmdlet " **Get-CsMeetingConfiguration** " gibt Informationen ähnlich der folgenden zurück:

Identität: Global

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: Unternehmen

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

Das letzte Element in der Liste, **AdmitAnonymousUsersByDefault**, aktiviert oder deaktiviert die Möglichkeit von anonymen Benutzern, an Besprechungen teilzunehmen.

Wenn Sie die Einstellungen für die besprechungskonfiguration überprüfen, finden Sie es möglicherweise hilfreich, die aktuellen Einstellungen mit den Standard äquivalenten zu vergleichen. Sie können die Standardeinstellungen für die besprechungskonfiguration anzeigen, indem Sie den folgenden Befehl ausführen:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

Der vorherige Befehl erstellt eine speicherresidente Instanz der globalen Besprechungs Konfigurationseinstellungen, eine Instanz, die den Standardwert für jede Eigenschaft verwendet. Wenn Sie den Befehl ausführen, werden keine tatsächlichen Besprechungs Konfigurationseinstellungen erstellt. Alle standardmäßigen Eigenschaftswerte werden jedoch auf dem Bildschirm angezeigt.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Überprüfen von Edgeserver und deren Einstellungen

Edge-Server Informationen können mithilfe von Windows PowerShell abgerufen werden. Dieser Befehl gibt Informationen zu allen Edge-Servern zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:

`Get-CsService -EdgeServer`

Die zurückgegebenen Informationen enthalten alle FQDN-und Porteinstellungen für jeden Edgeserver:

Identity: EdgeServer: DC.fabrikam.com

Kanzler: Kanzler: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: DC.fabrikam.com

DataEdgeExternalFqdn: DC.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: DC.fabrikam.com

DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE. fabrikam

com, MediationServer: LYNC-SE.

fabrikam.com}

Dienst-Nr: fabrikam.com-EdgeServer-2

Website-Nr: Website:fabrikam. com

PoolFqdn: DC.fabrikam.com

Version: 5

Rolle: EdgeServer

<div>

## <a name="check-federation-settings"></a>Überprüfen der Verbund Einstellungen

Überprüfen Sie die Verbund Einstellungen, beispielsweise ob Sie konfiguriert ist und, wenn die Antwort "Ja" lautet, den FQDN und den Port. Der Verbund wird mithilfe der globalen Sammlung von Access Edge-Konfigurationseinstellungen aktiviert und deaktiviert. Unter anderem bedeutet dies, dass der Verbund auf der Grundlage einer vollständigen oder gar nichts-Basis konfiguriert ist: entweder ist der Verbund für die gesamte Organisation aktiviert, oder der Verbund ist für die gesamte Organisation deaktiviert.

Ihre Access Edge-Konfigurationseinstellungen können mithilfe von Windows PowerShell zurückgegeben werden. Führen Sie dazu den folgenden Windows PowerShell-Befehl aus:

`Get-CsAccessEdgeConfiguration`

Dieser Befehl gibt wiederum Daten zurück, die wie folgt aussehen:

Identität: Global

AllowAnonymousUsers: falsch

AllowFederatedUsers: falsch

AllowOutsideUsers: falsch

Beclearing: falsch

EnablePartnerDiscovery: falsch

EnableArchivingDisclaimer: falsch

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod : UseDnsSrvRouting

Wenn die **AllowFederatedUsers** -Eigenschaft auf "true" festgelegt ist, bedeutet dies, dass der Verbund für Ihre Organisation aktiviert ist. (Wenn Sie **AllowFederatedUsers** auf "true" festlegen, bedeutet dies auch, dass Ihre lokalen Benutzer in einem geteilten Domänen Szenario nahtlos mit ihren in-the-Cloud-Benutzern kommunizieren können.)

Informationen zum Abrufen der FQDN-und Porteinstellungen für Ihren Edgeserver finden Sie in der vorherigen Aufgabe (Edgeserver und deren Einstellungen).

Das Aktivieren des Föderations Bereichs im globalen Bereich bedeutet nur, dass Benutzer potenziell mit Verbundbenutzern kommunizieren können. Wenn Sie feststellen möchten, ob einzelne Benutzer tatsächlich mit Verbundbenutzern kommunizieren können, müssen Sie die Richtlinie für den externen Benutzer Zugriff untersuchen, die diesem Benutzer zugewiesen ist.

Zugriffsinformationen für externe Benutzer können mithilfe von Windows PowerShell zurückgegeben werden. Dieser Befehl gibt beispielsweise Informationen für die globale Richtlinie für den externen Benutzer Zugriff zurück:

`Get-CsExternalAccessPolicy -Identity "Global"`

Und dieser Befehl gibt Informationen für alle Richtlinien für den externen Benutzer Zugriff zurück:

`Get-CsExternalAccessPolicy`

Die zurückgegebenen Informationen werden wie folgt aussehen:

Identität: falsch

Beschreibung

EnableFederationAccess: falsch

EnablePublicCloudAccess: falsch

EnablePublicCloudAccessAudioVideoAccess: falsch

EnableOutsideAccess: falsch

Wenn **EnableFederationAccess** auf "true" festgelegt ist, können Benutzer, die von der angegebenen Richtlinie verwaltet werden, mit Verbundbenutzern kommunizieren.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Überprüfen der Archivierungseinstellungen

Überprüfen Sie die Archivierungseinstellungen für die interne und die Verbundkommunikation. Bevor Sie die Einstellungen für die interne und externe Archivierung überprüfen, sollten Sie sicherstellen, dass die Archivierung aktiviert ist.

Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsArchivingConfiguration überprüft werden:

`Get-CsArchivingConfiguration -Identity "Global"`

Beachten Sie, dass Archivierungseinstellungen auch im Website Bereich konfiguriert werden können. Wenn Sie Informationen zu allen Archivierungseinstellungen zurückgeben möchten, verwenden Sie den folgenden Befehl:

`Get-CsArchivingConfiguration`

Das Cmdlet "Get-CsArchivingConfiguration" gibt Daten ähnlich wie folgt zurück:

Identität: Global

EnableArchiving: falsch

EnablePurging: falsch

PurgeExportedArchivesOnly: falsch

BlockOnArchiveFailure: falsch

"Keeparchivingdatafordays": 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

CachePurgingInterval: 24

Wenn die EnableArchiving-Eigenschaft auf false festgelegt ist, bedeutet dies, dass keine Kommunikationssitzungen archiviert werden. Wenn Sie nur Instant Messaging-Sitzungen archivieren möchten, verwenden Sie einen Befehl wie den folgenden, um die Archivierung von Chatsitzungen zu aktivieren:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Verwenden Sie den folgenden Befehl, um Konferenzsitzungen und Chatsitzungen zu archivieren:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Wenn Sie Ihre aktuellen Archivierungseinstellungen mit den Standardeinstellungen vergleichen möchten, führen Sie den folgenden Windows PowerShell-Befehl aus:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Dieser Befehl erstellt eine speicherresidente Instanz der globalen Archivierungs Konfigurationseinstellungen. Hierbei handelt es sich nicht um eine echte Sammlung von Einstellungen, die von lync Server verwendet werden. Es werden jedoch die Standardwerte für alle Archivierungs Konfigurationseigenschaften angezeigt.

Sie können diesen Befehl auch verwenden, um den FQDN ihrer Archivierungsserver zurückzugeben:

`Get-CsService -ArchivingServer`

Nachdem Sie überprüft haben, dass die Archivierung aktiviert ist, können Sie Ihre Archivierungsrichtlinien anzeigen, um festzustellen, ob interne und externe Kommunikationssitzungen archiviert werden.

Informationen zur Archivierungsrichtlinie können mit dem Cmdlet Get-CsArchivingPolicy abgerufen werden. Dieser Befehl gibt beispielsweise Informationen zur globalen Archivierungsrichtlinie zurück:

`Get-CsArchivingPolicy -Identity "Global"`

Da Archivierungsrichtlinien auch auf der Website und im Benutzerbereich konfiguriert werden können, möchten Sie möglicherweise auch diesen Befehl verwenden, der Informationen zu allen Archivierungsrichtlinien zurückgibt:

`Get-CsArchivingPolicy`

Die Informationen, die Sie von Get-CsArchivingPolicy erhalten, werden wie folgt aussehen:

Identität: Global

Beschreibung

ArchiveInternal: falsch

ArchiveExternal: falsch

Beachten Sie, dass die interne und externe Archivierung standardmäßig in einer Archivierungsrichtlinie deaktiviert ist.

</div>

<div>

## <a name="check-cdr-settings"></a>Überprüfen der CDR-Einstellungen

Überprüfen Sie die Einstellungen für den Anruf Detailsatz (CDR) für Peer-to-Peer-, Konferenz-und Sprachanruf Detail Aufzeichnung. Detaillierte Informationen zu Ihren CDR-Einstellungen können mit dem Cmdlet **Get-CsCdrConfiguration** zurückgegeben werden. Dieser Befehl gibt beispielsweise Informationen zur globalen Sammlung von CDR-Konfigurationseinstellungen zurück:

`Get-CsCdrConfiguration -Identity "Global"`

Da CdR auch im Website Bereich konfiguriert werden kann, möchten Sie möglicherweise auch diesen Befehl ausführen, der Informationen zu allen CdR-Konfigurationseinstellungen zurückgibt:

`Get-CsCdrConfiguration`

Das Cmdlet "Get-CsCdrConfiguration" gibt ähnliche Informationen für jede Sammlung von CDR-Konfigurationseinstellungen zurück:

Identität: Global

EnableCDR: true

EnablePurging: true

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Ähnliche Informationen können für die QoE-Überwachung mit dem Cmdlet Get-CsQoEConfiguration zurückgegeben werden. Dieser Befehl gibt beispielsweise Informationen zur globalen Sammlung der QoE-Konfigurationseinstellungen zurück:

`Get-QoEConfiguration -Identity "Global"`

Diese Informationen werden wie folgt aussehen:

Identität: Global

ExternalConsumerIssuedCertId :

EnablePurging: true

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: falsch

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Wenn Sie Ihre aktuellen CdR-Einstellungen mit den standardmäßigen CdR-Einstellungen vergleichen möchten, können Sie die Standardwerte überprüfen, indem Sie folgenden Befehl ausführen:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Ebenso können die Standardwerte für die QoE-Überwachung mithilfe dieses Befehls abgerufen werden:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Sie können auch den FQDN ihrer Überwachungsserver zurückgeben, indem Sie den folgenden Befehl ausführen:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Spracheinstellungen überprüfen

Die in der Regel für Administratoren wichtigen Spracheinstellungen sind in VoIP-Richtlinien und VoIP-Routen enthalten: VoIP-Richtlinien enthalten die Einstellungen, die die für einzelne Benutzer verfügbar gemachten Funktionen (wie die Möglichkeit zum Weiterleiten oder übertragen von Anrufen) bestimmen, während VoIP-Routen legen fest, wie (und wenn) Anrufe über das PSTN weitergeleitet werden.

VoIP-Richtlinieninformationen können mithilfe von Windows PowerShell abgerufen werden. Dieser Befehl gibt beispielsweise Informationen zur globalen VoIP-Richtlinie zurück:

`Get-CsVoicePolicy -Identity "Global"`

Und dieser Befehl gibt Informationen zu allen VoIP-Richtlinien zurück, die für die Verwendung in der Organisation konfiguriert sind:

`Get-CsVoicePolicy`

Die vom Cmdlet "Get-CsVoicePolicy" zurückgegebenen Informationen ähneln wie folgt:

Identität: Global

PstnUsages :{}

Beschreibung

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Name: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: falsch

EnableMaliciousCallTracing: falsch

EnableBWPolicyOverride: falsch

PreventPSTNTollBypass: falsch

Sie können auch Abfragen erstellen, die eine Teilmenge ihrer VoIP-Richtlinien zurückgegeben haben. Dieser Befehl gibt beispielsweise alle VoIP-Richtlinien zurück, die die Anrufweiterleitung zulassen:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Und dieser Befehl gibt alle VoIP-Richtlinien zurück, die keine Anrufweiterleitung zulassen:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Verwenden Sie in Windows PowerShell das Cmdlet "Get-CsVoiceRouting", um Informationen zu Ihren VoIP-Routen zurückzugeben:

`Get-CsVoiceRoute`

Dieser Befehl gibt Informationen wie diesen für alle VoIP-Routen zurück:

Identität: LocalRoute

Priorität: 0

Beschreibung

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

Name: LocalRoute

SuppressCallerId :

AlternateCallerId :

Mit lync Server können Sie VoIP-Routen erstellen, die keine PSTN-Nutzung aufweisen, und kein PSTN-Gateway angeben. Sie können jedoch keine Anrufe über eine VoIP-Route weiterleiten, für die diese beiden Eigenschaftswerte nicht konfiguriert sind. Aus diesem Grund ist es möglicherweise hilfreich, diesen Befehl in regelmäßigen Abständen auszuführen, wodurch die Identität einer VoIP-Route zurückgegeben wird, die keine PSTN-Nutzung aufweist:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Ebenso gibt dieser Befehl die Identität einer VoIP-Route zurück, die nicht für ein PSTN-Gateway konfiguriert wurde:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Überprüfen der Einstellungen der Konferenzzentrale

Überprüfen Sie die Einstellungen der Konferenzzentrale für PSTN-Einwahlkonferenzen. Einstellungen der Konferenzzentrale können nur mit dem Cmdlet **Get-CsDialInConferencingConfiguration** abgerufen werden. Diese Einstellungen stehen in der lync Server-Systemsteuerung nicht zur Verfügung. Verwenden Sie zum Anzeigen der Einstellungen der Konferenzzentrale einen Windows PowerShell-Befehl ähnlich der folgenden, der die globale Sammlung der Konferenz Aufsichts Einstellungen zurückgibt:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Beachten Sie, dass die Einstellungen der Konferenzzentrale auch im Website Bereich konfiguriert werden können. Wenn Sie Informationen zu allen Einstellungen der Konferenzzentrale zurückgeben möchten, verwenden Sie stattdessen folgenden Befehl:

`Get-CsDialInConferencingConfiguration`

Das Cmdlet "Get-CsDialInConferencingConfiguration" gibt Daten ähnlich wie folgt zurück:

Identität: Global

EntryExitAnnouncementsType : UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: falsch

Wenn EntryExitAnnouncementsEnabledByDefault auf "false" festgelegt ist, bedeutet dies, dass die Konferenz Ankündigungen deaktiviert sind. Führen Sie zum Aktivieren von Eingabe-und Beendigungs Ankündigungen einen Windows PowerShell-Befehl wie den folgenden aus:

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-csaccessedgeconfiguration nicht angeben](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

