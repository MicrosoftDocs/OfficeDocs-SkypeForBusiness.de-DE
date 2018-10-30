---
title: Konfigurieren von Zertifikaten für die AutoErmittlung
TOCTitle: Konfigurieren von Zertifikaten für die AutoErmittlung
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945617(v=OCS.15)
ms:contentKeyID: 52056293
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Zertifikaten für die AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2012-12-12_

Die Zertifikate für Ihren Directorpool, Front-End-Pool und Reverseproxy erfordern zusätzliche Einträge von alternativen Antragstellernamen, um sichere Verbindungen mit Lync-Clients zu unterstützen.


> [!NOTE]
> Mit dem Cmdlet <STRONG>Get-CsCertificate</STRONG> können Sie Informationen über die derzeit zugewiesenen Zertifikate anzeigen. In der Standardansicht werden die Eigenschaften des Zertifikats jedoch abgeschnitten, und die Werte in der Eigenschaft "SubjectAlternativeNames" werden nicht vollständig angezeigt. Mit den Cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate und <STRONG>Set-CsCertificate</STRONG> können Sie einige Informationen anzeigen und Zertifikate anfordern sowie zuweisen. Wenn Sie sich bezüglich der Eigenschaften der alternativen Antragstellernamen im aktuellen Zertifikat unsicher sind, ist dies jedoch nicht unbedingt die am besten geeignete Methode. Um das Zertifikat sowie alle Eigenschaftenmember anzuzeigen, wird daher empfohlen, das Zertifikat-Snap-In in der <EM>Microsoft Management Console (MMC)</EM> oder Lync Server-Bereitstellungs-Assistent zu verwenden. Im Lync Server-Bereitstellungs-Assistent können Sie die Zertifikateigenschaften mit dem Zertifikat-Assistenten anzeigen. Die Vorgehensweise zum Anzeigen, Anfordern und Zuweisen eines Zertifikats mit der Lync Server-Verwaltungsshell und mit der <EM>Microsoft Management Console (MMC)</EM> werden in den folgenden Verfahren veranschaulicht. Nähere Informationen zur Verwendung des Lync Server-Bereitstellungs-Assistent bei Bereitstellung des optionalen Director oder des optionalen Directorpool finden Sie hier: <A href="lync-server-2013-configure-certificates-for-the-director.md">Konfigurieren von Zertifikaten für den Director in Lync Server 2013</A>. Nähere Informationen zum Front-End-Server oder zum Front-End-Pool finden Sie hier: <A href="lync-server-2013-configure-certificates-for-servers.md">Konfigurieren von Zertifikaten für Server in Lync Server 2013</A>.<BR>Die ersten Schritte in diesem Verfahren dienen der Vorbereitung, und Sie werden in die Verwendung der aktuellen Zertifikate eingeführt. Die Zertifikate verfügen standardmäßig nicht über einen Eintrag für "lyncdiscover.&lt;sipdomain&gt;" oder "lyncdiscoverinternal.&lt;internal domain name&gt;". Dies ist nur der Fall, wenn die Mobilitätsdienste bereits installiert oder die Zertifikate entsprechend vorbereitet wurden. In diesem Verfahren wird der Beispielname "contoso.com" für die SIP-Domäne verwendet. Zudem wird der Beispielname "contoso.net" für die interne Domäne verwendet.<BR>In der Standardzertifikatkonfiguration für Lync Server 2013 und Lync Server 2010 wird ein einzelnes Zertifikat (mit dem Namen "Standard") für die Zwecke "Default" (alle Zwecke außer Webdienste), "WebServicesExternal" und "WebServicesInternal" verwendet. Optional können Sie ein separates Zertifikat für jeden Zweck verwenden. Die Zertifikate können mit dem Cmdlet Lync Server-Verwaltungsshell und mit dem Cmdlet Windows PowerShell oder mit dem Zertifikat-Assistenten in Lync Server-Bereitstellungs-Assistent verwaltet werden.



## So aktualisieren Sie Zertifikate mit neuen Antragstellernamen mit der Lync Server-Verwaltungsshell

1.  Melden Sie sich am Computer mit einem Konto an, das über die Rechte und Berechtigungen eines lokalen Administrators verfügt.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Stellen Sie fest, welche Zertifikate dem Server für welchen Verwendungszweck zugeordnet wurden. Sie benötigen diese Informationen im nächsten Schritt, um das aktualisierte Zertifikat zuzuweisen. Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsCertificate

4.  Suchen Sie in der Ausgabe des im vorherigen Schritte eingegebenen Befehls, ob ein einzelnes Zertifikat für mehrere Verwendungszwecke vorhanden ist oder ob für jeden Verwendungszweck ein anderes Zertifikat zugewiesen wurde. Sie können anhand des Use-Parameters feststellen, wie ein Zertifikat verwendet wird. Vergleichen Sie den Thumbprint-Parameter für die angezeigten Zertifikate, um festzustellen, ob ein Zertifikat für mehrere Verwendungszwecke vorgesehen ist.

5.  Aktualisieren Sie das Zertifikat. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Wenn das **Get-CsCertificate**-Cmdlet beispielsweise drei Zertifikate anzeigt, deren Use-Parameter jeweils einen anderen Wert ("Default", "WebServicesInternal" und "WebServicesExternal") enthält und alle denselben Thumbprint-Wert aufweisen, geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Wichtig:**
    
    Wenn für jeden Verwendungszweck ein anderes Zertifikat zugewiesen ist (der Thumbprint-Wert ist für jedes Zertifikat unterschiedlich), ist es wichtig, dass Sie das **Set-CsCertificate**-Cmdlet nicht mit mehreren Typen ausführen. Führen Sie in diesem Fall das **Set-CsCertificate**-Cmdlet für jeden Verwendungszweck separat aus. Beispiel:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Um das Zertifikat anzuzeigen, klicken Sie auf **Start** und auf **Ausführen**. Geben Sie "MMC" ein, um die Microsoft Management Console zu öffnen.

7.  Wählen Sie im MMC-Menü den Eintrag **Datei** und dann **Snap-In hinzufügen/entfernen** aus. Klicken Sie auf **Hinzufügen**. Wählen Sie das **Computerkonto**, wenn Sie dazu aufgefordert werden, und klicken Sie auf **Weiter**.

8.  Wenn sich das Zertifikat auf diesem Computer befindet, wählen Sie **Lokaler Computer** aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **Anderer Computer** aus. Klicken Sie auf **Namen überprüfen**. Geben Sie den Namen des Computers im Feld **Geben Sie die zu verwendenden Objektnamen ein** ein. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst werden kann, wird er unterstrichen. Klicken Sie auf **OK** und dann auf **Fertig stellen**. Klicken Sie auf **OK**, um die Auswahl zu übernehmen und das Dialogfeld **Snap-Ins hinzufügen bzw. entfernen** zu schließen.
    

    > [!IMPORTANT]
    > Wenn das Zertifikat in der Konsole nicht angezeigt wird, stellen Sie sicher, dass Sie nicht "Benutzer" oder "Dienst" ausgewählt haben. Sie müssen "Computer" auswählen, andernfalls kann das richtige Zertifikat nicht gefunden werden.



9.  Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate**, und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen**.

10. Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.

11. Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus. Daraufhin werden alle zugewiesenen alternativen Antragstellernamen angezeigt. Die alternativen Antragstellernamen der Eigenschaft weisen normalerweise den Typ **DNS-Name** auf. Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:
    
      - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
      - Der Name des Servers, dem das Zertifikat zugewiesen wurde.
    
      - Einfache URL-Datensätze, üblicherweise "meet" und "dialin".
    
      - In- und externe Namen von Webdiensten (wie "webpool01.contoso.net" oder "webpool01.contoso.com"), je nachdem, welche Auswahl in Topologie-Generator oder durch Überschreiben von Webdienst-Auswahlmöglichkeiten getroffen wurde.
    
      - Die Datensätze lyncdiscover.\<SIP-Domäne\> und lyncdiscoverinternal.\<SIP-Domäne\>, sofern bereits eine Zuweisung erfolgt ist.
    
    Das letzte Element ist für Sie am interessantesten – falls ein SAN-Eintrag für "lyncdiscover" bzw. für "lyncdiscoverinternal" vorhanden ist.
    
    Sobald Sie über diese Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.

12. Wenn ein alternativer Antragstellername des AutoErmittlungsdiensts, d. h. "lyncdiscover.\>domain name\>" und "lyncdiscoverinternal.\<domain name\>" (basierend darauf, ob es sich um ein externes oder internes Zertifikat handelt) fehlt und Sie ein einzelnes Standardzertifikat für die Typen "Default", "WebServicesInternal" und "WebServiceExternal" verwenden, gehen Sie wie folgt vor:
    
      - Geben Sie in der Befehlszeile von Lync Server-Verwaltungsshell Folgendes ein:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Bei einer hohen Anzahl an SIP-Domänen kann der neue AllSipDomain-Parameter nicht verwendet werden. Verwenden Sie stattdessen den DomainName-Parameter. Wenn Sie den DomainName-Parameter verwenden, müssen Sie den FQDN für die Datensätze "lyncdiscoverinternal" und "lyncdiscover" definieren. Beispiel:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um das Zertifikat zuzuweisen:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für das neu ausgestellte Zertifikat angezeigt wird.

13. Gehen Sie wie folgt vor, wenn Sie separate Zertifikate für "Default", "WebServicesInternal" und "WebServicesExternal" verwenden und ein alternativer Antragstellername für den internen AutoErmittlungsdienst fehlt:
    
      - Geben Sie in der Befehlszeile von Lync Server-Verwaltungsshell Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den DomainName-Parameter verwenden. Bei Verwendung des DomainName-Parameters müssen Sie für den FQDN der SIP-Domäne ein entsprechendes Präfix verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Wenn ein alternativer Antragstellername für einen externen AutoErmittlungsdienst fehlt, geben Sie an der Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den DomainName-Parameter verwenden. Bei Verwendung des DomainName-Parameters müssen Sie für den FQDN der SIP-Domäne ein entsprechendes Präfix verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um die einzelnen Zertifikattypen zuzuweisen:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten einzelnen Zertifikate angezeigt wird.

