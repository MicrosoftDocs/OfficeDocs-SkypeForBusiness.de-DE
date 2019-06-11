---
title: 'Lync Server 2013: Überprüfen der lync Server 2013-Serverzertifikate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="065c6-102">Überprüfen der lync Server 2013-Serverzertifikate</span><span class="sxs-lookup"><span data-stu-id="065c6-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="065c6-103">_**Letztes Änderungsdatum des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="065c6-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="065c6-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="065c6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="065c6-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="065c6-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="065c6-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="065c6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="065c6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="065c6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="065c6-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="065c6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="065c6-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="065c6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="065c6-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Get-CsCertificate verfügt.</span><span class="sxs-lookup"><span data-stu-id="065c6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="065c6-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="065c6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="065c6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="065c6-112">Description</span></span>

<span data-ttu-id="065c6-113">Mit dem Cmdlet Get-CsCertificate können Sie Informationen zu jedem ihrer lync Server-Zertifikate abrufen.</span><span class="sxs-lookup"><span data-stu-id="065c6-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="065c6-114">Dies ist besonders wichtig, da Zertifikate ein integriertes Ablaufdatum aufweisen.</span><span class="sxs-lookup"><span data-stu-id="065c6-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="065c6-115">So verfallen in der Regel privat ausgestellte Zertifikate nach 12 Monaten.</span><span class="sxs-lookup"><span data-stu-id="065c6-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="065c6-116">Wenn eines ihrer lync Server-Zertifikate abläuft, gehen die zugehörigen Funktionen verloren, bis das Zertifikat erneuert oder ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="065c6-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="065c6-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="065c6-117">Running the test</span></span>

<span data-ttu-id="065c6-118">Wenn Sie Informationen zu den einzelnen lync Server-Zertifikaten zurückgeben möchten, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="065c6-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="065c6-119">Alternativ können Sie die Rückgabe Zertifikatinformationen auf Grundlage des Ablaufdatums filtern.</span><span class="sxs-lookup"><span data-stu-id="065c6-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="065c6-120">Mit diesem Befehl werden beispielsweise die zurückgegebenen Daten auf Zertifikate begrenzt, die ablaufen (können nach) 1. Juni 2014 nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="065c6-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="065c6-121">Weitere Informationen finden Sie in der Hilfedokumentation für das Cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="065c6-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="065c6-122">Beachten Sie, dass das Cmdlet Test-CsCertificateConfiguration zwar vorhanden ist, aber für Administratoren nicht sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="065c6-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="065c6-123">(Stattdessen wird dieses Cmdlet in erster Linie vom Zertifikat-Assistenten verwendet.) Obwohl das Cmdlet funktioniert, sind die zurückgegebenen Informationen von minimalem Wert, wie im folgenden Ausgabebeispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="065c6-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="065c6-124">Fingerabdruck Verwendung</span><span class="sxs-lookup"><span data-stu-id="065c6-124">Thumbprint Use</span></span>

<span data-ttu-id="065c6-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="065c6-125"></span></span>

<span data-ttu-id="065c6-126">A9D51A2911C74FABFF7F2A8A994B20857D399107-Standard</span><span class="sxs-lookup"><span data-stu-id="065c6-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="065c6-127">Überprüfen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="065c6-127">Reviewing the output</span></span>

<span data-ttu-id="065c6-128">Das Cmdlet "Get-CsCertificate" gibt für jedes Ihrer lync Server-Zertifikate Informationen ähnlich der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="065c6-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="065c6-129">Emittent: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="065c6-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="065c6-130">NotAfter: 12/28/2015 3:35:41 Uhr</span><span class="sxs-lookup"><span data-stu-id="065c6-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="065c6-131">NotBefore: 1/2/2014 12:49:37 pm</span><span class="sxs-lookup"><span data-stu-id="065c6-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="065c6-132">Seriennummer: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="065c6-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="065c6-133">Betreff: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="065c6-134">AlternativeNames: {SIP.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="065c6-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="065c6-135">Meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="065c6-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="065c6-136">Daumenabdruck: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="065c6-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="065c6-137">Verwendung: Standard</span><span class="sxs-lookup"><span data-stu-id="065c6-137">Use : Default</span></span>

<span data-ttu-id="065c6-138">In der Regel beziehen sich die wichtigsten Probleme im Zusammenhang mit lync Server-Zertifikaten auf Datums-und Uhrzeitangaben, beispielsweise wenn Zertifikate wirksam werden (NotBefore) oder wenn Sie ablaufen (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="065c6-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="065c6-139">Da diese Datums-und Uhrzeitangaben so wichtig sind, möchten Sie möglicherweise die zurückgegebenen Daten auf Informationen wie die Zertifikatverwendung, die Seriennummer des Zertifikats und das Ablaufdatum des Zertifikats einschränken. Anschließend können Sie alle Zertifikate schnell überprüfen und ablaufen.</span><span class="sxs-lookup"><span data-stu-id="065c6-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="065c6-140">Wenn Sie nur diese Informationen zurückgeben möchten, verwenden Sie den Befehl zusammen mit den folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="065c6-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="065c6-141">Dieser Befehl gibt Daten ähnlich der folgenden zurück, wobei die Zertifikate in der Reihenfolgeihres Ablaufdatums sortiert sind:</span><span class="sxs-lookup"><span data-stu-id="065c6-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="065c6-142">Verwenden von Seriennummer NotAfter</span><span class="sxs-lookup"><span data-stu-id="065c6-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="065c6-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="065c6-143"></span></span>

<span data-ttu-id="065c6-144">Standard 611BB01200000000000C 12/28/2015 3:35:41 pm</span><span class="sxs-lookup"><span data-stu-id="065c6-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="065c6-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 pm</span><span class="sxs-lookup"><span data-stu-id="065c6-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="065c6-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 Uhr</span><span class="sxs-lookup"><span data-stu-id="065c6-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="065c6-147">Wenn Sie Probleme mit dem Zertifikat haben, empfiehlt es sich, die für ein Zertifikat konfigurierte AlternativeNames zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="065c6-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="065c6-148">Auf den ersten Blick scheint das ein Problem zu sein.</span><span class="sxs-lookup"><span data-stu-id="065c6-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="065c6-149">In Abhängigkeit von der Größe des Konsolenfensters können von Get-CsCertificate möglicherweise nicht alle Namen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="065c6-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="065c6-150">AlternativeNames: {SIP.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="065c6-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="065c6-151">Meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="065c6-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="065c6-152">Wenn Sie alle alternativen Namen anzeigen möchten, die einem Zertifikat zugewiesen sind, verwenden Sie einen Befehl ähnlich dem folgenden:</span><span class="sxs-lookup"><span data-stu-id="065c6-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="065c6-153">Damit sollten alle alternativen Namen auf dem Zertifikat angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="065c6-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="065c6-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-154">sip.fabrikam.com</span></span>

<span data-ttu-id="065c6-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="065c6-156">Meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-156">meet.fabrikam.com</span></span>

<span data-ttu-id="065c6-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-157">admin.fabrikam.com</span></span>

<span data-ttu-id="065c6-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="065c6-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="065c6-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="065c6-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="065c6-160">See Also</span></span>


[<span data-ttu-id="065c6-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="065c6-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

