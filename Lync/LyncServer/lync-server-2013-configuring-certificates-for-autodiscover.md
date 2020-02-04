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
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-12_

Die Zertifikate für den Director-Pool, den Front-End-Pool und den Reverse-Proxy erfordern zusätzliche Alternative Namenseinträge, um sichere Verbindungen mit lync-Clients zu unterstützen.

<div>


> [!NOTE]  
> Sie können das Cmdlet <STRONG>Get-CsCertificate</STRONG> verwenden, um Informationen zu den aktuell zugewiesenen Zertifikaten anzuzeigen. Die Standardansicht schneidet jedoch die Eigenschaften des Zertifikats ab und zeigt nicht alle Werte in der SubjectAlternativeNames-Eigenschaft an. Sie können die Cmdlets " <STRONG>Get-CsCertificate</STRONG> ", " <STRONG>Request-</STRONG>CsCertificate" und " <STRONG>Satz-CsCertificate</STRONG> " verwenden, um einige Informationen anzuzeigen und Zertifikate anzufordern und zuzuweisen. Allerdings ist es nicht die beste Methode, wenn Sie sich nicht sicher sind, welche Eigenschaften das "Subject Alternative Names (San)" für das aktuelle Zertifikat hat. Zum Anzeigen des Zertifikats und aller Eigenschafts Mitglieder wird empfohlen, das Zertifikat-Snap-in der <EM>Microsoft Management Console (MMC)</EM> zu verwenden oder den lync Server-Bereitstellungs-Assistenten zu verwenden. Im lync Server-Bereitstellungs-Assistenten können Sie den Zertifikat-Assistenten verwenden, um die Zertifikateigenschaften anzuzeigen. Die Verfahren zum Anzeigen, anfordern und Zuweisen eines Zertifikats mithilfe der lync Server-Verwaltungsshell und der <EM>Microsoft Management Console (MMC)</EM> sind in den folgenden Verfahren detailliert beschrieben. Informationen zum Verwenden des lync Server-Bereitstellungs-Assistenten finden Sie hier, wenn Sie den optionalen Director-oder Director-Pool bereitgestellt haben: <A href="lync-server-2013-configure-certificates-for-the-director.md">Konfigurieren von Zertifikaten für den Director in lync Server 2013</A>. Informationen zu Front-End-Servern oder Front-End-Pools finden Sie hier: <A href="lync-server-2013-configure-certificates-for-servers.md">Konfigurieren von Zertifikaten für Server in lync Server 2013</A>.<BR>Die ersten Schritte in diesem Verfahren sind Vorbereitungsschritte, mit denen Sie sich orientieren können, welche Rolle die aktuellen Zertifikate spielen. Standardmäßig haben die Zertifikate keinen lyncdiscover. &lt;sipdomain&gt; oder lyncdiscoverinternal. &lt;interner Domänennamen&gt; Eintrag, es sei denn, Sie haben zuvor Mobilitätsdienste installiert oder Ihre Zertifikate im Voraus vorbereitet. Bei diesem Verfahren wird der SIP-Domänenname "contoso.com" und der Beispiel interne Domänenname "contoso.net" verwendet.<BR>Die Standardzertifikat Konfiguration für lync Server 2013 und lync Server 2010 besteht darin, ein einzelnes Zertifikat (mit dem Namen "Standard") mit dem Standard für die Zwecke zu verwenden (für alle Zwecke mit Ausnahme der Webdienste), WebServicesExternal und WebServicesInternal. Eine optionale Konfiguration besteht darin, für jeden Zweck separate Zertifikate zu verwenden. Zertifikate können mithilfe der lync Server-Verwaltungsshell und Windows PowerShell-Cmdlets oder mithilfe des Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten verwaltet werden.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>So aktualisieren Sie Zertifikate mit neuen alternativen Subjektnamen mithilfe der lync Server-Verwaltungsshell

1.  Melden Sie sich bei dem Computer mit einem Konto an, das über lokale Administratorrechte und-Berechtigungen verfügt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Finden Sie heraus, welche Zertifikate dem Server zugewiesen wurden und für welche Art von Verwendung. Sie benötigen diese Informationen im nächsten Schritt, um das aktualisierte Zertifikat zuzuweisen. Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsCertificate

4.  Sehen Sie in der Ausgabe des vorherigen Schritts nach, ob ein einzelnes Zertifikat für mehrere Verwendungen zugewiesen ist oder ob für jede Verwendung ein anderes Zertifikat zugewiesen ist. Schauen Sie sich den use-Parameter an, um zu erfahren, wie ein Zertifikat verwendet wird. Vergleichen Sie den Parameter Fingerabdruck für die angezeigten Zertifikate, um festzustellen, ob dasselbe Zertifikat mehrere Verwendungszwecke aufweist.

5.  Aktualisieren Sie das Zertifikat. Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Wenn beispielsweise das Cmdlet " **Get-CsCertificate** " ein Zertifikat mit der Verwendung von Default, einem anderen mit einer Verwendung von WebServicesInternal und einem anderen mit einer Verwendung von WebServicesExternal und alle denselben Fingerabdruckwert aufweisen, geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Wichtig:**
    
    Wenn für jede Verwendung ein separates Zertifikat zugewiesen wird (der Fingerabdruckwert ist für jedes Zertifikat anders), ist es wichtig, dass Sie das Cmdlet " **festgelegt-CsCertificate** " nicht mit mehreren Typen ausführen. Führen Sie in diesem Fall das Cmdlet " **Satz-CsCertificate** " für jede Verwendung separat aus. Beispiel:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Klicken Sie zum Anzeigen des Zertifikats auf **Start**, klicken Sie auf **ausführen.**... Geben Sie MMC ein, um die Microsoft Management Console zu öffnen.

7.  Wählen Sie im MMC-Menü **Datei**aus, wählen Sie **Snap-in hinzufügen/entfernen**aus, und wählen Sie Zertifikate aus. Klicken Sie auf **Hinzufügen**. Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**aus, und klicken Sie auf **weiter**.

8.  Wenn sich das Zertifikat auf diesem Computer befindet, wählen Sie **lokaler Computer**aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **einen anderen Computer**aus, geben Sie den vollqualifizierten Domänennamen des Computers ein, oder klicken Sie auf **Durchsuchen** **Geben Sie den zu wählenden Objektnamen**ein, und geben Sie den Namen des Computers ein. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst wird, wird er unterstrichen. Klicken Sie auf **OK**und dann auf **Fertig stellen**. Klicken Sie auf **OK** , um die Auswahl zu bestätigen, und schließen Sie das Dialogfeld **Snap-Ins hinzufügen oder entfernen** .
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn das Zertifikat nicht in der Konsole angezeigt wird, stellen Sie sicher, dass Sie keinen Benutzer oder Dienst ausgewählt haben. Sie müssen Computer auswählen, oder Sie können das probper-Zertifikat nicht finden.

    
    </div>

9.  Wenn Sie die Eigenschaften des Zertifikats anzeigen möchten, erweitern Sie **Zertifikate**, erweitern Sie **Personal**, und wählen Sie **Zertifikate**aus. Wählen Sie das Zertifikat aus, das Sie anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie **Öffnen**aus.

10. Wählen Sie in der **Zertifikat** Ansicht **Details**aus. Hier können Sie den Namen des Zertifikat Antragstellers auswählen, indem Sie **Betreff** auswählen und der zugewiesene Antragstellername und die zugehörigen Eigenschaften angezeigt werden.

11. Wenn Sie die alternativen Namen des zugewiesenen betreffs anzeigen möchten, wählen Sie **alternativer Betreffname**aus. Alle zugewiesenen Subjekt alternativen Namen werden angezeigt. Die in der Eigenschaft gefundenen Alternativen Betreff-Namen sind standardmäßig vom Typ **DNS-Name** . Die folgenden Member sollten angezeigt werden (alle sollten vollqualifizierte Domänennamen sein, die in DNS-Hosteinträgen (A oder, wenn IPv6 AAAA) dargestellt werden:
    
      - Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt
    
      - Server Name, dem das Zertifikat zugewiesen ist
    
      - Einfache URL-Einträge, in der Regel treffen und einwählen
    
      - Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den Optionen, die im Topologie-Generator und über berittenen Webdiensten ausgewählt wurden.
    
      - Wenn Sie bereits zugewiesen ist, wird die lyncdiscover. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> -Datensätze.
    
    Das letzte Element ist das, was Sie am meisten interessieren, wenn es einen lyncdiscover-und lyncdiscoverinternal-San-Eintrag gibt.
    
    Sobald Sie über diese Informationen verfügen, können Sie die Zertifikat Ansicht und die MMC schließen.

12. Wenn ein AutoErmittlungsdienst, also das lyncdiscover. \>Domänenname\> und lyncdiscoverinternal. \<Domänenname\> (je nachdem, ob es sich um ein externes oder internes Zertifikat handelt) der Betreff alternativer Name fehlt, und Sie verwenden ein einzelnes Standardzertifikat für die Typen Standard, WebServicesInternal und WebServiceExternal, gehen Sie folgendermaßen vor:
    
      - Geben Sie an der Eingabeaufforderung der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die lyncdiscoverinternal-und lyncdiscover-Datensätze definieren. Beispiel:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Um das Zertifikat zuzuweisen, geben Sie Folgendes ein:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Wobei "Daumenabdruck" der für das neu ausgestellte Zertifikat angezeigte Fingerabdruck ist.

13. Gehen Sie wie folgt vor, wenn Sie bei Verwendung separater Zertifikate für Standard, WebServicesInternal und WebServicesExternal für einen fehlenden internen Auto Ermittlungs Betreff Alternative Namen verwenden:
    
      - Geben Sie an der Eingabeaufforderung der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Geben Sie für einen fehlenden externen Auto Ermittlungs Betreff-alternativen Namen in der Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Wenn Sie die einzelnen Zertifikattypen zuweisen möchten, geben Sie Folgendes ein:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Wobei "Daumenabdruck" der für die neu ausgestellten einzelnen Zertifikate angezeigte Fingerabdruck ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

