---
title: 'Lync Server 2013: Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="e0d32-102">Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0d32-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0d32-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e0d32-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e0d32-104">Gehen Sie wie folgt vor, um das Zertifikat in Ihren virtuellen Internet Informationsdienste (IIS)-Verzeichnissen zu konfigurieren oder zu überprüfen, ob das Zertifikat ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="e0d32-105">Führen Sie das folgende Verfahren auf jedem Server, auf dem IIS ausgeführt wird, im internen lync Server-Pool und den optionalen Director. oder Director-Pool Servern aus.</span><span class="sxs-lookup"><span data-stu-id="e0d32-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0d32-106">Das folgende Verfahren definiert eine Prozedur zum Anfordern eines kombinierten Zertifikats, das für alle Zwecke lync Server, interne Website und externe Website in IIS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0d32-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="e0d32-107">Lync Server 2010 hat einen Satz von Windows PowerShell-Cmdlets der lync Server-Verwaltungsshell&nbsp;für den ausdrücklichen Zweck der Verwaltung der Zertifikatanforderung, des Imports und der Zuweisung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0d32-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="e0d32-108">Bei diesem Verfahren wird davon ausgegangen, dass eine intern bereitgestellte Zertifizierungsstelle (Certification Authority, ca) vorhanden ist, die die Anforderung verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e0d32-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="e0d32-109">Wenn Sie öffentliche Zertifikate für Ihre lync-Server Zwecke verwenden oder für Ihre Zertifizierungsstelle eine Offlineanforderung erforderlich ist, lesen Sie die ausführliche Syntax in diesem Thema, um Informationen zum Parameter – Output zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e0d32-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="e0d32-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="e0d32-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e0d32-111">So konfigurieren Sie Authentifizierung und Zertifikate in virtuellen IIS-Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e0d32-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e0d32-112">Damit Sie die folgenden Schritte erfolgreich ausführen können, müssen Sie bei dem Computer (Front-End-Server oder Director) angemeldet sein, auf dem die Webdienste installiert sind, und ein lokaler Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="e0d32-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="e0d32-113">Sie müssen über die Berechtigungen **Lesen** und **registrieren** für die Zertifizierungsstelle verfügen, von der Sie Zertifikate anfordern werden, wenn die Zertifizierungsstelle die Zertifizierungsstelle Ihrer Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="e0d32-114">Sie benötigen keine Berechtigungen für die Zertifizierungsstelle, wenn Sie eine Offlinezertifikatanforderung konfigurieren und senden.</span><span class="sxs-lookup"><span data-stu-id="e0d32-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="e0d32-115">Klicken Sie auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.</span><span class="sxs-lookup"><span data-stu-id="e0d32-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="e0d32-116">Wählen Sie im **Internet Informationsdienste (IIS)-Manager**die Option **Servername**aus.</span><span class="sxs-lookup"><span data-stu-id="e0d32-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="e0d32-117">Wählen Sie in der **Ansicht Features**die Option **Server Zertifikate**aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Funktion öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="e0d32-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e0d32-118">Wenn dem Serverzertifikate zugewiesen sind, werden Sie in der Ansicht Serverzertifikate-Feature hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0d32-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="e0d32-119">Wenn ein Zertifikat vorhanden ist, das den Anforderungen für die externe Website in IIS entspricht, können Sie dieses Zertifikat erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0d32-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="e0d32-120">Wenn Sie ein Zertifikat anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie dann <STRONG>anzeigen</STRONG> aus.</span><span class="sxs-lookup"><span data-stu-id="e0d32-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="e0d32-121">Klicken Sie auf dem Front-End-Server oder Director, für den Sie das Zertifikat anfordern, auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Microsoft lync Server 2013**aus, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="e0d32-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="e0d32-122">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e0d32-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="e0d32-123">Die Ausgabe ist eine Liste der Zertifikate, die sich derzeit auf dem Server im persönlichen Zertifikatspeicher des Computers befinden.</span><span class="sxs-lookup"><span data-stu-id="e0d32-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="e0d32-124">Beachten Sie, dass in dem kombinierten Zertifikat (bei dem die standardmäßigen Webdienste Internal und Web Services External dasselbe Zertifikat verwenden) Sie sehen, dass die Use-Eigenschaft mit Standard, WebServicesInternal und WebServicesExternal aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="e0d32-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="e0d32-125">Darüber hinaus ist die Fingerabdruck-Eigenschaft für jeden der Verwendungstypen identisch.</span><span class="sxs-lookup"><span data-stu-id="e0d32-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="e0d32-126">In diesem Beispiel wird eine Beispielausgabe von Get-CsCertificate angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e0d32-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="e0d32-127">![Abrufen-CsCertificate Informationen zum aktuellen scert-Status] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Abrufen-CsCertificate Informationen zum aktuellen scert-Status")</span><span class="sxs-lookup"><span data-stu-id="e0d32-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="e0d32-128">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e0d32-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="e0d32-129">Wobei der vollständige Befehl wie im folgenden Beispiel aussehen würde:</span><span class="sxs-lookup"><span data-stu-id="e0d32-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e0d32-130">Standardmäßig füllt Request-CsCertificate den Namen des Antragstellers mit dem Server-oder Poolnamen auf und füllt Einträge im alternativen Subjektnamen mit dem Server-FQDN, dem FQDN des Pools, einfachen URL-FQDNs sowie den FQDNs für interne und externe Webdienste.</span><span class="sxs-lookup"><span data-stu-id="e0d32-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="e0d32-131">Dies erfolgt durch Verweisen auf das Topologie-Dokument in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e0d32-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="e0d32-132">Wenn ein fehlender Wert vorhanden ist und Sie den Parameter – verbose angegeben haben, werden Sie benachrichtigt, dass die berechneten und tatsächlichen Werte für alternative Namen unterschiedlich sind, Sie werden aber nicht informiert, welche Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="e0d32-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="e0d32-133">Sie wird mit dem gesamten berechneten Wert versorgt, auf den das Cmdlet verweist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="e0d32-134">Verwenden Sie die Zeichenfolge berechnete Alternative Namen in der Ausgabe, um ein neues Zertifikat erneut anzufordern, in dem alle Werte enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e0d32-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="e0d32-135">![Ausgabe aus CERT-Anforderung mithilfe von Request-CsCertifica] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Ausgabe aus CERT-Anforderung mithilfe von Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="e0d32-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="e0d32-136">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e0d32-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="e0d32-137">Wobei der vollständige Befehl wie im folgenden Beispiel aussehen würde:</span><span class="sxs-lookup"><span data-stu-id="e0d32-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="e0d32-138">Die Ausgabe des Cmdlets "CsCertificate" zeigt an, dass das gleiche Zertifikat (durch den Fingerabdruck des Zertifikats identifiziert) für die Verwendung von Standard, WebServicesExternal und WebServicesInternal zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="e0d32-139">![Ausgabe von "Satz-CsCertificate" auf IIS Webext] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Ausgabe von \"Satz-CsCertificate\" auf IIS Webext")</span><span class="sxs-lookup"><span data-stu-id="e0d32-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e0d32-140">So überprüfen oder konfigurieren Sie Authentifizierung und Zertifikate in virtuellen IIS-Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e0d32-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e0d32-141">Klicken Sie auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.</span><span class="sxs-lookup"><span data-stu-id="e0d32-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="e0d32-142">Erweitern Sie im **Internet Informationsdienste (IIS)-Manager** **Servername**, und erweitern Sie dann **Websites**.</span><span class="sxs-lookup"><span data-stu-id="e0d32-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="e0d32-143">Klicken Sie mit der rechten Maustaste auf **lync Server External Web Site**, und klicken Sie dann auf **Bindungen bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e0d32-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="e0d32-144">Vergewissern Sie sich, dass HTTPS Port 4443 zugeordnet ist, und klicken Sie dann auf **https**.</span><span class="sxs-lookup"><span data-stu-id="e0d32-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="e0d32-145">Wählen Sie den HTTPS-Eintrag aus, klicken Sie auf **Bearbeiten**, und stellen Sie dann sicher, dass lync Server WebServicesExternalCertificate an dieses Protokoll gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="e0d32-146">Vergleichen Sie den Fingerabdruck vom Cmdlet "CsCertificate", um sicherzustellen, dass das erwartete Zertifikat ordnungsgemäß mit der HTTPS-Bindung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e0d32-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0d32-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0d32-147">See Also</span></span>


[<span data-ttu-id="e0d32-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e0d32-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="e0d32-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e0d32-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

