---
title: 'Lync Server 2013: Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca51a3c597be40c679a7b131f87775876a63811d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="f149a-102">Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f149a-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f149a-103">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f149a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f149a-104">Verwenden Sie das folgende Verfahren, um das Zertifikat in Ihren Internet Information Services (IIS) virtuellen Verzeichnissen zu konfigurieren oder zu überprüfen, ob das Zertifikat ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f149a-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="f149a-105">Führen Sie das folgende Verfahren auf jedem Server aus, auf dem IIS in Ihrem internen lync Server Pool und dem optionalen Director. oder Directorpool-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f149a-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f149a-106">Im folgenden Verfahren wird eine Prozedur zum Anfordern eines kombinierten Zertifikats definiert, das für alle Zwecke lync Server, der internen Website und der externen Website in IIS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f149a-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="f149a-107">Lync Server 2010 eine Reihe von lync Server-Verwaltungsshell&nbsp;Windows PowerShell-Cmdlets zum Zweck der Verwaltung der Zertifikatanforderung, des Imports und der Zuweisung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f149a-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="f149a-108">Bei dem Verfahren wird angenommen, dass eine intern bereitgestellte Zertifizierungsstelle existiert, die die Anfrage verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f149a-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="f149a-109">Wenn Sie öffentliche Zertifikate für Ihre lync Server Zwecke verwenden oder Ihre Zertifizierungsstelle eine Offlineanforderung erfordert, finden Sie in der ausführlichen Syntax in diesem Thema Informationen zum Parameter – Output.</span><span class="sxs-lookup"><span data-stu-id="f149a-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="f149a-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="f149a-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="f149a-111">So konfigurieren Sie die Authentifizierung und Zertifikate für virtuelle IIS-Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="f149a-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="f149a-112">Um die folgenden Schritte erfolgreich abzuschließen, müssen Sie am Computer (Front-End-Server oder Director) angemeldet sein, auf dem die Webdienste installiert sind und ein lokaler Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="f149a-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="f149a-113">Sie müssen **Lese**- und **Registrierungs**-Berechtigungen auf der Zertifizierungsstelle besitzen, von der Sie Zertifikate anfordern, wenn die Zertifizierungsstelle diejenige Ihrer Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="f149a-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="f149a-114">Sie benötigen keine Berechtigungen bei der Zertifizierungsstelle, wenn Sie eine Offline-Zertifikatanforderung konfigurieren und senden möchten.</span><span class="sxs-lookup"><span data-stu-id="f149a-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="f149a-115">Klicken Sie auf **Start**, auf **Alle Programme** und dann auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**.</span><span class="sxs-lookup"><span data-stu-id="f149a-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="f149a-p104">Wählen Sie im **Internetinformationsdienste-Manager** den **ServerName** und in der Ansicht**Features** die **Serverzertifikate** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Feature öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="f149a-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f149a-p105">Wenn dem Server Zertifikate zugewiesen sind, werden sie in der Ansicht "Features" für Serverzertifikate angezeigt. Wenn ein Zertifikat vorhanden ist, das die Anforderungen für die externe Website in IIS erfüllt, können Sie dieses Zertifikat erneut verwenden. Um ein Zertifikat anzuzeigen, klicken Sie mit der rechten Maustaste darauf, und wählen Sie <STRONG>Anzeigen</STRONG> aus.</span><span class="sxs-lookup"><span data-stu-id="f149a-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="f149a-121">Klicken Sie auf der Front-End-Server oder dem Director, für den Sie das Zertifikat anfordern, auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Microsoft lync Server 2013**aus, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f149a-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="f149a-122">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f149a-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="f149a-p106">Die Ausgabe ist eine Liste der Zertifikate, die sich derzeit auf dem Server im eigenen Zertifikatspeicher des Computers befinden. Beachten Sie, dass im kombinierten Zertifikat (d. h. wenn für den Standard sowie für interne und externe Webdienste dasselbe Zertifikat verwendet wird) die Eigenschaft "Use" mit den Werten "Default", "WebServicesInternal" und "WebServicesExternal" ausgefüllt ist. Außerdem ist die Eigenschaft "Thumbprint" bei allen Use-Typen gleich. Im Folgenden finden Sie eine Beispielausgabe von Get-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="f149a-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="f149a-127">![Get-CsCertificate Informationen zum aktuellen scert-Status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate Informationen zum aktuellen scert-Status")</span><span class="sxs-lookup"><span data-stu-id="f149a-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="f149a-128">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f149a-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="f149a-129">Der vollständige Befehl würde folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="f149a-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f149a-p107">Standardmäßig füllt "Request-CsCertificate" das Feld "Antragstellername" mit dem Server- oder Poolnamen und Einträge im Feld "Alternativer Antragstellername" mit dem Server-FQDN, dem Pool-FQDN, den FQDNs für einfache URLs sowie den FQDNs für interne und externe Webdienste aus. Dies geschieht durch einen Verweis auf das Topologiedokument in Ihrer Bereitstellung. Wenn ein Wert fehlt und Sie den –Verbose-Parameter angegeben haben, werden Sie darüber benachrichtigt, dass die berechneten und tatsächlichen Werte für alternative Namen nicht übereinstimmen, jedoch nicht darüber, welche Werte fehlen. Sie erhalten den vollständigen berechneten Wert, auf den das Cmdlet verweist. Verwenden Sie die berechnete Zeichenfolge für alternative Namen in der Ausgabe, um ein neues Zertifikat anzufordern, das alle Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="f149a-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="f149a-135">![Ausgabe von CERT-Anforderung mithilfe von Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Ausgabe von CERT-Anforderung mithilfe von Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="f149a-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="f149a-136">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f149a-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="f149a-137">Der vollständige Befehl würde folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="f149a-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="f149a-138">Die Ausgabe vom Set-CsCertificate-Cmdlet zeigt an, dass dasselbe Zertifikat (identifiziert durch seinen Fingerabdruck) für die Verwendung mit Default, WebServicesExternal und WebServicesInternal zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f149a-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="f149a-139">![Ausgabe von "CsCertificate" in IIS Webext](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Ausgabe von "CsCertificate" in IIS Webext")</span><span class="sxs-lookup"><span data-stu-id="f149a-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="f149a-140">So überprüfen oder konfigurieren Sie die Authentifizierung und die Zertifikate für virtuelle IIS-Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="f149a-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="f149a-141">Klicken Sie auf **Start**, auf **Alle Programme** und dann auf **Verwaltung**, und klicken Sie auf **Internetinformationsdienste-Manager**.</span><span class="sxs-lookup"><span data-stu-id="f149a-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="f149a-142">Erweitern Sie in **Internet Information Services (IIS)-Manager**den Knoten **Servername**, und erweitern Sie dann **Websites**.</span><span class="sxs-lookup"><span data-stu-id="f149a-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="f149a-143">Klicken Sie mit der rechten Maustaste auf **Externe Lync Server-Website** und anschließend auf **Bindungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f149a-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="f149a-144">Stellen Sie sicher, dass HTTPS Port 4443 zugeordnet ist, und klicken Sie dann auf **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="f149a-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="f149a-145">Wählen Sie den Eintrag HTTPS aus, klicken Sie auf **Bearbeiten**, und vergewissern Sie sich, dass lync Server WebServicesExternalCertificate an dieses Protokoll gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="f149a-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="f149a-146">Vergleichen Sie den Fingerabdruck des Set-CsCertificate-Cmdlets, um sicherzustellen, dass das erwartete Zertifikat der HTTPS Bindung richtig zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f149a-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f149a-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f149a-147">See Also</span></span>


[<span data-ttu-id="f149a-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="f149a-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="f149a-149">Gruppe-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="f149a-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

