---
title: Migrieren von Konferenz Verzeichnissen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae2d3b588cafb09fd2eaea821b998b546fd0211
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="eea52-102">Migrieren von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="eea52-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eea52-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="eea52-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="eea52-104">Vor dem Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Office Communications Server 2007 R2 Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="eea52-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="eea52-105">So migrieren Sie ein Konferenzverzeichnis in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eea52-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="eea52-106">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="eea52-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="eea52-107">Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu beziehen:</span><span class="sxs-lookup"><span data-stu-id="eea52-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="eea52-p101">Dieses Cmdlet gibt alle Konferenzverzeichnisse in der Organisation zurück. Deshalb empfiehlt es sich u. U., die Ergebnisse auf den Pool zu beschränken, den Sie außer Betrieb nehmen möchten. Beispiel: Sie möchten einen Pool mit dem vollqualifizierten Domänennamen (FQDN) pool01.contoso.net außer Betrieb nehmen:</span><span class="sxs-lookup"><span data-stu-id="eea52-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="eea52-110">Dieses Cmdlet gibt alle Konferenzverzeichnisse zurück, deren Dienst-ID den FQDN pool01.contoso.net enthält.</span><span class="sxs-lookup"><span data-stu-id="eea52-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="eea52-111">Führen Sie zum Verschieben von Konferenzverzeichnissen folgenden Befehl für jedes Konferenzverzeichnis in dem Pool aus:</span><span class="sxs-lookup"><span data-stu-id="eea52-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="eea52-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eea52-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="eea52-113">Möglicherweise tritt ein unten dargestellter Fehler auf, der durch die lync Server-Verwaltungsshell, die eine aktualisierte Gruppe von Berechtigungen aus Active Directory erfordern, verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="eea52-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="eea52-114">Schließen Sie zum Beheben des Fehlers das aktuelle Fenster, und öffnen Sie ein neues lync Server-Verwaltungsshell, und führen Sie den Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="eea52-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="eea52-115">![CsConferenceDirectory-Fehlerausgabe](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "CsConferenceDirectory-Fehlerausgabe")</span><span class="sxs-lookup"><span data-stu-id="eea52-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

