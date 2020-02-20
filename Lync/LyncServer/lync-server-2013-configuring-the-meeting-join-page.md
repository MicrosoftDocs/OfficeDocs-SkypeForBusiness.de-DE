---
title: 'Lync Server 2013: Konfigurieren der Seite für den besprechungsbeitritt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 977903d8d85b3eaa4d944e8b3e62ec0df629c1d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="a8d4e-102">Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8d4e-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d4e-103">_**Letztes Änderungsstand des Themas:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="a8d4e-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="a8d4e-104">Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den besprechungsbeitritt, ob ein lync 2013 Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="a8d4e-105">Wenn bereits ein Client installiert ist, wird dieser geöffnet und tritt der Besprechung bei.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="a8d4e-106">Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von lync Web App geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="a8d4e-107">Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="a8d4e-108">Diese Konfigurationsoptionen wurden aus der lync Server 2013-Systemsteuerung entfernt, Sie können Sie jedoch mithilfe des Cmdlets "Cmdlet festlegen-CsWebServiceConfiguration" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="a8d4e-109">Set-CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="a8d4e-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8d4e-110">Set-CsWebServiceConfiguration-Parameter</span><span class="sxs-lookup"><span data-stu-id="a8d4e-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="a8d4e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8d4e-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8d4e-112">"Showjoinusinglegacyclientlink"</span><span class="sxs-lookup"><span data-stu-id="a8d4e-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="a8d4e-113">Bei Festlegung auf "true" wird Benutzern, die einer Besprechung mithilfe einer anderen Clientanwendung als lync beitreten, die Möglichkeit gegeben, an der Besprechung mit Office Communicator 2007 R2 teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="a8d4e-114">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="a8d4e-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8d4e-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="a8d4e-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="a8d4e-p104">Bei Festlegung auf "True" werden automatisch alternative Optionen für die Teilnahme an einer Onlinekonferenz (z. B. Office Communicator 2007 R2) erweitert und für Benutzer angezeigt. Bei Festlegung auf "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen selbst anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="a8d4e-118">So konfigurieren Sie die Seite für den besprechungsbeitritt mithilfe lync Server 2013 Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="a8d4e-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="a8d4e-119">Starten Sie die lync Server 2013 Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a8d4e-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a8d4e-120">Führen Sie das folgende Cmdlet aus, um die Konfigurationseinstellungen des Webdiensts anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="a8d4e-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="a8d4e-121">Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie unter " [CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) " in der Dokumentation zu lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="a8d4e-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8d4e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8d4e-122">See Also</span></span>


[<span data-ttu-id="a8d4e-123">Gruppe-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8d4e-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

