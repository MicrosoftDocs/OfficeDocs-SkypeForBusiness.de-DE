---
title: Testen und melden der Funktionsbereitschaft für die Kerberos-Authentifizierung
description: Testen und melden Sie die Funktionsbereitschaft für die Kerberos-Authentifizierung.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d32591a8cced7dce2e0bb78cc26189dce1900a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554061"
---
# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="caa6b-103">Testen und melden der Funktionsbereitschaft für die Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="caa6b-103">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caa6b-104">_**Letztes Änderungsstand des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="caa6b-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="caa6b-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="caa6b-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="caa6b-106">Sie können das Cmdlet **Test-CsKerberosAccountAssignment**   Windows PowerShell verwenden, um die Funktionsbereitschaft einer Standortzuweisung für die Kerberos-Authentifizierung zu testen und zu melden.</span><span class="sxs-lookup"><span data-stu-id="caa6b-106">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="caa6b-107">Dieser Befehl fragt den im erforderlichen Parameter "Identity" angegebenen Standort ab.</span><span class="sxs-lookup"><span data-stu-id="caa6b-107">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="caa6b-108">Der optionale Berichtsparameter bewirkt, dass das Cmdlet einen HTML-Bericht in C: \\ Logs auf dem Computer schreibt, auf dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="caa6b-108">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="caa6b-109">Bei Verwendung des optionalen Parameters "Verbose" werden auf dem Bildschirm ausführliche Informationen zur Aktivität ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="caa6b-109">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="caa6b-110">So testen Sie die Funktionsfähigkeit der Kerberos-Authentifizierung an einem Standort und erstellen einen Bericht</span><span class="sxs-lookup"><span data-stu-id="caa6b-110">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="caa6b-111">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an dem Computer mit den Verwaltungstools installiert ist.</span><span class="sxs-lookup"><span data-stu-id="caa6b-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="caa6b-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="caa6b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="caa6b-113">Führen Sie den folgenden Befehl über die Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="caa6b-113">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="caa6b-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="caa6b-114">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

