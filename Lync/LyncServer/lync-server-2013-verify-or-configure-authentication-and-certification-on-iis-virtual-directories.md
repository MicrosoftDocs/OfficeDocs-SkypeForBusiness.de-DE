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

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-05-25_

Gehen Sie wie folgt vor, um das Zertifikat in Ihren virtuellen Internet Informationsdienste (IIS)-Verzeichnissen zu konfigurieren oder zu überprüfen, ob das Zertifikat ordnungsgemäß konfiguriert ist. Führen Sie das folgende Verfahren auf jedem Server, auf dem IIS ausgeführt wird, im internen lync Server-Pool und den optionalen Director. oder Director-Pool Servern aus.

<div>


> [!NOTE]  
> Das folgende Verfahren definiert eine Prozedur zum Anfordern eines kombinierten Zertifikats, das für alle Zwecke lync Server, interne Website und externe Website in IIS verwendet wird. Lync Server 2010 hat einen Satz von Windows PowerShell-Cmdlets der lync Server-Verwaltungsshell&nbsp;für den ausdrücklichen Zweck der Verwaltung der Zertifikatanforderung, des Imports und der Zuweisung eingeführt. Bei diesem Verfahren wird davon ausgegangen, dass eine intern bereitgestellte Zertifizierungsstelle (Certification Authority, ca) vorhanden ist, die die Anforderung verarbeiten kann. Wenn Sie öffentliche Zertifikate für Ihre lync-Server Zwecke verwenden oder für Ihre Zertifizierungsstelle eine Offlineanforderung erforderlich ist, lesen Sie die ausführliche Syntax in diesem Thema, um Informationen zum Parameter – Output zu erhalten. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>So konfigurieren Sie Authentifizierung und Zertifikate in virtuellen IIS-Verzeichnissen

1.  Damit Sie die folgenden Schritte erfolgreich ausführen können, müssen Sie bei dem Computer (Front-End-Server oder Director) angemeldet sein, auf dem die Webdienste installiert sind, und ein lokaler Administrator sein. Sie müssen über die Berechtigungen **Lesen** und **registrieren** für die Zertifizierungsstelle verfügen, von der Sie Zertifikate anfordern werden, wenn die Zertifizierungsstelle die Zertifizierungsstelle Ihrer Organisation ist. Sie benötigen keine Berechtigungen für die Zertifizierungsstelle, wenn Sie eine Offlinezertifikatanforderung konfigurieren und senden.

2.  Klicken Sie auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.

3.  Wählen Sie im **Internet Informationsdienste (IIS)-Manager**die Option **Servername**aus. Wählen Sie in der **Ansicht Features**die Option **Server Zertifikate**aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Funktion öffnen**aus.
    
    <div>
    

    > [!TIP]  
    > Wenn dem Serverzertifikate zugewiesen sind, werden Sie in der Ansicht Serverzertifikate-Feature hier angezeigt. Wenn ein Zertifikat vorhanden ist, das den Anforderungen für die externe Website in IIS entspricht, können Sie dieses Zertifikat erneut verwenden. Wenn Sie ein Zertifikat anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie dann <STRONG>anzeigen</STRONG> aus.

    
    </div>

4.  Klicken Sie auf dem Front-End-Server oder Director, für den Sie das Zertifikat anfordern, auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Microsoft lync Server 2013**aus, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

5.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsCertificate
    
    Die Ausgabe ist eine Liste der Zertifikate, die sich derzeit auf dem Server im persönlichen Zertifikatspeicher des Computers befinden. Beachten Sie, dass in dem kombinierten Zertifikat (bei dem die standardmäßigen Webdienste Internal und Web Services External dasselbe Zertifikat verwenden) Sie sehen, dass die Use-Eigenschaft mit Standard, WebServicesInternal und WebServicesExternal aufgefüllt wird. Darüber hinaus ist die Fingerabdruck-Eigenschaft für jeden der Verwendungstypen identisch. In diesem Beispiel wird eine Beispielausgabe von Get-CsCertificate angezeigt:
    
    ![Abrufen-CsCertificate Informationen zum aktuellen scert-Status] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Abrufen-CsCertificate Informationen zum aktuellen scert-Status")

6.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Wobei der vollständige Befehl wie im folgenden Beispiel aussehen würde:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Standardmäßig füllt Request-CsCertificate den Namen des Antragstellers mit dem Server-oder Poolnamen auf und füllt Einträge im alternativen Subjektnamen mit dem Server-FQDN, dem FQDN des Pools, einfachen URL-FQDNs sowie den FQDNs für interne und externe Webdienste. Dies erfolgt durch Verweisen auf das Topologie-Dokument in Ihrer Bereitstellung. Wenn ein fehlender Wert vorhanden ist und Sie den Parameter – verbose angegeben haben, werden Sie benachrichtigt, dass die berechneten und tatsächlichen Werte für alternative Namen unterschiedlich sind, Sie werden aber nicht informiert, welche Werte fehlen. Sie wird mit dem gesamten berechneten Wert versorgt, auf den das Cmdlet verweist. Verwenden Sie die Zeichenfolge berechnete Alternative Namen in der Ausgabe, um ein neues Zertifikat erneut anzufordern, in dem alle Werte enthalten sind.

    
    </div>
    
    ![Ausgabe aus CERT-Anforderung mithilfe von Request-CsCertifica] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Ausgabe aus CERT-Anforderung mithilfe von Request-CsCertifica")

7.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Wobei der vollständige Befehl wie im folgenden Beispiel aussehen würde:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Die Ausgabe des Cmdlets "CsCertificate" zeigt an, dass das gleiche Zertifikat (durch den Fingerabdruck des Zertifikats identifiziert) für die Verwendung von Standard, WebServicesExternal und WebServicesInternal zugewiesen ist.
    
    ![Ausgabe von "Satz-CsCertificate" auf IIS Webext] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Ausgabe von \"Satz-CsCertificate\" auf IIS Webext")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>So überprüfen oder konfigurieren Sie Authentifizierung und Zertifikate in virtuellen IIS-Verzeichnissen

1.  Klicken Sie auf **Start**, wählen Sie **Alle Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.

2.  Erweitern Sie im **Internet Informationsdienste (IIS)-Manager** **Servername**, und erweitern Sie dann **Websites**.

3.  Klicken Sie mit der rechten Maustaste auf **lync Server External Web Site**, und klicken Sie dann auf **Bindungen bearbeiten** .

4.  Vergewissern Sie sich, dass HTTPS Port 4443 zugeordnet ist, und klicken Sie dann auf **https**.

5.  Wählen Sie den HTTPS-Eintrag aus, klicken Sie auf **Bearbeiten**, und stellen Sie dann sicher, dass lync Server WebServicesExternalCertificate an dieses Protokoll gebunden ist. Vergleichen Sie den Fingerabdruck vom Cmdlet "CsCertificate", um sicherzustellen, dass das erwartete Zertifikat ordnungsgemäß mit der HTTPS-Bindung verknüpft ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

