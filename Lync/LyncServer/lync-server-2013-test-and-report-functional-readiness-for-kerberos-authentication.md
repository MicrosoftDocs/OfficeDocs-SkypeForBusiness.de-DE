---
title: Testen der Funktionsfähigkeit der Kerberos-Authentifizierung und Erstellen eines Berichts
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="14517-102">Testen der Funktionsfähigkeit der Kerberos-Authentifizierung und Erstellen eines Berichts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14517-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14517-103">_**Letztes Änderungsdatum des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="14517-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="14517-104">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="14517-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="14517-105">Sie können das Windows PowerShell **-Cmdlet Test-CsKerberosAccountAssignment** verwenden, um die Funktionsbereitschaft einer Website Aufgabe für die Kerberos-Authentifizierung zu testen und zu melden.</span><span class="sxs-lookup"><span data-stu-id="14517-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="14517-106">Dieser Befehl fragt die im erforderlichen Identity-Parameter angegebene Website ab.</span><span class="sxs-lookup"><span data-stu-id="14517-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="14517-107">Der optionale Berichtsparameter bewirkt, dass das Cmdlet einen HTML-Bericht in C\\:-Protokolle auf dem Computer schreibt, auf dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14517-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="14517-108">Der optionale Verbose-Parameter meldet Aktivitätsinformationen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="14517-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="14517-109">So testen und melden Sie die Funktionsbereitschaft für die Kerberos-Authentifizierung für eine Website</span><span class="sxs-lookup"><span data-stu-id="14517-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="14517-110">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf dem Computer an, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="14517-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="14517-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="14517-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="14517-112">Führen Sie in der Befehlszeile den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="14517-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="14517-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="14517-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

