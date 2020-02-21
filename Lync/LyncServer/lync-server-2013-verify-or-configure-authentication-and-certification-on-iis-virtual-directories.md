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

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-25_

Verwenden Sie das folgende Verfahren, um das Zertifikat in Ihren Internet Information Services (IIS) virtuellen Verzeichnissen zu konfigurieren oder zu überprüfen, ob das Zertifikat ordnungsgemäß konfiguriert ist. Führen Sie das folgende Verfahren auf jedem Server aus, auf dem IIS in Ihrem internen lync Server Pool und dem optionalen Director. oder Directorpool-Server ausgeführt wird.

<div>


> [!NOTE]  
> Im folgenden Verfahren wird eine Prozedur zum Anfordern eines kombinierten Zertifikats definiert, das für alle Zwecke lync Server, der internen Website und der externen Website in IIS verwendet wird. Lync Server 2010 eine Reihe von lync Server-Verwaltungsshell&nbsp;Windows PowerShell-Cmdlets zum Zweck der Verwaltung der Zertifikatanforderung, des Imports und der Zuweisung eingeführt. Bei dem Verfahren wird angenommen, dass eine intern bereitgestellte Zertifizierungsstelle existiert, die die Anfrage verarbeiten kann. Wenn Sie öffentliche Zertifikate für Ihre lync Server Zwecke verwenden oder Ihre Zertifizierungsstelle eine Offlineanforderung erfordert, finden Sie in der ausführlichen Syntax in diesem Thema Informationen zum Parameter – Output. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>So konfigurieren Sie die Authentifizierung und Zertifikate für virtuelle IIS-Verzeichnisse

1.  Um die folgenden Schritte erfolgreich abzuschließen, müssen Sie am Computer (Front-End-Server oder Director) angemeldet sein, auf dem die Webdienste installiert sind und ein lokaler Administrator sein. Sie müssen **Lese**- und **Registrierungs**-Berechtigungen auf der Zertifizierungsstelle besitzen, von der Sie Zertifikate anfordern, wenn die Zertifizierungsstelle diejenige Ihrer Organisation ist. Sie benötigen keine Berechtigungen bei der Zertifizierungsstelle, wenn Sie eine Offline-Zertifikatanforderung konfigurieren und senden möchten.

2.  Klicken Sie auf **Start**, auf **Alle Programme** und dann auf **Verwaltung**, und klicken Sie anschließend auf **Internetinformationsdienste-Manager**.

3.  Wählen Sie im **Internetinformationsdienste-Manager** den **ServerName** und in der Ansicht**Features** die **Serverzertifikate** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Feature öffnen** aus.
    
    <div>
    

    > [!TIP]  
    > Wenn dem Server Zertifikate zugewiesen sind, werden sie in der Ansicht "Features" für Serverzertifikate angezeigt. Wenn ein Zertifikat vorhanden ist, das die Anforderungen für die externe Website in IIS erfüllt, können Sie dieses Zertifikat erneut verwenden. Um ein Zertifikat anzuzeigen, klicken Sie mit der rechten Maustaste darauf, und wählen Sie <STRONG>Anzeigen</STRONG> aus.

    
    </div>

4.  Klicken Sie auf der Front-End-Server oder dem Director, für den Sie das Zertifikat anfordern, auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Microsoft lync Server 2013**aus, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

5.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsCertificate
    
    Die Ausgabe ist eine Liste der Zertifikate, die sich derzeit auf dem Server im eigenen Zertifikatspeicher des Computers befinden. Beachten Sie, dass im kombinierten Zertifikat (d. h. wenn für den Standard sowie für interne und externe Webdienste dasselbe Zertifikat verwendet wird) die Eigenschaft "Use" mit den Werten "Default", "WebServicesInternal" und "WebServicesExternal" ausgefüllt ist. Außerdem ist die Eigenschaft "Thumbprint" bei allen Use-Typen gleich. Im Folgenden finden Sie eine Beispielausgabe von Get-CsCertificate:
    
    ![Get-CsCertificate Informationen zum aktuellen scert-Status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate Informationen zum aktuellen scert-Status")

6.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Der vollständige Befehl würde folgendermaßen aussehen:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Standardmäßig füllt "Request-CsCertificate" das Feld "Antragstellername" mit dem Server- oder Poolnamen und Einträge im Feld "Alternativer Antragstellername" mit dem Server-FQDN, dem Pool-FQDN, den FQDNs für einfache URLs sowie den FQDNs für interne und externe Webdienste aus. Dies geschieht durch einen Verweis auf das Topologiedokument in Ihrer Bereitstellung. Wenn ein Wert fehlt und Sie den –Verbose-Parameter angegeben haben, werden Sie darüber benachrichtigt, dass die berechneten und tatsächlichen Werte für alternative Namen nicht übereinstimmen, jedoch nicht darüber, welche Werte fehlen. Sie erhalten den vollständigen berechneten Wert, auf den das Cmdlet verweist. Verwenden Sie die berechnete Zeichenfolge für alternative Namen in der Ausgabe, um ein neues Zertifikat anzufordern, das alle Werte enthält.

    
    </div>
    
    ![Ausgabe von CERT-Anforderung mithilfe von Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Ausgabe von CERT-Anforderung mithilfe von Request-CsCertifica")

7.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Der vollständige Befehl würde folgendermaßen aussehen:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Die Ausgabe vom Set-CsCertificate-Cmdlet zeigt an, dass dasselbe Zertifikat (identifiziert durch seinen Fingerabdruck) für die Verwendung mit Default, WebServicesExternal und WebServicesInternal zugewiesen ist.
    
    ![Ausgabe von "CsCertificate" in IIS Webext](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Ausgabe von "CsCertificate" in IIS Webext")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>So überprüfen oder konfigurieren Sie die Authentifizierung und die Zertifikate für virtuelle IIS-Verzeichnisse

1.  Klicken Sie auf **Start**, auf **Alle Programme** und dann auf **Verwaltung**, und klicken Sie auf **Internetinformationsdienste-Manager**.

2.  Erweitern Sie in **Internet Information Services (IIS)-Manager**den Knoten **Servername**, und erweitern Sie dann **Websites**.

3.  Klicken Sie mit der rechten Maustaste auf **Externe Lync Server-Website** und anschließend auf **Bindungen bearbeiten**.

4.  Stellen Sie sicher, dass HTTPS Port 4443 zugeordnet ist, und klicken Sie dann auf **HTTPS**.

5.  Wählen Sie den Eintrag HTTPS aus, klicken Sie auf **Bearbeiten**, und vergewissern Sie sich, dass lync Server WebServicesExternalCertificate an dieses Protokoll gebunden ist. Vergleichen Sie den Fingerabdruck des Set-CsCertificate-Cmdlets, um sicherzustellen, dass das erwartete Zertifikat der HTTPS Bindung richtig zugewiesen ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Gruppe-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

