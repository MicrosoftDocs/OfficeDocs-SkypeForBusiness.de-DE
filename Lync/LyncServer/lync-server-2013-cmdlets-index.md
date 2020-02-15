---
title: 'Lync Server 2013: Cmdlets-Index'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca2367ebe47d5abde48a11f06be49d4a6d6ea35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013-Cmdlets-Index

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-04-12_

Microsoft lync Server 2013 ist mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren lync Server 2013 über die Befehlszeile verwalten können. Die lync Server-Cmdlets werden in der Regel mit dem lync Server-Verwaltungsshell verwendet. Eine Möglichkeit zum Verwenden des lync Server-Verwaltungsshell ist die Anmeldung an einem Computer, auf dem ein lync Server Dienst oder eine Server Rolle läuft, klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**. Nachdem die Verwaltungsshell geöffnet ist, können Sie die Hilfe für ein Cmdlet direkt von der Befehlszeile aus abrufen, indem Sie einen Befehl wie den folgenden eingeben:

    Get-Help New-CsVoicePolicy -Full

Der obige Befehl ruft die vollständige Hilfe ab, die für das Cmdlet **New-CsVoicePolicy** zur Verfügung steht. Wenn Sie Hilfe zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie die Hilfe abrufen möchten.

Geben Sie an der lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der für die Verwaltung von lync Server verfügbaren Cmdlets abzurufen:

    Get-Command * -Module Lync -CommandType cmdlet

Ausführliche Informationen zur Verwendung der lync Server-Verwaltungsshell finden Sie im lync Server Windows PowerShell Blog unter [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150).

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013-Cmdlets

Im folgenden finden Sie eine Liste der Cmdlets, die mit lync Server 2013 ausgeliefert werden:

  - [Add-CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))

  - [Genehmigen-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - [Sicherung-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

  - [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

  - [Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [Convert-csuserdata "](https://technet.microsoft.com/library/JJ205337(v=OCS.15))

  - [Debug-csaddressbookreplication "](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

  - [Debug-csintrapoolreplication "](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

  - [Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - [Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - [Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - [Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - [Disable-csmeetingroom "](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - [Disable-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - [Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - [Enable-csmeetingroom "](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - [Enable-csreplica "](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - [Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))

  - [Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

  - [Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - [Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - [Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))

  - [Export-csuserdata "](https://technet.microsoft.com/library/JJ204897(v=OCS.15))

  - [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - [Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))

  - [Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

  - [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - [Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

  - [Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - [Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

  - [Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

  - [Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - [Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))

  - [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - [Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - [Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))

  - [Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))

  - [Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - [Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - [Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))

  - [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - [Get-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

  - [Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - [Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - [Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))

  - [Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - [Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - [Get-csclientaccesslicense abrufen](https://technet.microsoft.com/library/JJ204853(v=OCS.15))

  - [Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))

  - [Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))

  - [Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))

  - [Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))

  - [Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))

  - [Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))

  - [Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))

  - [Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))

  - [Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - [Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - [Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - [Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - [Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - [Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - [Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))

  - [Get-csdatabasemirrorstate "](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

  - [Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - [Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - [Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - [Get-CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))

  - [Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))

  - [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - [Get-csfipsconfiguration "](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))

  - [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - [Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - [Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - [Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - [Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - [Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - [Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - [Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - [Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - [Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))

  - [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

  - [Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))

  - [Get-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - [Get-csmeetingroom "](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))

  - [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - [Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - [Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

  - [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - [Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - [Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - [Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - [Get-csoauthconfiguration "](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Get-csoauthserver "](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - [Get-cspartnerapplication "](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [Get-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [Get-cspersistentchateligibleprincipal "](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

  - [Get-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [Get-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [Get-cspersistentchatstate "](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - [Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

  - [Get-cspoolbackuprelationship "](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

  - [Get-cspoolupgradereadinessstate "](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - [Get-cspresenceprovider "](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - [Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - [Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - [Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))

  - [Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - [Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - [Get-csreportingconfiguration "](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - [Get-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))

  - [Get-CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))

  - [Get-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))

  - [Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))

  - [Get-CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))

  - [Get-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))

  - [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - [Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))

  - [Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

  - [Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

  - [Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - [Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - [Get-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))

  - [Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - [Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - [Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - [Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - [Get-cstrunk "](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

  - [Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - [Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))

  - [Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))

  - [Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))

  - [Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))

  - [Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - [Get-CsUICulture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))

  - [Get-CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))

  - [Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))

  - [Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - [Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))

  - [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - [Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - [Get-csuserservicespolicy "](https://technet.microsoft.com/library/JJ204838(v=OCS.15))

  - [Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - [Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))

  - [Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - [Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - [Get-csvoiceroutingpolicy "](https://technet.microsoft.com/library/JJ204940(v=OCS.15))

  - [Get-csvoicetestconfiguration getestet](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - [Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - [Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - [Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - [Get-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [Get-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))

  - [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))

  - [Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))

  - [Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - [Grant-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - [Grant-csuserservicespolicy "](https://technet.microsoft.com/library/JJ205388(v=OCS.15))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - [Grant-csvoiceroutingpolicy "](https://technet.microsoft.com/library/JJ205141(v=OCS.15))

  - [Import-CsAnnouncementFile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))

  - [Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - [Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

  - [Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

  - [Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))

  - [Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))

  - [Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - [Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

  - [Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))

  - [Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))

  - [Import-csuserdata "](https://technet.microsoft.com/library/JJ205373(v=OCS.15))

  - [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

  - [Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

  - [Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - [Invoke-csdatabasefailover "](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

  - [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

  - [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

  - [Invoke-CsUcsRollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))

  - [Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))

  - [CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))

  - [CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - [Csmeetingroom "](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))

  - [CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))

  - [New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - [New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - [New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - [New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - [New-CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))

  - [New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - [New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - [New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))

  - [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - [New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - [New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - [New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))

  - [New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))

  - [New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))

  - [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))

  - [New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))

  - [New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))

  - [New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))

  - [New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))

  - [New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))

  - [New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - [New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - [New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - [New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - [New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))

  - [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - [New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - [New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

  - [New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - [New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - [New-csextendedtest "](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

  - [New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - [New-CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))

  - [New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - [New-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - [New-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - [New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - [New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

  - [New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

  - [New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - [New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - [New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))

  - [New-CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))

  - [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - [New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))

  - [New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - [New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

  - [New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

  - [New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - [New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - [New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))

  - [New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - [New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - [New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - [New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - [New-csoauthserver "](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - [New-cspartnerapplication "](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [New-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [New-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [New-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [New-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - [New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - [New-cspresenceprovider "](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - [New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - [New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - [New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))

  - [New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - [New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - [New-csreportingconfiguration "](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - [New-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))

  - [New-CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))

  - [New-CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))

  - [New-CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))

  - [New-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))

  - [New-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))

  - [New-CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))

  - [New-CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))

  - [New-CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))

  - [New-CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))

  - [New-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))

  - [New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - [New-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))

  - [New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

  - [New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - [New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

  - [New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - [New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

  - [New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

  - [New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

  - [New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

  - [New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

  - [New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

  - [New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

  - [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

  - [New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - [New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - [New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - [New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))

  - [New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))

  - [New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))

  - [New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))

  - [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - [New-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))

  - [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - [New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - [New-csuserservicespolicy "](https://technet.microsoft.com/library/JJ205072(v=OCS.15))

  - [New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))

  - [New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - [New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - [New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

  - [New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - [New-csvoiceroutingpolicy "](https://technet.microsoft.com/library/JJ205135(v=OCS.15))

  - [New-csvoicetestconfiguration getestet](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - [New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))

  - [New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - [New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

  - [New-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Veröffentlichen-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [Veröffentlichen-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - [Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - [Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - [Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [Remove-CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))

  - [Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - [Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - [Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))

  - [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - [Remove-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - [Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - [Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))

  - [Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - [Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - [Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))

  - [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))

  - [Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))

  - [Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))

  - [Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))

  - [Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))

  - [Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))

  - [Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - [Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - [Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - [Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - [Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))

  - [Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - [Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - [Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - [Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - [Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - [Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - [Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - [Remove-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - [Remove-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - [Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))

  - [Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - [Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - [Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - [Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - [Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - [Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - [Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - [Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - [Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - [Remove-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))

  - [Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))

  - [Remove-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))

  - [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - [Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))

  - [Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - [Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - [Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - [Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - [Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - [Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - [Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - [Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - [Remove-csoauthserver "](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Remove-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - [Remove-cspartnerapplication "](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Remove-cspersistentchataddin "](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [Remove-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [Remove-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [Remove-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

  - [Remove-cspersistentchatmessage "](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [Remove-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - [Remove-cspresenceprovider "](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - [Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - [Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - [Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))

  - [Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - [Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - [Remove-csreportingconfiguration "](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - [Remove-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))

  - [Remove-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))

  - [Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))

  - [Remove-CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))

  - [Remove-CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))

  - [Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - [Remove-CsServerApplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))

  - [Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - [Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - [Remove-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))

  - [Remove-CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))

  - [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - [Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - [Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - [Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))

  - [Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))

  - [Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))

  - [Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))

  - [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - [Remove-CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))

  - [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - [Remove-csuserservicespolicy "](https://technet.microsoft.com/library/JJ204629(v=OCS.15))

  - [Remove-csadminrole](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

  - [Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - [Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))

  - [Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - [Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - [Remove-csvoiceroutingpolicy "](https://technet.microsoft.com/library/JJ204799(v=OCS.15))

  - [Remove-csvoicetestconfiguration getestet](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - [Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - [Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - [Remove-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

  - [REVOKE-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

  - [REVOKE-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - [REVOKE-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - [Gruppe-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [Gruppe-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

  - [Gruppe-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - [Gruppe-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

  - [Gruppe-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

  - [Gruppe-CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))

  - [Gruppe-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))

  - [Gruppe-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

  - [Gruppe-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

  - [Gruppe-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

  - [Gruppe-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

  - [Gruppe-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))

  - [Gruppe-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

  - [Gruppe-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

  - [Gruppe-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

  - [Gruppe-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

  - [Gruppe-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))

  - [Gruppe-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))

  - [Gruppe-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

  - [Gruppe-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

  - [Gruppe-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - [Gruppe-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))

  - [Gruppe-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))

  - [Gruppe-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))

  - [Gruppe-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))

  - [Gruppe-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))

  - [Gruppe-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))

  - [Gruppe-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))

  - [Gruppe-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))

  - [Gruppe-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

  - [Gruppe-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

  - [Gruppe-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

  - [Gruppe-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

  - [Gruppe-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

  - [Gruppe-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

  - [Gruppe-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))

  - [Gruppe-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

  - [Gruppe-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

  - [Gruppe-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

  - [Gruppe-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

  - [Gruppe-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

  - [Gruppe-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

  - [Gruppe-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15)) Gruppe-CsDialPlan

  - [Gruppe-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

  - [Gruppe-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

  - [Gruppe-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

  - [Gruppe-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

  - [Gruppe-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))

  - [Gruppe-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

  - [Gruppe-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

  - [Gruppe-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

  - [Gruppe-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))

  - [Gruppe-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

  - [Gruppe-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

  - [Gruppe-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - [Gruppe-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

  - [Gruppe-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

  - [Gruppe-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

  - [Gruppe-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

  - [Gruppe-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

  - [Gruppe-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

  - [Gruppe-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

  - [Gruppe-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - [Gruppe-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))

  - [Gruppe-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))

  - [Gruppe-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

  - [Gruppe-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))

  - [Gruppe-csmediationserver begrenzen](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

  - [Gruppe-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

  - [Gruppe-csmeetingroom "](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

  - [Gruppe-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))

  - [Gruppe-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

  - [Gruppe-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

  - [Gruppe-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

  - [Gruppe-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

  - [Gruppe-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

  - [Gruppe-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

  - [Gruppe-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

  - [Gruppe-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

  - [Gruppe-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

  - [Gruppe-csoauthconfiguration "](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

  - [Gruppe-csoauthserver "](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

  - [Gruppe-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

  - [Gruppe-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

  - [Gruppe-cspartnerapplication "](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

  - [Gruppe-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

  - [Gruppe-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

  - [Gruppe-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

  - [Gruppe-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

  - [Gruppe-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

  - [Gruppe-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

  - [Gruppe-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

  - [Gruppe-cspersistentchatstate "](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

  - [Gruppe-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

  - [Gruppe-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

  - [Gruppe-cspresenceprovider "](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

  - [Gruppe-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

  - [Gruppe-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

  - [Gruppe-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

  - [Gruppe-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

  - [Gruppe-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

  - [Gruppe-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))

  - [Gruppe-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

  - [Gruppe-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

  - [Gruppe-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

  - [Gruppe-csreportingconfiguration "](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

  - [Gruppe-CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))

  - [Gruppe-CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))

  - [Gruppe-CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))

  - [Gruppe-CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))

  - [Gruppe-CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))

  - [Gruppe-CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))

  - [Gruppe-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

  - [Gruppe-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))

  - [Gruppe-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

  - [Gruppe-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

  - [Gruppe-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

  - [Gruppe-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

  - [Gruppe-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))

  - [Gruppe-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

  - [Gruppe-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

  - [Gruppe-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - [Gruppe-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))

  - [Gruppe-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))

  - [Gruppe-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))

  - [Gruppe-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

  - [Gruppe-CsUICulture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))

  - [Gruppe-CsUnassignedNumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))

  - [Gruppe-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))

  - [Gruppe-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))

  - [Gruppe-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

  - [Gruppe-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

  - [Gruppe-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

  - [Gruppe-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

  - [Gruppe-csuserservicespolicy "](https://technet.microsoft.com/library/JJ205414(v=OCS.15))

  - [Gruppe-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

  - [Gruppe-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))

  - [Gruppe-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - [Gruppe-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - [Gruppe-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - [Gruppe-csvoiceroutingpolicy "](https://technet.microsoft.com/library/JJ205313(v=OCS.15))

  - [Gruppe-csvoicetestconfiguration getestet](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - [Gruppe-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - [Gruppe-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

  - [Gruppe-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

  - [Gruppe-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

  - [Gruppe-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

  - [Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - [Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

  - [Sync-csuserdata "](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

  - [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

  - [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

  - [Test-csasconference "](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - [Test-CsAudioConferencingProvider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))

  - [Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - [Test-csavedgeconnectivity "](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

  - [Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

  - [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

  - [Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - [Test-csdataconference "](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - [Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

  - [Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

  - [Test-csexstorageconnectivity "](https://technet.microsoft.com/library/JJ204740(v=OCS.15))

  - [Test-csexstoragenotification "](https://technet.microsoft.com/library/JJ205331(v=OCS.15))

  - [Test-csexumconnectivity "](https://technet.microsoft.com/library/JJ204784(v=OCS.15))

  - [Test-csexumvoicemail "](https://technet.microsoft.com/library/JJ205058(v=OCS.15))

  - [Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

  - [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

  - [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

  - [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

  - [Test-csintertrunkrouting "](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

  - [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

  - [Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

  - [Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - [Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

  - [Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))

  - [Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))

  - [Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))

  - [Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

  - [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

  - [Test-cspersistentchatmessage "](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

  - [Test-csphonebootstrap aus](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

  - [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

  - [Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

  - [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

  - [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

  - [Test-csreplica "](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

  - [Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

  - [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

  - [Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

  - [Test-CsUnifiedContactStore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))

  - [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

  - [Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

  - [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

  - [Test-csvoicetestconfiguration getestet](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

  - [Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

  - [Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

  - [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - [Test-cswebscheduler "](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

  - [Test-csxmppim "](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

  - [Deinstallieren-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [Deinstallieren-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [Aufheben der Veröffentlichung-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

  - [Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

  - [Update-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))

  - [Update-csuserdata "](https://technet.microsoft.com/library/JJ205358(v=OCS.15))

  - [Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

