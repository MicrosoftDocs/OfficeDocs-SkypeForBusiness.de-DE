---
title: Konfigurieren der Seite für den besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b0829037377c15f8690c36f29f8775f9e5a56c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="4d0a2-102">Konfigurieren der Seite für den besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="4d0a2-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d0a2-103">_**Letztes Änderungsstand des Themas:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="4d0a2-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="4d0a2-104">Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den besprechungsbeitritt, ob ein lync 2013 Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="4d0a2-105">Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="4d0a2-106">Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von Microsoft lync Web App geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="4d0a2-107">Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="4d0a2-108">Diese Konfigurationsoptionen wurden aus der lync Server 2013-Systemsteuerung entfernt, Sie werden jedoch mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="4d0a2-109">CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="4d0a2-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0a2-110">CsWebServiceConfiguration-Parameter</span><span class="sxs-lookup"><span data-stu-id="4d0a2-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="4d0a2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d0a2-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0a2-112">"Showjoinusinglegacyclientlink"</span><span class="sxs-lookup"><span data-stu-id="4d0a2-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="4d0a2-113">Bei Festlegung auf "true" wird Benutzern, die einer Besprechung mithilfe einer anderen Clientanwendung als lync beitreten, die Möglichkeit gegeben, an der Besprechung mit Office Communicator 2007 R2 teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="4d0a2-114">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="4d0a2-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0a2-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="4d0a2-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="4d0a2-p104">Bei Festlegung auf "True" werden automatisch alternative Optionen für die Teilnahme an einer Onlinekonferenz (z. B. Office Communicator 2007 R2) erweitert und für Benutzer angezeigt. Bei Festlegung auf "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen selbst anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="4d0a2-118">So konfigurieren Sie die Seite für den besprechungsbeitritt mithilfe lync Server 2013 Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="4d0a2-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="4d0a2-119">Starten Sie die lync Server 2013 Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4d0a2-120">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="4d0a2-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="4d0a2-121">Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.</span><span class="sxs-lookup"><span data-stu-id="4d0a2-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="4d0a2-122">Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur lync Server 2013 Verwaltungsshell):</span><span class="sxs-lookup"><span data-stu-id="4d0a2-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

