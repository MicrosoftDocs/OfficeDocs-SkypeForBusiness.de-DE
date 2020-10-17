---
title: Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos
description: Testen der Konfiguration des Kerberos-Kontos, das einem Standort zugewiesen ist.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560691"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="90891-103">Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90891-103">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90891-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="90891-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90891-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="90891-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="90891-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="90891-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90891-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="90891-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="90891-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90891-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90891-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="90891-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="90891-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="90891-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="90891-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsKerberosAccountAssignment-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="90891-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="90891-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="90891-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="90891-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90891-113">Description</span></span>

<span data-ttu-id="90891-114">Mit dem Test-CsKerberosAccountAssignment-Cmdlet können Sie sicherstellen, dass einem bestimmten Standort ein Kerberos-Konto zugeordnet ist, dass dieses Konto ordnungsgemäß konfiguriert ist und dass das Konto wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="90891-114">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="90891-115">Bei Kerberos-Konten handelt es sich um Computerkonten, die als Authentifizierungs Prinzipal für alle Computer an einem Standort dienen können, auf dem Internet Information Server (IIS) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90891-115">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="90891-116">Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden die Konten als Kerberos-Konten bezeichnet, und der neue Authentifizierungsprozess wird als Kerberos-Webauthentifizierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="90891-116">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="90891-117">Auf diese Weise können Sie alle IIS-Server mithilfe eines einzigen Kontos verwalten.</span><span class="sxs-lookup"><span data-stu-id="90891-117">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="90891-118">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="90891-118">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="90891-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="90891-119">Running the Test</span></span>

<span data-ttu-id="90891-120">Standardmäßig zeigt Test-CsKerberosAccountAssignment nur sehr wenig Ausgabe auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="90891-120">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="90891-121">Stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="90891-121">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="90891-122">Aus diesem Grund wird empfohlen, dass Sie den Verbose-Parameter und den Report-Parameter immer dann einbeziehen, wenn Sie Test-CsKerberosAccountAssignment ausführen.</span><span class="sxs-lookup"><span data-stu-id="90891-122">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="90891-123">Der Verbose-Parameter stellt eine etwas detailliertere Ausgabe auf dem Bildschirm bereit, während das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90891-123">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="90891-124">Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsKerberosAccountAssignment generierte HTML-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="90891-124">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="90891-125">Wenn Sie den Parameter "Report" nicht angeben, wird die HTML-Datei automatisch im Ordner "Users" gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="90891-125">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="90891-126">Sie müssen auch eine Websiteidentität angeben, wenn Sie Test-CsKerberosAccountAssignment ausführen.</span><span class="sxs-lookup"><span data-stu-id="90891-126">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="90891-127">Kerberos-Konten werden auf Standortebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90891-127">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="90891-128">Der folgende Befehl führt Test-CsKerberosAccountAssignment aus und speichert die Ausgabe in einer Datei mit dem Namen C: \\ Logs \\KerberosTest.html:</span><span class="sxs-lookup"><span data-stu-id="90891-128">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="90891-129">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="90891-129">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="90891-130">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="90891-130">Determining Success or Failure</span></span>

<span data-ttu-id="90891-131">Das Test-CsKerberosAccountAssignment-Cmdlet gibt keinen einfachen Hinweis auf Erfolg oder Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="90891-131">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="90891-132">Stattdessen müssen Sie die generierte HTML-Datei mit Internet Explorer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="90891-132">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="90891-133">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="90891-133">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="90891-134">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsKerberosAccountAssignment Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="90891-134">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="90891-135">Möglicherweise haben Sie eine falsche Websiteidentität angegeben.</span><span class="sxs-lookup"><span data-stu-id="90891-135">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="90891-136">Verwenden Sie diesen Befehl, um eine Liste gültiger Websiteidentität zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="90891-136">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="90891-137">Eine Websiteidentität sieht normalerweise folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="90891-137">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="90891-138">Website: Redmond</span><span class="sxs-lookup"><span data-stu-id="90891-138">site:Redmond</span></span>

  - <span data-ttu-id="90891-139">Der angegebenen Website ist möglicherweise kein Kerberos-Konto zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90891-139">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="90891-140">Sie können ermitteln, ob einem Standort ein Kerberos-Konto zugewiesen ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="90891-140">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="90891-141">Ihr Kerberos-Konto verfügt möglicherweise über ein gültiges Kennwort.</span><span class="sxs-lookup"><span data-stu-id="90891-141">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="90891-142">Wenn die folgende Fehlermeldung in Report angezeigt wird, müssen Sie wahrscheinlich das Kennwort für das Kerberos-Konto zurücksetzen:</span><span class="sxs-lookup"><span data-stu-id="90891-142">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="90891-143">InvalidKerberosConfiguration: die Kerberos-Konfiguration ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="90891-143">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="90891-144">InvalidKerberosConfiguration: die Kerberos-Konfiguration auf ATL-cs001.litwareinc.com ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="90891-144">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="90891-145">Das erwartete zugewiesene Konto ist litwareinc \\ kerberostest.</span><span class="sxs-lookup"><span data-stu-id="90891-145">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="90891-146">Stellen Sie sicher, dass das Konto nicht abgelaufen ist und dass das konfigurierte Kennwort auf dem Computer mit dem Active Directory Kennwort des Kontos übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="90891-146">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="90891-147">Sie können das Kennwort mit dem Cmdlet " [CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) " festlegen.</span><span class="sxs-lookup"><span data-stu-id="90891-147">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

