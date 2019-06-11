---
title: 'Lync Server 2013: Cmdlets-Index'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d18b599792d2599d96b4775aa37a4178f99d1e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013-Cmdlets-Index

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-04-12_

Microsoft lync Server 2013 ist mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren lync Server 2013 über die Befehlszeile verwalten können. Die lync Server-Cmdlets werden in der Regel mit der lync Server-Verwaltungsshell verwendet. Eine Möglichkeit, die lync Server-Verwaltungsshell zu verwenden, ist die Anmeldung an einem Computer, auf dem ein lync Server-Dienst oder eine Serverrolle ausgeführt wird, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell. **. Nach dem Öffnen der Verwaltungsshell können Sie Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl ähnlich der folgenden eingeben:

    Get-Help New-CsVoicePolicy -Full

Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab. Wenn Sie Hilfeinformationen zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.

Wenn Sie eine vollständige Liste der für die Verwaltung von lync Server verfügbaren Cmdlets abrufen möchten, geben Sie Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:

    Get-Command * -Module Lync -CommandType cmdlet

Ausführliche Informationen zur Verwendung der lync Server-Verwaltungsshell finden Sie im Windows PowerShell-Blog von [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150)lync Server unter.

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013-Cmdlets

Es folgt eine Liste der Cmdlets, die im Lieferumfang von lync Server 2013 enthalten sind:

  - [Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))

  - [Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))

  - [Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))

  - [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))

  - [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))

  - [Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))

  - [Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))

  - [Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))

  - [Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))

  - [Deaktivieren-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))

  - [Deaktivieren-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))

  - [Deaktivieren-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - [Deaktivieren-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Deaktivieren-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - [Deaktivieren-CsUser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))

  - [Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - [Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))

  - [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - [Enable-CsUser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))

  - [Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))

  - [Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - [Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))

  - [Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))

  - [Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))

  - [Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))

  - [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))

  - [Get-CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))

  - [Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))

  - [Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))

  - [Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))

  - [Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))

  - [Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))

  - [Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))

  - [Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))

  - [Get-CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))

  - [Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - [Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))

  - [Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))

  - [Get-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))

  - [Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))

  - [Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))

  - [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))

  - [Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))

  - [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))

  - [Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))

  - [Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))

  - [Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - [Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))

  - [Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))

  - [Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))

  - [Get-CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))

  - [Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))

  - [Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))

  - [Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))

  - [Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))

  - [Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))

  - [Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))

  - [Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))

  - [Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))

  - [Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))

  - [Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))

  - [Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - [Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))

  - [Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))

  - [Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - [Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))

  - [Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))

  - [Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))

  - [Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))

  - [Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))

  - [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))

  - [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))

  - [Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))

  - [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))

  - [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))

  - [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))

  - [Get-CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))

  - [Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))

  - [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))

  - [Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))

  - [Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))

  - [Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))

  - [Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))

  - [Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))

  - [Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))

  - [Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))

  - [Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))

  - [Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))

  - [Get-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))

  - [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))

  - [Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))

  - [Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))

  - [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))

  - [Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))

  - [Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

  - [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))

  - [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))

  - [Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))

  - [Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))

  - [Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))

  - [Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))

  - [Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - [Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))

  - [Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))

  - [Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))

  - [Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))

  - [Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))

  - [Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))

  - [Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))

  - [Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))

  - [Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))

  - [Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))

  - [Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))

  - [Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

  - [Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - [Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - [Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))

  - [Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))

  - [Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - [Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))

  - [Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))

  - [Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))

  - [Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))

  - [Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))

  - [Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))

  - [Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))

  - [Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))

  - [Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))

  - [Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))

  - [Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))

  - [Get-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))

  - [Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

  - [Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))

  - [Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))

  - [Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))

  - [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - [Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))

  - [Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - [Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))

  - [Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))

  - [Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - [Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

  - [Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - [Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))

  - [Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))

  - [Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))

  - [Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))

  - [Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))

  - [Get-CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))

  - [Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))

  - [Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))

  - [Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))

  - [Get-CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))

  - [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))

  - [Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))

  - [Get-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))

  - [Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))

  - [Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))

  - [Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))

  - [Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))

  - [Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))

  - [Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))

  - [Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))

  - [Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))

  - [Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))

  - [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))

  - [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))

  - [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))

  - [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))

  - [Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))

  - [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))

  - [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))

  - [Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))

  - [Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))

  - [Grant-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))

  - [Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))

  - [Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))

  - [Importieren-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))

  - [Importieren-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

  - [Importieren-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))

  - [Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))

  - [Importieren-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))

  - [Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))

  - [Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))

  - [Importieren-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))

  - [Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))

  - [Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))

  - [Installieren-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))

  - [Installieren-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

  - [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))

  - [Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))

  - [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))

  - [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))

  - [Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))

  - [Sperren-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

  - [Zusammenführen – CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))

  - [Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - [Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))

  - [Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - [Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - [Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))

  - [Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))

  - [Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))

  - [Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))

  - [Verschieben-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))

  - [Verschieben-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))

  - [Neu – CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))

  - [Neu – CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))

  - [Neu – CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - [New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))

  - [Neu – CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))

  - [Neu – CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))

  - [Neu – CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))

  - [New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))

  - [Neu – CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))

  - [Neu – CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))

  - [Neu – CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - [Neu – CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))

  - [Neu – CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))

  - [Neu – CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))

  - [Neu – CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))

  - [Neu – CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))

  - [New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))

  - [Neu – CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))

  - [New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))

  - [New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))

  - [New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))

  - [New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))

  - [New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))

  - [New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))

  - [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))

  - [Neu – CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))

  - [Neu – CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))

  - [New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))

  - [Neu – CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))

  - [Neu – CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))

  - [New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))

  - [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))

  - [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))

  - [New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))

  - [New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))

  - [Neu – CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))

  - [Neu – CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))

  - [New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [Neu – CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))

  - [Neu – CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))

  - [Neu – CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - [Neu – CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))

  - [Neu – CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

  - [New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))

  - [New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))

  - [Neu – CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))

  - [New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))

  - [Neu – CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))

  - [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))

  - [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))

  - [New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))

  - [New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))

  - [New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))

  - [New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))

  - [New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))

  - [New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))

  - [New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))

  - [New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))

  - [New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))

  - [New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))

  - [New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))

  - [New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [Neu – CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))

  - [New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))

  - [New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))

  - [New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))

  - [New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))

  - [New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))

  - [New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))

  - [New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))

  - [New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))

  - [New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))

  - [New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))

  - [Neu – CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))

  - [Neu – CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))

  - [Neu – CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - [New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))

  - [Neu – CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))

  - [Neu – CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))

  - [New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))

  - [Neu – CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))

  - [Neu – CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))

  - [Neu – CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))

  - [Neu – CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))

  - [Neu – CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))

  - [Neu – CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))

  - [New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))

  - [Neu – CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))

  - [Neu – CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))

  - [Neu – CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))

  - [Neu – CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))

  - [Neu – CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))

  - [Neu – CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))

  - [Neu – CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))

  - [Neu – CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))

  - [Neu – CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))

  - [New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))

  - [Neu – CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

  - [Neu – CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

  - [Neu – CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

  - [Neu – CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

  - [Neu – CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

  - [Neu – CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

  - [Neu – CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

  - [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

  - [Neu – CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - [Neu – CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))

  - [Neu – CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - [New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))

  - [New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))

  - [New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))

  - [New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))

  - [Neu – CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))

  - [New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))

  - [Neu – CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))

  - [Neu – CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))

  - [New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))

  - [Neu – CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))

  - [Neu – CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))

  - [Neu – CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))

  - [Neu – CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

  - [Neu – CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))

  - [New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))

  - [Neu – CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))

  - [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))

  - [New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))

  - [Neu – CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))

  - [New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

  - [Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))

  - [Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))

  - [Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - [Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - [Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))

  - [Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))

  - [Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))

  - [Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))

  - [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))

  - [Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))

  - [Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))

  - [Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - [Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))

  - [Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))

  - [Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))

  - [Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))

  - [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))

  - [Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))

  - [Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))

  - [Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))

  - [Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))

  - [Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))

  - [Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - [Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))

  - [Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))

  - [Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))

  - [Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))

  - [Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))

  - [Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))

  - [Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))

  - [Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))

  - [Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))

  - [Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))

  - [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))

  - [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))

  - [Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))

  - [Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))

  - [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - [Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))

  - [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))

  - [Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))

  - [Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))

  - [Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - [Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))

  - [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))

  - [Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))

  - [Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))

  - [Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))

  - [Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))

  - [Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))

  - [Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))

  - [Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))

  - [Remove-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))

  - [Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))

  - [Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))

  - [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))

  - [Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))

  - [Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))

  - [Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))

  - [Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))

  - [Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))

  - [Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))

  - [Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))

  - [Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))

  - [Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - [Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))

  - [Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))

  - [Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))

  - [Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))

  - [Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))

  - [Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))

  - [Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))

  - [Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))

  - [Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))

  - [Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))

  - [Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))

  - [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))

  - [Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))

  - [Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - [Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))

  - [Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))

  - [Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))

  - [Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))

  - [Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))

  - [Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))

  - [Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))

  - [Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))

  - [Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))

  - [Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))

  - [Remove-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))

  - [Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))

  - [Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))

  - [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - [Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))

  - [Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))

  - [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - [Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))

  - [Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))

  - [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - [Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))

  - [Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))

  - [Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))

  - [Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))

  - [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))

  - [Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))

  - [Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))

  - [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))

  - [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))

  - [Remove-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))

  - [Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))

  - [Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))

  - [Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))

  - [Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))

  - [Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))

  - [Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))

  - [Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))

  - [Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))

  - [Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))

  - [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))

  - [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))

  - [REVOKE-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))

  - [REVOKE-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))

  - [REVOKE-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))

  - [Satz-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

  - [Satz-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))

  - [Satz-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))

  - [Satz-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

  - [Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))

  - [Satz-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))

  - [Satz-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))

  - [Satz-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))

  - [Satz-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))

  - [Satz-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))

  - [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))

  - [Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))

  - [Satz-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))

  - [Satz-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))

  - [Satz-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

  - [Satz-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))

  - [Satz-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))

  - [Satz-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))

  - [Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))

  - [Satz-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))

  - [Satz-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))

  - [Satz-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))

  - [Satz-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))

  - [Satz-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))

  - [Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))

  - [Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))

  - [Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))

  - [Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))

  - [Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))

  - [Satz-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))

  - [Satz-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

  - [Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))

  - [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))

  - [Satz-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))

  - [Satz-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))

  - [Satz-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))

  - [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))

  - [Satz-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))

  - [Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))

  - [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))

  - [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))

  - [Satz-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15)) Satz-CsDialPlan

  - [Satz-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))

  - [Satz-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))

  - [Satz-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))

  - [Satz-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))

  - [Satz-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

  - [Satz-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))

  - [Satz-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))

  - [Satz-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

  - [Satz-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))

  - [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))

  - [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))

  - [Satz-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))

  - [Satz-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))

  - [Satz-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))

  - [Satz-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))

  - [Satz-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))

  - [Satz-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))

  - [Satz-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))

  - [Satz-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))

  - [Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))

  - [Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))

  - [Satz-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))

  - [Satz-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

  - [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))

  - [Satz-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))

  - [Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))

  - [Satz-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))

  - [Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))

  - [Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))

  - [Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))

  - [Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))

  - [Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))

  - [Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

  - [Satz-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

  - [Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))

  - [Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))

  - [Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))

  - [Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))

  - [Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))

  - [Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))

  - [Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))

  - [Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))

  - [Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))

  - [Satz-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))

  - [Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))

  - [Satz-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

  - [Satz-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))

  - [Satz-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))

  - [Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))

  - [Satz-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

  - [Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))

  - [Satz-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))

  - [Satz-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))

  - [Satz-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))

  - [Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))

  - [Satz-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))

  - [Satz-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))

  - [Satz-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))

  - [Satz-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))

  - [Satz-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))

  - [Satz-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))

  - [Satz-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))

  - [Satz-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))

  - [Satz-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))

  - [Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))

  - [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

  - [Satz-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

  - [Satz-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))

  - [Satz-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

  - [Satz-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))

  - [Satz-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - [Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))

  - [Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))

  - [Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))

  - [Satz-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))

  - [Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))

  - [Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))

  - [Satz-CsUser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))

  - [Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))

  - [Satz-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))

  - [Satz-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

  - [Satz-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))

  - [Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))

  - [Satz-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))

  - [Satz-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))

  - [Satz-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))

  - [Satz-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))

  - [Satz-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))

  - [Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))

  - [Satz-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))

  - [Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))

  - [Satz-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))

  - [Satz-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

  - [Anfang-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))

  - [Stopp-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))

  - [Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))

  - [Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))

  - [Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))

  - [Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))

  - [Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))

  - [Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))

  - [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))

  - [Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))

  - [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

  - [Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))

  - [Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))

  - [Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))

  - [Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))

  - [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))

  - [Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))

  - [Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))

  - [Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))

  - [Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

  - [Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))

  - [Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))

  - [Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

  - [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))

  - [Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))

  - [Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))

  - [Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))

  - [Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))

  - [Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))

  - [Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))

  - [Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))

  - [Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))

  - [Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))

  - [Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))

  - [Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))

  - [Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))

  - [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))

  - [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))

  - [Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))

  - [Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))

  - [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

  - [Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

  - [Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))

  - [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))

  - [Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))

  - [Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))

  - [Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))

  - [Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))

  - [Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))

  - [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

  - [Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

  - [Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

  - [Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

  - [Entsperren-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

  - [Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

  - [Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))

  - [Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))

  - [Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))

  - [Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))

  - [Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

