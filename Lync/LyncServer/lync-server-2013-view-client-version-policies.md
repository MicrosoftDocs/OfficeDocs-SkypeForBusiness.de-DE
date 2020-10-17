---
title: 'Lync Server 2013: Anzeigen von clientversionsrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edd1720040c31545bc8b83465109700db77b2b84
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506582"
---
# <a name="view-client-version-policies-in-lync-server-2013"></a><span data-ttu-id="5e970-102">Anzeigen von clientversionsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e970-102">View client version policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e970-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5e970-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5e970-104">Clientversionsrichtlinien werden verwendet, um eine Reihe von Regeln für die Client Versionsverwaltung auf globaler Ebene oder auf einen bestimmten Standort, einen Pool oder eine Gruppe von Benutzern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="5e970-104">Client version policies are used to apply a set of client versioning rules globally or to a particular site, pool, or group of users.</span></span> <span data-ttu-id="5e970-105">Sie können die clientversionsrichtlinien, die in ihrer lync Server 2013 Umgebung konfiguriert wurden, über lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e970-105">You can view the client version policies that have been configured in your Lync Server 2013 environment from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="5e970-106">So zeigen Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="5e970-106">To view client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5e970-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5e970-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5e970-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5e970-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5e970-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5e970-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5e970-110">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versionsrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="5e970-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="5e970-111">Wenn Sie die Regeln für eine clientversionsrichtlinie anzeigen möchten, doppelklicken Sie auf der Seite **clientversionsrichtlinie** auf die Richtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5e970-111">If you want to view the rules for a client version policy, on the **Client Version Policy** page, double-click the policy you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5e970-112">Anzeigen von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5e970-112">Viewing Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5e970-113">Sie können clientversionsrichtlinien anzeigen, indem Sie das Cmdlet **Get-CsClientVersionPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e970-113">You can view client version policies by using the **Get-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="5e970-114">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5e970-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5e970-115">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="5e970-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policies"></a><span data-ttu-id="5e970-116">So zeigen Sie clientversionsrichtlinien an</span><span class="sxs-lookup"><span data-stu-id="5e970-116">To view client version policies</span></span>

  - <span data-ttu-id="5e970-117">Um Informationen zu allen clientversionsrichtlinien anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5e970-117">To view information about all your client version policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicy
    
    <span data-ttu-id="5e970-118">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="5e970-118">That will return information similar to this:</span></span>
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

<span data-ttu-id="5e970-119">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5e970-119">For details, see the Help topic for the [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

