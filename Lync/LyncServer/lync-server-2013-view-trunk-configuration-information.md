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
ms.openlocfilehash: 3b1e232cda56258a530f1cd0f5a0106d9b7725ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="b49f8-102">Anzeigen von trunk Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b49f8-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b49f8-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b49f8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b49f8-p101">Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="b49f8-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="b49f8-106">Ob die Medienumgebung für Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b49f8-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="b49f8-107">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b49f8-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="b49f8-108">Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b49f8-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b49f8-109">Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="b49f8-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b49f8-110">Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="b49f8-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="b49f8-111">So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe von lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="b49f8-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b49f8-112">Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf **trunk Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b49f8-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="b49f8-113">Auf der Registerkarte **trunk Configuration** wird eine Liste aller trunkkonfigurationseinstellungen-Auflistung angezeigt. für jede Auflistung werden Werte für die Eigenschaften **Name**, **Scope**, **State**und **Media Bypass** sowie die Anzahl der **PSTN-Verwendungen**, die Regeln für das **Anrufen von Nummern**und die **aufgerufenen Nummern Regeln** angezeigt, die der Auflistung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b49f8-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="b49f8-114">Um weitere Details zu einer Sammlung von trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die Sammlung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b49f8-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="b49f8-115">Beachten Sie, dass Sie detaillierte Informationen nur für eine Sammlung von trunkkonfigurationseinstellungen gleichzeitig anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b49f8-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b49f8-116">Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b49f8-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b49f8-117">Die SIP-Trunk-Konfigurationseinstellungen können mit lync Server PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b49f8-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="b49f8-118">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b49f8-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="b49f8-119">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="b49f8-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="b49f8-120">So zeigen Sie SIP-Trunk-Konfigurationsinformationen an</span><span class="sxs-lookup"><span data-stu-id="b49f8-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="b49f8-121">Wenn Sie Informationen zu allen SIP-Trunk-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b49f8-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="b49f8-122">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="b49f8-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="b49f8-123">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="b49f8-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

