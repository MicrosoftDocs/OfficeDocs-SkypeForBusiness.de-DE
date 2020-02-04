---
title: 'Lync Server 2013: Melden von Kerberos-Kontozuweisungen'
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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="6e48b-102">Melden von Kerberos-Kontozuweisungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e48b-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e48b-103">_**Letztes Änderungsdatum des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="6e48b-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="6e48b-104">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6e48b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="6e48b-105">Mit dem Cmdlet **Get-CsKerberosAccountAssignment** können Sie Informationen zu den Kerberos-Authentifizierungs Konto Zuweisungen Abfragen und Informationen zu den aktuellen Aufgaben in Ihrer Bereitstellung melden.</span><span class="sxs-lookup"><span data-stu-id="6e48b-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="6e48b-106">So Abfragen Sie Kerberos-Authentifizierungs Konto Zuweisungen für eine Website</span><span class="sxs-lookup"><span data-stu-id="6e48b-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="6e48b-107">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e48b-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="6e48b-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6e48b-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6e48b-109">Führen Sie in der Befehlszeile einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="6e48b-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="6e48b-110">Wenn Sie alle Kerberos-Authentifizierungs Konto Zuweisungen in Ihrer Organisation Abfragen und Zuordnungsinformationen zu den einzelnen Aufgaben zurückgeben möchten, führen Sie das Cmdlet ohne Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="6e48b-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="6e48b-111">Führen Sie das Cmdlet mit dem Parameter Identity aus, um alle Kerberos-Authentifizierungs Konto Zuweisungen in Ihrer Bereitstellung abzufragen und Websitezuordnungsinformationen zu diesen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="6e48b-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="6e48b-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e48b-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="6e48b-113">Führen Sie das Cmdlet mit dem Parameter Filter aus, um alle Kerberos-Authentifizierungs Konto Zuweisungen an einer einzigen Website abzufragen und Zuordnungsinformationen zu den einzelnen Websites zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="6e48b-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="6e48b-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e48b-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6e48b-115">Durch die Angabe von \* Sitename für den Filter-Parameter werden Informationen zu allen Websites zurückgegeben, die den angegebenen Websitenamen an einer beliebigen Stelle in der Website-ID enthalten (beispielsweise alle Websites, die die Zeichenfolge Redmond in der Website-ID enthalten).</span><span class="sxs-lookup"><span data-stu-id="6e48b-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

