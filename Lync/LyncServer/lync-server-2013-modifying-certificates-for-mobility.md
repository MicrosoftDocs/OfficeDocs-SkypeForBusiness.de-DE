---
title: 'Lync Server 2013: Ändern von Zertifikaten für Mobilität'
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
ms.openlocfilehash: b10ea662d055812b9fccaa730a936033aaea077c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515162"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Ändern von Zertifikaten für Mobilität in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-20_

Um sichere Verbindungen zwischen Ihrer lync-Umgebung und ihren mobilen Clients zu unterstützen, müssen die SSL-Zertifikate (Secure Socket Layer) für Ihre Directorpool, Front-End-Pool und Reverseproxy mit einigen zusätzlichen alternativen Antragstellernamen (San-Einträgen) aktualisiert werden. Wenn Sie weitere Details zu den Zertifikatanforderungen für Mobilität lesen müssen, lesen Sie den Abschnitt Zertifikatanforderungen unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), aber im Grunde müssen Sie neue Zertifikate von der Zertifizierungsstelle mit den zusätzlichen San-Einträgen erhalten, und fügen Sie diese Zertifikate dann mithilfe der Schritte dieses Artikels hinzu.

Bevor Sie beginnen, ist es normalerweise ratsam zu wissen, welche alternativen Antragstellernamen ihre Zertifikate bereits besitzen. Wenn Sie nicht sicher sind, was bereits konfiguriert ist, gibt es viele Möglichkeiten, dies herauszufinden. Während die Option zum Ausführen der Befehle **Get-CsCertificate** und other PowerShell zum Anzeigen dieser Informationen (die wir weiter unten durchlaufen) standardmäßig die Daten abgeschnitten werden, sodass Sie möglicherweise nicht alle Eigenschaften angezeigt werden, die Sie benötigen. Um ein gutes Bild des Zertifikats und seiner Eigenschaften zu erhalten, können Sie zur Microsoft Management Console (MMC) wechseln und das Zertifikat-Snap-in (das wir auch weiter unten durchlaufen) laden, oder Sie können einfach den lync Server-Bereitstellungs-Assistenten einchecken.

Wie oben erwähnt, führen Sie die folgenden Schritte durch die Aktualisierung der Zertifikate mithilfe der lync Server-Verwaltungsshell und der MMC. Wenn Sie den Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten für diese stattdessen verwenden möchten, können Sie in lync Server 2013 für den Director oder den Directorpool [Konfigurieren von Zertifikaten für den Director](lync-server-2013-configure-certificates-for-the-director.md) überprüfen, wenn Sie einen konfiguriert haben (möglicherweise nicht). Für die Front-End-Server oder Front-End-Pool sollten Sie die Informationen zum [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)anzeigen.

Als letztes müssen Sie Bedenken, dass Sie möglicherweise ein einzelnes Standardzertifikat in ihrer lync Server 2013 Umgebung haben oder wenn Sie unterschiedliche Zertifikate für den Standardwert (alles andere als die Webdienste), "webservicesexternal" und "webservicesinternal". Unabhängig von Ihrer Konfiguration sollten diese Schritte Ihnen helfen.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>So aktualisieren Sie Zertifikate mit neuen alternativen Antragstellernamen mithilfe der lync Server-Verwaltungsshell

1.  Sie müssen sich bei Ihrem lync Server 2013 Server mit einem Konto anmelden, das über lokale Administratorrechte und-Berechtigungen verfügt. Wenn Sie den PowerShell **-Anforderungs-CsCertificate** in den Schritten 12 und darüber hinaus ausführen, benötigt das Konto außerdem Rechte für die angegebene Zertifizierungsstelle (Certification Authority, ca).

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Bevor Sie ein aktualisiertes Zertifikat zuweisen können, müssen Sie herausfinden, welche Zertifikate dem Server zugewiesen wurden und für welchen Verwendungstyp. Geben Sie in die Befehlszeile Folgendes ein:
    
        Get-CsCertificate

4.  Überprüfen Sie die Ausgabe des vorherigen Schritts, um festzustellen, ob ein einzelnes Zertifikat für mehrere Zwecke verwendet wurde oder ob für jede Verwendung ein anderes Zertifikat zugewiesen wurde. Suchen Sie im Use-Parameter, um herauszufinden, wie ein Zertifikat verwendet wird. Vergleichen Sie den Thumbprint-Parameter für die angezeigten Zertifikate, um festzustellen, ob ein Zertifikat für mehrere Verwendungszwecke vorgesehen ist. Halten Sie den Fingerabdruck Parameter im Auge.

5.  Aktualisieren Sie das Zertifikat. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Wenn das **Get-CsCertificate-** Cmdlet beispielsweise ein Zertifikat mit der Standardeinstellung, ein anderes mit einer Verwendung von "webservicesinternal" und ein anderes mit einer Verwendung von "webservicesexternal" angezeigt wurde und alle denselben Fingerabdruckwert hatten, sollten Sie Folgendes eingeben:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Wichtig:**
    
    Wenn für jede Verwendung ein separates Zertifikat zugewiesen wird (damit der von Ihnen überprüfte Fingerabdruckwert für jedes Zertifikat unterschiedlich ist), ist es wichtig, dass Sie das Cmdlet " **CsCertificate** " **nicht** mit mehreren Typen ausführen, wie im obigen Beispiel dargestellt. Führen Sie in diesem Fall das **Set-CsCertificate**-Cmdlet für jeden Verwendungszweck separat aus. Zum Beispiel:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Klicken Sie zum Anzeigen des Zertifikats (oder der Zertifikate) auf **Start**, klicken Sie auf **ausführen.** Geben Sie "MMC" ein, um die Microsoft Management Console zu öffnen.

7.  Wählen Sie im MMC-Menü den Eintrag **Datei** und dann **Snap-In hinzufügen/entfernen** aus. Klicken Sie auf **Hinzufügen**. Wählen Sie das **Computerkonto**, wenn Sie dazu aufgefordert werden, und klicken Sie auf **Weiter**.

8.  Wenn es sich um den Server handelt, auf dem sich das Zertifikat befindet, wählen Sie **lokaler Computer**aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **einen anderen Computer**aus, und geben Sie dann entweder den vollqualifizierten Domänennamen des Computers ein, oder klicken Sie auf **Durchsuchen** **Geben Sie den zu verwendenden Objektnamen**ein ein, und geben Sie den Namen des Computers ein. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst wird, wird er unterstrichen. Klicken Sie auf **OK**und dann auf **Fertig stellen**. Klicken Sie auf **OK** , um einen Commit für die Auswahl auszuführen und das Dialogfeld **Snap-Ins hinzufügen oder entfernen** zu schließen.

9.  Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate**, und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen**.

10. Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.

11. Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus. Hier werden alle zugewiesenen alternativen Antragstellernamen angezeigt. Die alternativen Antragstellernamen, die hier gefunden werden, sind standardmäßig vom Typ **DNS-Name** . Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:
    
      - Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt
    
      - Der Name des Servers, dem das Zertifikat zugewiesen wurde.
    
      - Einfache URL-Datensätze, üblicherweise "meet" und "dialin".
    
      - Interne Webdienste und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den im Topologie-Generator und über berittenen Webdiensten vorgenommenen Auswahlmöglichkeiten.
    
      - Wenn bereits zugewiesen, lyncdiscover.\<sipdomain\> und "lyncdiscoverinternal".\<sipdomain\> Datensätze.
    
    Am meisten interessieren Sie sich für das letzte Element – Wenn ein lyncdiscover-und "lyncdiscoverinternal"-San-Eintrag vorhanden ist.
    
    Wiederholen Sie diese Schritte, wenn Sie über mehrere Zertifikate zu überprüfen haben. Sobald Sie über diese Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.

12. Gehen Sie wie folgt vor, wenn ein alternativer Antragstellername für den AutoErmittlungsdienst fehlt und Sie ein einzelnes Standardzertifikat für die Typen "Default", "WebServicesInternal" und "WebServicesExternal" verwenden:
    
      - Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die "lyncdiscoverinternal"-und lyncdiscover-Datensätze definieren. Beispiel:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um das Zertifikat zuzuweisen:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für das neu ausgestellte Zertifikat angezeigt wird.

13. Gehen Sie für ein fehlendes internes Auto Ermittlungs-San bei Verwendung von separaten Zertifikaten für Default, "webservicesinternal" und "webservicesexternal" folgendermaßen vor:
    
      - Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Wenn ein alternativer Antragstellername für einen externen AutoErmittlungsdienst fehlt, geben Sie an der Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den Domain Name-Parameter verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um die einzelnen Zertifikattypen zuzuweisen:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten Zertifikate angezeigt wird.
    
    <div>
    

    > [!NOTE]  
    > Beachten Sie, dass die Schritte 12 und 13 nur ausgeführt werden sollten, wenn das Konto, auf dem Sie ausgeführt werden, über die entsprechenden Berechtigungen auf die Zertifizierungsstelle zugreifen kann. Wenn Sie sich nicht mit einem Konto anmelden können, das diese Berechtigungen hat, oder wenn Sie eine öffentliche oder Remotezertifizierungsstelle für Ihre Zertifikate verwenden, müssen Sie diese über den lync Server-Bereitstellungs-Assistenten anfordern, der oben im Artikel behandelt wurde.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

