---
title: 'Lync Server 2013: Melden von Kerberos-Konto Zuweisungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c742e6e7e5cedc773e0275700a738afd26a6777d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="37472-102">Melden von Kerberos-Konto Zuweisungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37472-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37472-103">_**Letztes Änderungsstand des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="37472-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="37472-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="37472-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="37472-105">Mit dem Cmdlet **Get-CsKerberosAccountAssignment** können Sie Informationen zu Kontozuweisungen für die Kerberos-Authentifizierung sowie Berichtinformationen zu den aktuellen Zuweisungen in Ihrer Bereitstellung abrufen.</span><span class="sxs-lookup"><span data-stu-id="37472-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="37472-106">So rufen Sie Kontozuweisungen für die Kerberos-Authentifizierung für einen Standort ab</span><span class="sxs-lookup"><span data-stu-id="37472-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="37472-107">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an einem Computer mit den Verwaltungstools installiert ist.</span><span class="sxs-lookup"><span data-stu-id="37472-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="37472-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="37472-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="37472-109">Führen Sie an der Befehlszeile einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="37472-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="37472-110">Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Organisation und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet ohne Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="37472-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="37472-111">Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Bereitstellung und Zurückgeben von Standortzuweisungsinformationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Identitätsparameter aus:</span><span class="sxs-lookup"><span data-stu-id="37472-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="37472-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37472-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="37472-113">Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung an einem einzelnen Standort und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Filterparameter aus:</span><span class="sxs-lookup"><span data-stu-id="37472-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="37472-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37472-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="37472-115">Bei Angabe von "\*SiteName" als Filterparameter werden Informationen zu sämtlichen Standorten zurückgegeben, deren Standort-ID den angegebenen Standortnamen enthält (z. B. alle Standorte mit der Zeichenfolge "Redmond" in der Standort-ID).</span><span class="sxs-lookup"><span data-stu-id="37472-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

