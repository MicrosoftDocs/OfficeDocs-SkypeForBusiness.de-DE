---
title: 'Lync Server 2013: Anzeigen von clientversionsrichtlinien Regeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a269ff6a90f95d76ddc9c230a3ce8a769977dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506552"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="32bc6-102">Anzeigen von clientversionsrichtlinien Regeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32bc6-102">View client version policy rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32bc6-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="32bc6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="32bc6-104">Eine clientversionsrichtlinie besteht aus einer Reihe von clientversionsrichtlinien Regeln.</span><span class="sxs-lookup"><span data-stu-id="32bc6-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="32bc6-105">Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="32bc6-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="32bc6-106">Sie können clientversionsrichtlinien Regeln in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="32bc6-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="32bc6-107">So zeigen Sie clientversionsrichtlinien Regeln mithilfe von lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="32bc6-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="32bc6-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="32bc6-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="32bc6-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="32bc6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="32bc6-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32bc6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="32bc6-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versionsrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="32bc6-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="32bc6-112">Doppelklicken Sie auf der Seite **clientversionsrichtlinie** auf eine clientversionsrichtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="32bc6-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="32bc6-113">Die Regeln werden auf der Seite **Client Versionsrichtlinie bearbeiten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32bc6-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="32bc6-114">Um die Details für eine Regel anzuzeigen, wählen Sie die Regel aus, und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="32bc6-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="32bc6-115">Anzeigen von Client Versionsrichtlinien Regeln mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="32bc6-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="32bc6-116">Sie können clientversionsrichtlinien Regeln anzeigen, indem Sie lync Server-Verwaltungsshell und das Cmdlet **Get-CsClientVersionPolicyRule** verwenden.</span><span class="sxs-lookup"><span data-stu-id="32bc6-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="32bc6-117">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="32bc6-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="32bc6-118">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="32bc6-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="32bc6-119">So zeigen Sie clientversionsrichtlinien Regeln an</span><span class="sxs-lookup"><span data-stu-id="32bc6-119">To view client version policy rules</span></span>

  - <span data-ttu-id="32bc6-120">Um die Regeln für die clientversionsrichtlinie anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="32bc6-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="32bc6-121">Dadurch werden für jede konfigurierte Regel ähnliche Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="32bc6-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="32bc6-122">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="32bc6-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

