---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502112"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-12_

Die Zertifikate für Ihre Directorpool, Front-End-Pool und Reverseproxy erfordern zusätzliche Alternative Antragstellernamen Einträge zur Unterstützung sicherer Verbindungen mit lync-Clients.

<div>


> [!NOTE]  
> Mit dem Cmdlet <STRONG>Get-CsCertificate</STRONG> können Sie Informationen über die derzeit zugewiesenen Zertifikate anzeigen. In der Standardansicht werden die Eigenschaften des Zertifikats jedoch abgeschnitten, und die Werte in der Eigenschaft "SubjectAlternativeNames" werden nicht vollständig angezeigt. Mit den Cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate und <STRONG>Set-CsCertificate</STRONG> können Sie einige Informationen anzeigen und Zertifikate anfordern sowie zuweisen. Wenn Sie sich bezüglich der Eigenschaften der alternativen Antragstellernamen im aktuellen Zertifikat unsicher sind, ist dies jedoch nicht unbedingt die am besten geeignete Methode. Um das Zertifikat und alle Eigenschaften Mitglieder anzuzeigen, wird empfohlen, das Zertifikat-Snap-in <EM>Microsoft Management Console (MMC)</EM> zu verwenden oder den lync Server-Bereitstellungs-Assistenten zu verwenden. Im lync Server-Bereitstellungs-Assistenten können Sie den Zertifikat-Assistenten verwenden, um die Zertifikateigenschaften anzuzeigen. Die Verfahren zum Anzeigen, anfordern und Zuweisen eines Zertifikats mithilfe der lync Server-Verwaltungsshell und der <EM>MMC (Microsoft Management Console)</EM> werden in den folgenden Verfahren erläutert. Informationen zum Verwenden des lync Server-Bereitstellungs-Assistenten finden Sie unter Details hier, wenn Sie den optionalen Director oder Directorpool: <A href="lync-server-2013-configure-certificates-for-the-director.md">configure certificates for the Director in lync Server 2013</A>bereitgestellt haben. Informationen zum Front-End-Server oder Front-End-Pool finden Sie unter Details hier: <A href="lync-server-2013-configure-certificates-for-servers.md">Konfigurieren von Zertifikaten für Server in lync Server 2013</A>.<BR>Die ersten Schritte in diesem Verfahren sind Vorbereitungsschritte zur Orientierung an der Rolle, die die aktuellen Zertifikate spielen. Standardmäßig verfügen die Zertifikate über keine lyncdiscover. &lt; sipdomain " &gt; oder" lyncdiscoverinternal ". &lt; Interner Domänennamen &gt; Eintrag, es sei denn, Sie haben zuvor Mobilitätsdienste installiert oder Ihre Zertifikate im Voraus vorbereitet. Dieses Verfahren verwendet den SIP-Domänennamen "contoso.com" und den Beispiel internen Domänennamen "contoso.net".<BR>Die Standardzertifikat Konfiguration für lync Server 2013 und lync Server 2010 besteht darin, ein einzelnes Zertifikat (mit dem Namen "Default") mit dem Verwendungszweck default (für alle Zwecke außer für die Webdienste), "webservicesexternal" und "webservicesinternal" zu verwenden. Optional können Sie ein separates Zertifikat für jeden Zweck verwenden. Zertifikate können mithilfe der Cmdlets lync Server-Verwaltungsshell und Windows PowerShell oder mithilfe des Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten verwaltet werden.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>So aktualisieren Sie Zertifikate mit neuen alternativen Antragstellernamen mithilfe der lync Server-Verwaltungsshell

1.  Melden Sie sich am Computer mit einem Konto an, das über die Rechte und Berechtigungen eines lokalen Administrators verfügt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

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

8.  Wenn sich das Zertifikat auf diesem Computer befindet, wählen Sie **lokaler Computer**aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **einen anderen Computer**aus, geben Sie den vollqualifizierten Domänennamen des Computers ein, oder klicken Sie auf **Durchsuchen** geben Sie den Namen des **zu verwendenden Objekts**ein, geben Sie den Namen des Computers ein. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst ist, wird er unterstrichen. Klicken Sie auf **OK**und dann auf **Fertig stellen**. Klicken Sie auf **OK** , um einen Commit für die Auswahl auszuführen und das Dialogfeld **Snap-Ins hinzufügen oder entfernen** zu schließen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn das Zertifikat nicht in der Konsole angezeigt wird, stellen Sie sicher, dass Sie keinen Benutzer oder Dienst ausgewählt haben. Sie müssen Computer auswählen, oder das probper-Zertifikat kann nicht gefunden werden.

    
    </div>

9.  Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate**, und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen**.

10. Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.

11. Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus. Daraufhin werden alle zugewiesenen alternativen Antragstellernamen angezeigt. Die alternativen Antragstellernamen der Eigenschaft weisen normalerweise den Typ **DNS-Name** auf. Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:
    
      - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
      - Der Name des Servers, dem das Zertifikat zugewiesen wurde.
    
      - Einfache URL-Datensätze, üblicherweise "meet" und "dialin".
    
      - Interne Webdienste und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den im Topologie-Generator und über berittenen Webdiensten vorgenommenen Auswahlmöglichkeiten.
    
      - Wenn bereits zugewiesen, lyncdiscover.\<sipdomain\> und "lyncdiscoverinternal".\<sipdomain\> Datensätze.
    
    Das letzte Element ist für Sie am interessantesten – falls ein SAN-Eintrag für "lyncdiscover" bzw. für "lyncdiscoverinternal" vorhanden ist.
    
    Sobald Sie über diese Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.

12. Wenn ein AutoErmittlungsdienst, das heißt lyncdiscover. \> Domänenname \> und "lyncdiscoverinternal".\<domain name\> (je nachdem, ob es sich um ein externes oder internes Zertifikat handelt) fehlt der Alternative Antragstellername, und Sie verwenden ein einzelnes Standardzertifikat für die Typen Default, "webservicesinternal" und WebServiceExternal, und führen Sie die folgenden Schritte aus:
    
      - Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Verwenden Sie stattdessen den DomainName-Parameter. Wenn Sie den DomainName-Parameter verwenden, müssen Sie den FQDN für die Datensätze "lyncdiscoverinternal" und "lyncdiscover" definieren. Beispiel:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um das Zertifikat zuzuweisen:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für das neu ausgestellte Zertifikat angezeigt wird.

13. Gehen Sie wie folgt vor, wenn Sie separate Zertifikate für "Default", "WebServicesInternal" und "WebServicesExternal" verwenden und ein alternativer Antragstellername für den internen AutoErmittlungsdienst fehlt:
    
      - Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:
        
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
        
        "Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten Zertifikate angezeigt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

