---
title: 'Lync Server 2013: Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse'
TOCTitle: Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429702(v=OCS.15)
ms:contentKeyID: 49293750
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-05-25_

Führen Sie das folgende Verfahren aus, um das Zertifikat Ihrer virtuellen Internetinformationsdienste (Internet Information Services, IIS)-Verzeichnisse zu konfigurieren oder um die ordnungsgemäße Konfiguration der Zertifizierung zu überprüfen. Führen Sie das folgende Verfahren auf jedem Server mit IIS in Ihrem internen Lync Server-Pool sowie auf den optionalen Director- oder Directorpool-Servern aus.


> [!NOTE]
> Mit dem folgenden Verfahren wird eine Anfrage eines kombinierten Zertifikats definiert, das für alle Zwecke von Lync Server, interne Websites und externe Websites in IIS verwendet wird. Mit Lync Server 2010 wurde ein Satz von Lync Server-Verwaltungsshell- Windows PowerShell-Cmdlets für den Ausdruckszweck der Verwaltung von Zertifikatanforderung, -import und -zuweisung eingeführt. Bei dem Verfahren wird angenommen, dass eine intern bereitgestellte Zertifizierungsstelle existiert, die die Anfrage verarbeiten kann. Wenn Sie öffentliche Zertifikate für Ihre Lync Server-Zwecke verwenden oder Ihre Zertifizierungsstelle eine Offline-Anfrage erfordert, finden Sie in der detaillierten Syntax in diesem Thema Informationen zum -Output -Parameter. <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



## So konfigurieren Sie die Authentifizierung und Zertifikate für virtuelle IIS-Verzeichnisse

1.  Um Folgendes erfolgreich abschließen zu können, müssen Sie auf dem Computer angemeldet sein, auf dem die Webdienste installiert sind, und lokaler Administrator sein ( Front-End-Server oder Director). Sie müssen **Lese** - und **Registrierungs** -Berechtigungen auf der Zertifizierungsstelle besitzen, von der Sie Zertifikate anfordern, wenn die Zertifizierungsstelle diejenige Ihrer Organisation ist. Sie benötigen keine Berechtigungen bei der Zertifizierungsstelle, wenn Sie eine Offline-Zertifikatanforderung konfigurieren und senden möchten.

2.  Klicken Sie auf **Start** , auf **Alle Programme** und dann auf **Verwaltung** , und klicken Sie auf **Internetinformationsdienste-Manager** .

3.  Wählen Sie im **Internetinformationsdienste-Manager** den **ServerName** und in der Ansicht **Features** die **Serverzertifikate** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Feature öffnen** aus.
    

    > [!TIP]
    > Wenn dem Server Zertifikate zugewiesen sind, werden sie in der Ansicht "Features" für Serverzertifikate angezeigt. Wenn ein Zertifikat vorhanden ist, das die Anforderungen für die externe Website in IIS erfüllt, können Sie dieses Zertifikat erneut verwenden. Um ein Zertifikat anzuzeigen, klicken Sie mit der rechten Maustaste darauf, und wählen Sie <STRONG>Anzeigen</STRONG> aus.



4.  Klicken Sie auf dem Front-End-Server oder dem Director, für den Sie das Zertifikat anfordern, auf **Start** , **Alle Programme** , wählen Sie **Microsoft Lync Server 2013** aus, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

5.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsCertificate
    
    Die Ausgabe ist eine Liste der Zertifikate, die sich derzeit auf dem Server im eigenen Zertifikatspeicher des Computers befinden. Beachten Sie, dass im kombinierten Zertifikat (d. h. wenn für den Standard sowie für interne und externe Webdienste dasselbe Zertifikat verwendet wird) die Eigenschaft "Use" mit den Werten "Default", "WebServicesInternal" und "WebServicesExternal" ausgefüllt ist. Außerdem ist die Eigenschaft "Thumbprint" bei allen Use-Typen gleich. Im Folgenden finden Sie eine Beispielausgabe von Get-CsCertificate:
    
    ![Get-CsCertificate-Informationen zum aktuellen scert-Status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate-Informationen zum aktuellen scert-Status")

6.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Der vollständige Befehl würde folgendermaßen aussehen:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    

    > [!TIP]
    > Standardmäßig füllt "Request-CsCertificate" das Feld "Antragstellername" mit dem Server- oder Poolnamen und Einträge im Feld "Alternativer Antragstellername" mit dem Server-FQDN, dem Pool-FQDN, den FQDNs für einfache URLs sowie den FQDNs für interne und externe Webdienste aus. Dies geschieht durch einen Verweis auf das Topologiedokument in Ihrer Bereitstellung. Wenn ein Wert fehlt und Sie den -Verbose-Parameter angegeben haben, werden Sie darüber benachrichtigt, dass die berechneten und tatsächlichen Werte für alternative Namen nicht übereinstimmen, jedoch nicht darüber, welche Werte fehlen. Sie erhalten den vollständigen berechneten Wert, auf den das Cmdlet verweist. Verwenden Sie die berechnete Zeichenfolge für alternative Namen in der Ausgabe, um ein neues Zertifikat anzufordern, das alle Werte enthält.

    
    ![Ausgabe der cert-Anforderung mit „Request-CsCertificate“](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Ausgabe der cert-Anforderung mit „Request-CsCertificate“")

7.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Der vollständige Befehl würde folgendermaßen aussehen:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Die Ausgabe vom Set-CsCertificate-Cmdlet zeigt an, dass dasselbe Zertifikat (identifiziert durch seinen Fingerabdruck) für die Verwendung mit Default, WebServicesExternal und WebServicesInternal zugewiesen ist.
    
    ![Ausgabe von „Set-CsCertificate“ für IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Ausgabe von „Set-CsCertificate“ für IIS WebExt")

## So überprüfen oder konfigurieren Sie die Authentifizierung und die Zertifikate für virtuelle IIS-Verzeichnisse

1.  Klicken Sie auf **Start** , auf **Alle Programme** und dann auf **Verwaltung** , und klicken Sie auf **Internetinformationsdienste-Manager** .

2.  Erweitern Sie im **Internetinformationsdienste-Manager** den Servernamen und anschließend **Websites** .

3.  Klicken Sie mit der rechten Maustaste auf **Externe Lync Server-Website** und anschließend auf **Bindungen bearbeiten** .

4.  Stellen Sie sicher, dass HTTPS Port 4443 zugeordnet ist, und klicken Sie dann auf **HTTPS** .

5.  Wählen Sie den HTTPS-Eintrag aus, klicken Sie auf **Bearbeiten** , und vergewissern Sie sich, dass Lync Server WebServicesExternalCertificate an dieses Protokoll gebunden ist. Vergleichen Sie den Fingerabdruck des Set-CsCertificate-Cmdlets, um sicherzustellen, dass das erwartete Zertifikat der HTTPS Bindung richtig zugewiesen ist.

## Siehe auch

#### Weitere Ressourcen

[Get-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

