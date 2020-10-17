---
title: 'Lync Server 2013: Informationen zur trunkkonfiguration anzeigen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe7c828fe771a410825fd641c333a2230d7e9798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518372"
---
# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Anzeigen von trunk Konfigurationsinformationen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

  - Ob die Medienumgebung für Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.

  - Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe von lync Server-Systemsteuerung an

1.  Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf **trunk Konfiguration**.

2.  Auf der Registerkarte **trunk Configuration** wird eine Liste aller trunkkonfigurationseinstellungen-Auflistung angezeigt. für jede Auflistung werden Werte für die Eigenschaften **Name**, **Scope**, **State**und **Media Bypass** sowie die Anzahl der **PSTN-Verwendungen**, die Regeln für das **Anrufen von Nummern**und die **aufgerufenen Nummern Regeln** angezeigt, die der Auflistung zugeordnet sind. Um weitere Details zu einer Sammlung von trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die Sammlung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie detaillierte Informationen nur für eine Sammlung von trunkkonfigurationseinstellungen gleichzeitig anzeigen können.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Die SIP-Trunk-Konfigurationseinstellungen können mit lync Server PowerShell und dem Get-CsTrunkConfiguration-Cmdlet angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>So zeigen Sie SIP-Trunk-Konfigurationsinformationen an

  - Wenn Sie Informationen zu allen SIP-Trunk-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsTrunkConfiguration
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

