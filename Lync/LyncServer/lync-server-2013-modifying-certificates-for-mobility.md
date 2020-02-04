---
title: 'Lync Server 2013: Ändern der Zertifikate für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Ändern der Zertifikate für Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-20_

Um sichere Verbindungen zwischen Ihrer lync-Umgebung und ihren mobilen Clients zu unterstützen, müssen die Secure Socket Layer (SSL)-Zertifikate für Ihren Director-Pool, Front-End-Pool und Reverse-Proxy mit einem zusätzlichen alternativen Betreff-Namen aktualisiert werden ( San)-Einträge. Wenn Sie weitere Details zu den Zertifikatanforderungen für Mobilität lesen müssen, lesen Sie den Abschnitt Zertifikatanforderungen unter [Technische Anforderungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), aber im Grunde müssen Sie neue Zertifikate von der Zertifizierungsstelle mit den zusätzlichen San-Einträgen abrufen und diese Zertifikate dann mithilfe der Schritte dieses Artikels hinzufügen.

Bevor Sie beginnen, ist es in der Regel ratsam, zu wissen, welche alternativen Namen ihre Zertifikate bereits haben. Wenn Sie sich nicht sicher sind, was bereits konfiguriert wurde, gibt es viele Möglichkeiten, dies herauszufinden. Während die Option zum Ausführen der Befehle " **Get-CsCertificate** " und "andere PowerShell" zum Anzeigen dieser Informationen (die wir weiter unten durchlaufen) standardmäßig die Daten abgeschnitten werden, werden möglicherweise nicht alle benötigten Eigenschaften angezeigt. Um sich das Zertifikat und alle seine Eigenschaften genauer anzusehen, können Sie zur Microsoft Management Console (MMC) wechseln und das Zertifikat-Snap-In laden (das wir auch weiter unten durchlaufen), oder Sie können einfach den lync Server-Bereitstellungs-Assistenten einchecken.

Wie bereits erwähnt, führen Sie die folgenden Schritte durch die Aktualisierung der Zertifikate mithilfe der lync Server-Verwaltungsshell und der MMC. Wenn Sie stattdessen den Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten für diesen Zweck verwenden möchten, können Sie für den Director-oder Director-Pool die [Konfiguration von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) überprüfen, wenn Sie einen konfiguriert haben (Dies ist möglicherweise nicht der Fall). Für den Front-End-Server oder den Front-End-Pool empfiehlt es sich, [Zertifikate für Server in lync Server 2013 zu konfigurieren](lync-server-2013-configure-certificates-for-servers.md).

Als letztes sollten Sie Bedenken, dass Sie möglicherweise über ein einzelnes Standardzertifikat in ihrer lync Server 2013-Umgebung verfügen, oder dass Sie möglicherweise getrennte Zertifikate für den Standardwert (alles andere als die Webdienste), WebServicesExternal und WebServicesInternal. Was auch immer Ihre Konfiguration ist, diese Schritte sollten Ihnen helfen.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>So aktualisieren Sie Zertifikate mit neuen alternativen Subjektnamen mithilfe der lync Server-Verwaltungsshell

1.  Sie müssen sich bei Ihrem lync Server 2013-Server mit einem Konto anmelden, das über lokale Administratorrechte und-Berechtigungen verfügt. Wenn Sie die PowerShell **-Anforderungs-CsCertificate** in Schritten 12 und darüber hinaus ausführen, muss das Konto darüber hinaus über Rechte für die angegebene Zertifizierungsstelle (Certification Authority, ca) verfügen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Bevor Sie ein aktualisiertes Zertifikat zuweisen können, müssen Sie herausfinden, welche Zertifikate dem Server zugewiesen wurden und für welche Art von Verwendung. Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsCertificate

4.  Überprüfen Sie die Ausgabe des vorherigen Schritts, um festzustellen, ob ein einzelnes Zertifikat für mehrere Zwecke zugewiesen wurde oder ob für jede Verwendung ein anderes Zertifikat zugewiesen wurde. Schauen Sie sich den use-Parameter an, um zu erfahren, wie ein Zertifikat verwendet wird. Vergleichen Sie den Parameter Fingerabdruck für die angezeigten Zertifikate, um festzustellen, ob dasselbe Zertifikat mehrere Verwendungszwecke aufweist. Behalten Sie den Parameter Fingerabdruck im Auge.

5.  Aktualisieren Sie das Zertifikat. Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Wenn beispielsweise das Cmdlet " **Get-CsCertificate** " ein Zertifikat mit der Verwendung von Default, einem anderen mit einer Verwendung von WebServicesInternal und einem anderen mit einer Verwendung von WebServicesExternal angezeigt hat und alle denselben Fingerabdruckwert hatten, sollten Sie in der Befehlszeile Folgendes eingeben:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Wichtig:**
    
    Wenn für jede Verwendung ein separates Zertifikat zugewiesen wird (damit der von Ihnen geprüfte Fingerabdruckwert für jedes Zertifikat anders ist), ist es wichtig, dass Sie das Cmdlet " **CsCertificate** " **nicht** mit mehreren Typen ausführen, wie im obigen Beispiel gezeigt. Führen Sie in diesem Fall das Cmdlet " **Satz-CsCertificate** " für jede Verwendung separat aus. Beispiel:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Klicken Sie zum Anzeigen des Zertifikats (oder der Zertifikate) auf **Start**, klicken Sie auf **ausführen.**... Geben Sie MMC ein, um die Microsoft Management Console zu öffnen.

7.  Wählen Sie im MMC-Menü **Datei**aus, wählen Sie **Snap-in hinzufügen/entfernen**aus, und wählen Sie Zertifikate aus. Klicken Sie auf **Hinzufügen**. Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**aus, und klicken Sie auf **weiter**.

8.  Wenn es sich um den Server handelt, auf dem sich das Zertifikat befindet, wählen Sie **lokaler Computer**aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, sollten Sie **einen anderen Computer**auswählen, und dann können Sie entweder den vollqualifizierten Domänennamen des Computers eingeben, oder Sie klicken auf **Durchsuchen** **Geben Sie den zu wählenden Objektnamen**ein, und geben Sie den Namen des Computers ein. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst wird, wird er unterstrichen. Klicken Sie auf **OK**und dann auf **Fertig stellen**. Klicken Sie auf **OK** , um die Auswahl zu bestätigen, und schließen Sie das Dialogfeld **Snap-Ins hinzufügen oder entfernen** .

9.  Wenn Sie die Eigenschaften des Zertifikats anzeigen möchten, erweitern Sie **Zertifikate**, erweitern Sie **Personal**, und wählen Sie **Zertifikate**aus. Wählen Sie das Zertifikat aus, das Sie anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie **Öffnen**aus.

10. Wählen Sie in der **Zertifikat** Ansicht **Details**aus. Hier können Sie den Namen des Zertifikat Antragstellers auswählen, indem Sie **Betreff** auswählen und der zugewiesene Antragstellername und die zugehörigen Eigenschaften angezeigt werden.

11. Wenn Sie die alternativen Namen des zugewiesenen betreffs anzeigen möchten, wählen Sie **alternativer Betreffname**aus. Hier werden alle zugewiesenen Subjekt alternativen Namen angezeigt. Die hier gefundenen Alternativen Betreff-Namen sind standardmäßig vom Typ **DNS-Name** . Die folgenden Member sollten angezeigt werden (alle sollten vollqualifizierte Domänennamen sein, die in DNS-Hosteinträgen (A oder, wenn IPv6 AAAA) dargestellt werden:
    
      - Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt
    
      - Server Name, dem das Zertifikat zugewiesen ist
    
      - Einfache URL-Einträge, in der Regel treffen und einwählen
    
      - Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den Optionen, die im Topologie-Generator und über berittenen Webdiensten ausgewählt wurden.
    
      - Wenn Sie bereits zugewiesen ist, wird die lyncdiscover. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> -Datensätze.
    
    Das letzte Element ist das, was Sie am meisten interessieren – wenn ein lyncdiscover-und lyncdiscoverinternal-San-Eintrag vorhanden ist.
    
    Wiederholen Sie diese Schritte, wenn Sie über mehrere zu überprüfende Zertifikate verfügen. Sobald Sie über diese Informationen verfügen, können Sie die Zertifikat Ansicht und die MMC schließen.

12. Gehen Sie wie folgt vor, wenn der Alternative Name des AutoErmittlungsdiensts nicht vorhanden ist und Sie ein einzelnes Standardzertifikat für die Typen Standard, WebServicesInternal und WebServiceExternal verwenden:
    
      - Geben Sie an der Eingabeaufforderung der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die lyncdiscoverinternal-und lyncdiscover-Datensätze definieren. Beispiel:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Um das Zertifikat zuzuweisen, geben Sie Folgendes ein:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Wobei "Daumenabdruck" der für das neu ausgestellte Zertifikat angezeigte Fingerabdruck ist.

13. Gehen Sie bei einem fehlenden internen autodiscover-San bei Verwendung separater Zertifikate für Standard, WebServicesInternal und WebServicesExternal wie folgt vor:
    
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
    
    <div>
    

    > [!NOTE]  
    > Einfach zu beachten: die Schritte 12 und 13 sollten nur ausgeführt werden, wenn das Konto, auf dem Sie ausgeführt wird, Zugriff auf die Zertifizierungsstelle mit den entsprechenden Berechtigungen hat. Wenn Sie sich nicht mit einem Konto anmelden können, das diese Berechtigungen hat, oder wenn Sie eine öffentliche oder Remote-Zertifizierungsstelle für Ihre Zertifikate verwenden, müssen Sie diese über den lync Server-Bereitstellungs-Assistenten anfordern, der oben im Artikel.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

