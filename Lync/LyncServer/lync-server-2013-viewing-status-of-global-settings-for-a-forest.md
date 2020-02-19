---
title: 'Lync Server 2013: Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ce07a106e583f3ea0d4b523e1cf882677c19b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-20_

Administratoren sollten die globalen Einstellungen für eine lync Server 2013-Bereitstellung monatlich überprüfen. Das Ziel besteht darin, die implementierten Einstellungen anhand einer Reihe bekannter Konfigurationen zu überprüfen – einer Basiskonfiguration, um sicherzustellen, dass die Einstellungen gültig sind, und um zu ermitteln, ob die Basisdokumentation aktualisiert werden soll. Änderungen an der globalen Einstellung sollten über einen Änderungssteuerungsprozess implementiert werden, der die Dokumentierung der neuen Einstellungen umfassen sollte.

Globale Einstellungen, die überprüft werden sollten, werden in den folgenden Abschnitten beschrieben:

<div>

## <a name="check-general-settings"></a>Allgemeine Einstellungen überprüfen

Überprüfen Sie die allgemeinen Einstellungen, einschließlich der unterstützten SIP-Domänen (Session Initiation Protocol) für lync Server 2013.

SIP-Domäneninformationen können mit Windows PowerShell und dem Cmdlet **Get-CsSipDomain** zurückgegeben werden. Führen Sie den `Get-CsSipDomain` Befehl Windows PowerShell aus, um diese Informationen zurückzugeben.

Mit Get-CsSipDomain werden Informationen wie diese für alle autorisierten SIP-Domänen zurückgegeben:

Identitäts Name-IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Wenn die IsDefault-Eigenschaft auf true festgelegt ist, ist die entsprechende Domäne Ihre Standard-SIP-Domäne. Sie können das Cmdlet "CsSipDomain" verwenden, um die Standard-SIP-Domäne für Ihre Organisation zu ändern. Allerdings können Sie die Standard-SIP-Domäne nicht einfach löschen, da Sie ohne Standarddomäne bleiben würde. Wenn Sie die fabrikam.com-Domäne löschen wollten (wie im vorherigen Beispiel gezeigt), müssen Sie zunächst na.fabrikam.com so konfigurieren, dass Sie die Standarddomäne ist.

</div>

<div>

## <a name="check-meeting-settings"></a>Überprüfen der Besprechungseinstellungen

Die Besprechungseinstellungen umfassen Richtlinien Definitionen für Besprechungen und Unterstützung für die Teilnahme anonymer Benutzer an Besprechungen.

Die Besprechungs Konfigurationseinstellungen können mit Windows PowerShell und dem Cmdlet **Get-CsMeetingConfiguration** abgerufen werden. Mit diesem Befehl werden beispielsweise Informationen zu den globalen Besprechungs Konfigurationseinstellungen zurückgegeben:

Get-CsMeetingConfiguration – Identity "Global" Besprechungs Konfigurationseinstellungen können auch auf Standortebene konfiguriert werden. Aus diesem Grund möchten Sie möglicherweise den folgenden Befehl verwenden, der Informationen zu allen Besprechungs Konfigurationseinstellungen zurückgibt:

`Get-CsMeetingConfiguration`

Mit dem Cmdlet **Get-CsMeetingConfiguration** werden Informationen wie die folgenden zurückgegeben:

Identity: Global

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: Unternehmen

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

Das letzte Element in der Liste **AdmitAnonymousUsersByDefault**aktiviert oder deaktiviert die Möglichkeit anonymer Benutzer, an Besprechungen teilzunehmen.

Bei der Überprüfung der Besprechungs Konfigurationseinstellungen ist es möglicherweise hilfreich, die aktuellen Einstellungen mit den Standard Entsprechungen zu vergleichen. Sie können die Standardeinstellungen für die besprechungskonfiguration anzeigen, indem Sie den folgenden Befehl ausführen:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

Mit dem vorherigen Befehl wird eine nur im Arbeitsspeicher befindliche Instanz der globalen Besprechungs Konfigurationseinstellungen erstellt, eine Instanz, die den Standardwert für jede Eigenschaft verwendet. Beim Ausführen des Befehls werden keine tatsächlichen Besprechungs Konfigurationseinstellungen erstellt. Allerdings werden alle standardmäßigen Eigenschaftswerte auf dem Bildschirm angezeigt.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Überprüfen der Edgeserver und deren Einstellungen

Edgeserver Informationen können mithilfe von Windows PowerShell abgerufen werden. Dieser Befehl gibt Informationen zu allen für die Verwendung in Ihrer Organisation konfigurierten Edge-Servern zurück.

`Get-CsService -EdgeServer`

Die zurückgegebenen Informationen enthalten alle FQDN-und Porteinstellungen für jede Edgeserver:

Identity: EdgeServer: DC.fabrikam.com

Registrar: Registrar: LYNC-SE.fabrikam.com

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

Website-Nr: Website-:fabrikam. com

Poolfqdn ": DC.fabrikam.com

Version: 5

Rolle: EdgeServer

<div>

## <a name="check-federation-settings"></a>Überprüfen der Verbund Einstellungen

Überprüfen Sie die Verbund Einstellungen, beispielsweise ob Sie konfiguriert ist, und, wenn die Antwort "Ja" lautet, den FQDN und den Port. Der Verbund wird mithilfe der globalen Sammlung von Access-Edge-Konfigurationseinstellungen aktiviert und deaktiviert. Unter anderem bedeutet dies, dass der Verbund auf einer all-oder-Nothing-Basis konfiguriert ist: jeder Partnerverbund ist für die gesamte Organisation aktiviert, oder der Verbund ist für die gesamte Organisation deaktiviert.

Ihre Zugriffs-Edge-Konfigurationseinstellungen können mithilfe von Windows PowerShell zurückgegeben werden. Führen Sie dazu den folgenden Windows PowerShell Befehl aus:

`Get-CsAccessEdgeConfiguration`

Dieser Befehl gibt wiederum Daten wie die folgende zurück:

Identity: Global

AllowAnonymousUsers: false

AllowFederatedUsers: false

AllowOutsideUsers: false

Beclearing: false

EnablePartnerDiscovery: false

EnableArchivingDisclaimer: false

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

Wenn die **AllowFederatedUsers** -Eigenschaft auf true festgelegt ist, bedeutet dies, dass der Verbund für Ihre Organisation aktiviert ist. (Das Festlegen von **AllowFederatedUsers** auf "true" bedeutet auch, dass Ihre lokalen Benutzer in einem geteilten Domänen Szenario nahtlos mit ihren in-the-Cloud-Benutzern kommunizieren können.)

Informationen zum Abrufen der FQDN-und Porteinstellungen für Ihre Edgeserver finden Sie in der vorherigen Aufgabe (Edgeserver und deren Einstellungen).

Das Aktivieren von Verbund auf globaler Ebene bedeutet nur, dass Benutzer potenziell mit Verbundbenutzern kommunizieren können. Um zu ermitteln, ob einzelne Benutzer tatsächlich mit Verbundbenutzern kommunizieren können, müssen Sie die Zugriffsrichtlinie für externe Benutzer überprüfen, die diesem Benutzer zugewiesen ist.

Mithilfe von Windows PowerShell können externe Benutzerzugriffs Informationen zurückgegeben werden. Mit diesem Befehl werden beispielsweise Informationen für die globale Richtlinie für den Zugriff auf externe Benutzer zurückgegeben:

`Get-CsExternalAccessPolicy -Identity "Global"`

Und dieser Befehl gibt Informationen zu allen Richtlinien für den externen Benutzer Zugriff zurück:

`Get-CsExternalAccessPolicy`

Die zurückgegebenen Informationen ähneln Folgendem:

Identity: false

Beschreibung

EnableFederationAccess: false

EnablePublicCloudAccess: false

EnablePublicCloudAccessAudioVideoAccess: false

EnableOutsideAccess: false

Wenn **EnableFederationAccess** auf true festgelegt ist, können Benutzer, die von der angegebenen Richtlinie verwaltet werden, mit Verbundbenutzern kommunizieren.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Überprüfen der Archivierungseinstellungen

Überprüfen Sie die Archivierungseinstellungen für die interne und die Verbundkommunikation. Bevor Sie die Einstellungen für die interne und externe Archivierung überprüfen, sollten Sie überprüfen, ob die Archivierung aktiviert ist.

Die Archivierungs Konfigurationseinstellungen können mit Windows PowerShell und dem Cmdlet Get-CsArchivingConfiguration überprüft werden:

`Get-CsArchivingConfiguration -Identity "Global"`

Beachten Sie, dass Archivierungseinstellungen auch auf Standortebene konfiguriert werden können. Verwenden Sie diesen Befehl, um Informationen zu allen Archivierungseinstellungen zurückzugeben:

`Get-CsArchivingConfiguration`

Das Get-CsArchivingConfiguration-Cmdlet gibt Daten ähnlich der folgenden zurück:

Identity: Global

Eigenschaft "enablearchiving: false

"Enablepurging": false

"Purgeexportedarchivesonly": false

BlockOnArchiveFailure: false

"Keeparchivingdatafordays": 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

CachePurgingInterval: 24

Wenn die Eigenschaft "enablearchiving-Eigenschaft auf false festgelegt ist, bedeutet dies, dass keine Kommunikationssitzungen archiviert werden. Wenn Sie nur Chatsitzungen archivieren möchten, verwenden Sie einen Befehl wie den folgenden, um die Archivierung von Sofortnachrichtensitzungen zu aktivieren:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Verwenden Sie diesen Befehl zum Archivieren von Konferenzsitzungen und Chatnachrichten Sitzungen:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Wenn Sie Ihre aktuellen Archivierungseinstellungen mit den Standardeinstellungen vergleichen möchten, führen Sie den folgenden Windows PowerShell Befehl aus:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Mit diesem Befehl wird eine nur im Arbeitsspeicher vorhandene Instanz der globalen Archivierungs Konfigurationseinstellungen erstellt. Hierbei handelt es sich nicht um eine echte Sammlung von Einstellungen, die von lync Server verwendet werden. Es werden jedoch die Standardwerte für alle Archivierungs Konfigurationseigenschaften angezeigt.

Sie können diesen Befehl auch verwenden, um den FQDN ihrer Archivierungsserver zurückzugeben:

`Get-CsService -ArchivingServer`

Nachdem Sie überprüft haben, dass die Archivierung aktiviert ist, können Sie Ihre Archivierungsrichtlinien anzeigen, um festzustellen, ob interne und externe Kommunikationssitzungen archiviert werden.

Informationen zur Archivierungsrichtlinie können mithilfe des Cmdlets Get-CsArchivingPolicy abgerufen werden. Mit diesem Befehl werden beispielsweise Informationen zur globalen Archivierungsrichtlinie zurückgegeben:

`Get-CsArchivingPolicy -Identity "Global"`

Da Archivierungsrichtlinien auch auf Standort-und Benutzerebene konfiguriert werden können, möchten Sie möglicherweise auch diesen Befehl verwenden, der Informationen zu allen Archivierungsrichtlinien zurückgibt:

`Get-CsArchivingPolicy`

Die Informationen, die Sie von Get-CsArchivingPolicy erhalten, ähneln Ihnen:

Identity: Global

Beschreibung

"Archiveinternal": false

"Archiveexternal": false

Beachten Sie, dass die interne und externe Archivierung standardmäßig in einer Archivierungsrichtlinie deaktiviert ist.

</div>

<div>

## <a name="check-cdr-settings"></a>Überprüfen der KDS-Einstellungen

Überprüfen Sie die KDS-Einstellungen (Call Detail Record) für die Aufzeichnung von Peer-zu-Peer-, Konferenz-und Sprachanruf Details. Ausführliche Informationen zu ihren KDS-Einstellungen können mit dem Cmdlet **Get-CsCdrConfiguration** zurückgegeben werden. Mit diesem Befehl werden beispielsweise Informationen über die globale Auflistung von KDS-Konfigurationseinstellungen zurückgegeben:

`Get-CsCdrConfiguration -Identity "Global"`

Da KDS auch auf Standortebene konfiguriert werden kann, möchten Sie möglicherweise auch diesen Befehl ausführen, der Informationen zu allen KDS-Konfigurationseinstellungen zurückgibt:

`Get-CsCdrConfiguration`

Das Cmdlet Get-CsCdrConfiguration gibt für jede Auflistung von KDS-Konfigurationseinstellungen ähnliche Informationen zurück:

Identity: Global

"Enablecdr": true

"Enablepurging": true

"Keepcalldetailfordays": 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Ähnliche Informationen können für die QoE-Überwachung mithilfe des Get-CsQoEConfiguration-Cmdlets zurückgegeben werden. Mit diesem Befehl werden beispielsweise Informationen über die globale Auflistung von QoE-Konfigurationseinstellungen zurückgegeben:

`Get-QoEConfiguration -Identity "Global"`

Diese Informationen ähneln Ihnen:

Identity: Global

ExternalConsumerIssuedCertId :

"Enablepurging": true

"Keepqoedatafordays": 60

PurgeHourOfDay: 1

EnableExternalConsumer: false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Wenn Sie Ihre aktuellen KDS-Einstellungen mit den standardmäßigen KDS-Einstellungen vergleichen möchten, können Sie die Standardwerte überprüfen, indem Sie den folgenden Befehl ausführen:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Ebenso können die Standardwerte für die QoE-Überwachung mithilfe dieses Befehls abgerufen werden:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Sie können den FQDN ihrer Monitoring Server auch zurückgeben, indem Sie den folgenden Befehl ausführen:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Spracheinstellungen überprüfen

Die VoIP-Einstellungen, die für Administratoren typischerweise wichtig sind, sind in VoIP-Richtlinien und VoIP-Routen enthalten: VoIP-Richtlinien enthalten die Einstellungen, die die für einzelne Benutzer verfügbaren Funktionen bestimmen (beispielsweise die Möglichkeit, Anrufe weiterzuleiten oder zu übertragen), während VoIP-Routen bestimmen, wie (und ob) Anrufe über das PSTN weitergeleitet werden.

Informationen zur VoIP-Richtlinie können mithilfe von Windows PowerShell abgerufen werden. Mit diesem Befehl werden beispielsweise Informationen zur globalen VoIP-Richtlinie zurückgegeben:

`Get-CsVoicePolicy -Identity "Global"`

Und dieser Befehl gibt Informationen zu allen VoIP-Richtlinien zurück, die für die Verwendung in der Organisation konfiguriert sind:

`Get-CsVoicePolicy`

Die vom Cmdlet Get-CsVoicePolicy zurückgegebenen Informationen ähneln wie folgt:

Identity: Global

PstnUsages{}

Beschreibung

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Name: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: false

EnableMaliciousCallTracing: false

EnableBWPolicyOverride: false

PreventPSTNTollBypass: false

Sie können auch Abfragen erstellen, die eine Teilmenge ihrer VoIP-Richtlinien zurückgegeben haben. Mit diesem Befehl werden beispielsweise alle VoIP-Richtlinien zurückgegeben, die die Anrufweiterleitung ermöglichen:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Und dieser Befehl gibt alle VoIP-Richtlinien zurück, die die Anrufweiterleitung nicht zulassen:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Verwenden Sie in Windows PowerShell das Cmdlet Get-CsVoiceRouting, um Informationen zu Ihren VoIP-Routen zurückzugeben:

`Get-CsVoiceRoute`

Dieser Befehl gibt Informationen wie diese für alle VoIP-Routen zurück:

Identity: LocalRoute

Priorität: 0

Beschreibung

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList :{}

Name: LocalRoute

SuppressCallerId :

AlternateCallerId :

In lync Server können Sie VoIP-Routen erstellen, die nicht über ein PSTN verwendet werden und kein PSTN-Gateway angeben. Es ist jedoch nicht möglich, Anrufe tatsächlich über eine VoIP-Route weiterzuleiten, für die diese beiden Eigenschaftswerte nicht konfiguriert sind. Aus diesem Grund kann es sinnvoll sein, diesen Befehl regelmäßig auszuführen, wodurch die Identität einer VoIP-Route zurückgegeben wird, die nicht über ein PSTN verwendet wird:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Auf ähnliche Weise gibt dieser Befehl die Identität einer VoIP-Route zurück, die nicht für ein PSTN-Gateway konfiguriert wurde:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Überprüfen der Einstellungen für die Konferenzzentrale

Überprüfen der Einstellungen für die Konferenzzentrale für PSTN-Einwahlkonferenzen. Einstellungen für die Konferenzzentrale können nur mithilfe des Cmdlets **Get-CsDialInConferencingConfiguration** abgerufen werden. Diese Einstellungen stehen im lync Server-Systemsteuerung nicht zur Verfügung. Verwenden Sie zum Anzeigen der Einstellungen für die Konferenzzentrale einen Windows PowerShell Befehl wie den folgenden, der die globale Auflistung der Einstellungen für die Konferenzzentrale zurückgibt:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Beachten Sie, dass die Einstellungen für die Konferenzzentrale auch auf Standortebene konfiguriert werden können. Wenn Sie Informationen zu allen Einstellungen für die Konferenzzentrale zurückgeben möchten, verwenden Sie stattdessen den folgenden Befehl:

`Get-CsDialInConferencingConfiguration`

Das Get-CsDialInConferencingConfiguration-Cmdlet gibt Daten ähnlich der folgenden zurück:

Identity: Global

EntryExitAnnouncementsType : UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: false

Wenn EntryExitAnnouncementsEnabledByDefault auf false festgelegt ist, bedeutet dies, dass die Ankündigungen für Konferenzen deaktiviert sind. Um ein-und Ausstiegs Ankündigungen zu aktivieren, führen Sie einen Windows PowerShell Befehl wie den folgenden aus:

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

