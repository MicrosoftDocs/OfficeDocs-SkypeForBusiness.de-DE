---
title: 'Lync Server 2013: Überprüfen der lync Server 2013-Server Zertifikate'
description: 'Lync Server 2013: Überprüfen Sie lync Server 2013 Server Zertifikate.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543591"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="1ad07-103">Überprüfen lync Server 2013 Server Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="1ad07-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ad07-104">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="1ad07-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ad07-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="1ad07-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1ad07-106">Monatlich</span><span class="sxs-lookup"><span data-stu-id="1ad07-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ad07-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="1ad07-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1ad07-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ad07-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ad07-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1ad07-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1ad07-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="1ad07-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1ad07-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Get-CsCertificate-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="1ad07-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="1ad07-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="1ad07-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1ad07-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ad07-113">Description</span></span>

<span data-ttu-id="1ad07-114">Mit dem Get-CsCertificate-Cmdlet können Sie Informationen zu den einzelnen lync Server-Zertifikaten abrufen.</span><span class="sxs-lookup"><span data-stu-id="1ad07-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="1ad07-115">Dies ist besonders wichtig, da Zertifikate ein integriertes Ablaufdatum aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1ad07-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="1ad07-116">Beispielsweise laufen privat ausgestellte Zertifikate in der Regel nach 12 Monaten ab.</span><span class="sxs-lookup"><span data-stu-id="1ad07-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="1ad07-117">Wenn eines ihrer lync Server Zertifikate abläuft, verlieren Sie die zugehörige Funktionalität, bis das Zertifikat erneuert oder ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1ad07-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1ad07-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="1ad07-118">Running the test</span></span>

<span data-ttu-id="1ad07-119">Wenn Sie Informationen zu den einzelnen lync Server Zertifikaten zurückgeben möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1ad07-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="1ad07-120">Sie können auch die Informationen zum Rückgabe Zertifikat basierend auf dem Ablaufdatum filtern.</span><span class="sxs-lookup"><span data-stu-id="1ad07-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="1ad07-121">Beispielsweise schränkt dieser Befehl die zurückgegebenen Daten auf Zertifikate ein, die ablaufen (können nicht verwendet werden nach) Juni 1, 2014:</span><span class="sxs-lookup"><span data-stu-id="1ad07-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="1ad07-122">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="1ad07-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="1ad07-123">Beachten Sie, dass das Test-CsCertificateConfiguration-Cmdlet zwar vorhanden ist, für Administratoren jedoch nicht besonders hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="1ad07-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="1ad07-124">(Stattdessen wird das Cmdlet in erster Linie vom Zertifikat-Assistenten verwendet.) Obwohl das Cmdlet funktioniert, sind die zurückgegebenen Informationen von Minimalwert, wie im folgenden Ausgabebeispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ad07-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="1ad07-125">Verwendung des Fingerabdrucks</span><span class="sxs-lookup"><span data-stu-id="1ad07-125">Thumbprint Use</span></span>

<span data-ttu-id="1ad07-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="1ad07-126">\---------- ---</span></span>

<span data-ttu-id="1ad07-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Standard</span><span class="sxs-lookup"><span data-stu-id="1ad07-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="1ad07-128">Überprüfen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="1ad07-128">Reviewing the output</span></span>

<span data-ttu-id="1ad07-129">Das Get-CsCertificate-Cmdlet gibt für jedes Ihrer lync Server-Zertifikate Informationen zurück, die den folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="1ad07-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="1ad07-130">Aussteller: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="1ad07-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="1ad07-131">NotAfter: 12/28/2015 3:35:41 Uhr</span><span class="sxs-lookup"><span data-stu-id="1ad07-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="1ad07-132">NotBefore: 1/2/2014 12:49:37 Uhr</span><span class="sxs-lookup"><span data-stu-id="1ad07-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="1ad07-133">Seriennummer: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="1ad07-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="1ad07-134">Betreff: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="1ad07-135">AlternativeNames: {SIP.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="1ad07-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="1ad07-136">Meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="1ad07-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="1ad07-137">Fingerabdruck: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="1ad07-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="1ad07-138">Verwendung: Standard</span><span class="sxs-lookup"><span data-stu-id="1ad07-138">Use : Default</span></span>

<span data-ttu-id="1ad07-139">In der Regel beinhalten die häufigsten Probleme bei lync Server Zertifikaten Daten und Uhrzeiten, beispielsweise wenn Zertifikate wirksam werden (NotBefore) oder wenn Sie ablaufen (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="1ad07-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="1ad07-140">Da diese Datums-und Uhrzeitangaben so wichtig sind, können Sie die zurückgegebenen Daten auf Informationen wie die Verwendung des Zertifikats, die Seriennummer des Zertifikats und das Ablaufdatum des Zertifikats beschränken. Anschließend können Sie schnell alle Zertifikate überprüfen und ablaufen.</span><span class="sxs-lookup"><span data-stu-id="1ad07-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="1ad07-141">Um nur diese Informationen zurückzugeben, verwenden Sie den Befehl zusammen mit den Optionen wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1ad07-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="1ad07-142">Dieser Befehl gibt Daten ähnlich der folgenden zurück, wobei die Zertifikate in der Reihenfolgeihres Ablaufdatums sortiert sind:</span><span class="sxs-lookup"><span data-stu-id="1ad07-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="1ad07-143">Seriennummer NotAfter verwenden</span><span class="sxs-lookup"><span data-stu-id="1ad07-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="1ad07-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="1ad07-144">\--- ------------ --------</span></span>

<span data-ttu-id="1ad07-145">Standard 611BB01200000000000C 12/28/2015 3:35:41 Uhr</span><span class="sxs-lookup"><span data-stu-id="1ad07-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="1ad07-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 Uhr</span><span class="sxs-lookup"><span data-stu-id="1ad07-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="1ad07-147">"Webservicesexternal" 0451B012003872651A0C 02/20/2016 7:11:58 Uhr</span><span class="sxs-lookup"><span data-stu-id="1ad07-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="1ad07-148">Wenn Sie über Zertifikatprobleme verfügen, sollten Sie die für ein Zertifikat konfigurierten AlternativeNames möglicherweise überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1ad07-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="1ad07-149">Auf den ersten Blick scheint dies ein Problem zu sein.</span><span class="sxs-lookup"><span data-stu-id="1ad07-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="1ad07-150">In der Standardeinstellung und je nach Größe des Konsolenfensters können Get-CsCertificate möglicherweise nicht alle Namen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="1ad07-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="1ad07-151">AlternativeNames: {SIP.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="1ad07-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="1ad07-152">Meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="1ad07-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="1ad07-153">Wenn Sie alle alternativen Namen anzeigen möchten, die einem Zertifikat zugewiesen sind, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="1ad07-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="1ad07-154">Dadurch sollten alle alternativen Namen im Zertifikat angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1ad07-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="1ad07-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-155">sip.fabrikam.com</span></span>

<span data-ttu-id="1ad07-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="1ad07-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-157">meet.fabrikam.com</span></span>

<span data-ttu-id="1ad07-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-158">admin.fabrikam.com</span></span>

<span data-ttu-id="1ad07-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="1ad07-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ad07-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ad07-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ad07-161">See Also</span></span>


[<span data-ttu-id="1ad07-162">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1ad07-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

