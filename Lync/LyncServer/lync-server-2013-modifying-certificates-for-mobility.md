---
title: 'Lync Server 2013: Ändern der Zertifikate für Mobilität'
TOCTitle: Ändern der Zertifikate für Mobilität
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690015(v=OCS.15)
ms:contentKeyID: 49293963
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der Zertifikate für Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-06-20_

Um eine sichere Kommunikation zwischen Ihrer Lync-Umgebung und den mobilen Clients zu ermöglichen, müssen die SSL-Zertifikate für Ihren Directorpool, Front-End-Pool und Reverseproxy durch zusätzliche SAN-Einträge (Subject Alternative Name) für alternativer Antragstellernamen ergänzt werden. Weitere Informationen dazu, welche Anforderungen an Zertifikate für die Mobilität erfüllt sein müssen, finden Sie im Abschnitt "Zertifikatanforderungen" unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Allgemein gilt jedoch, dass Sie sich neue Zertifikate von der Zertifizierungsstelle inklusive der zusätzlichen SAN-Einträge besorgen und diese dann gemäß den Anweisungen in diesem Artikel hinzufügen müssen.

Bevor Sie damit beginnen, empfiehlt es sich, sich ein Bild zu machen, welche alternativen Antragstellernamen bereits in Ihren Zertifikaten vorhanden sind. Es gibt eine Reihe von Möglichkeiten, dies herauszufinden, falls Sie sich nicht sicher sind. Obwohl die Möglichkeit besteht, zum Anzeigen dieser Informationen **Get-CsCertificate** oder andere PowerShell-Befehle zu nutzen (eine Anleitung hierzu finden Sie weiter unten), werden die Daten in diesem Format standardmäßig unvollständig angezeigt, sodass Sie möglicherweise nicht alle benötigten Eigenschaften zu sehen bekommen. Um sich einen guten Überblick über das Zertifikat mitsamt all seiner Eigenschaften zu verschaffen, öffnen Sie die Microsoft Management Console (MMC) und laden Sie das Zertifikat-Snap-In (auch hierzu finden Sie weiter unten eine Anleitung). Sie können das Zertifikat aber auch einfach im Bereitstellungs-Assistent von Lync Server überprüfen.

Wie oben erwähnt, folgt nun eine Anleitung zum Aktualisieren der Zertifikate mithilfe der Lync Server-Verwaltungsshell und der MMC. Wenn Sie lieber den Zertifikat-Assistenten im Bereitstellungs-Assistenten von Lync Server verwenden möchten, schauen Sie sich [Konfigurieren von Zertifikaten für den Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) für den Director oder Directorpool an, falls Sie einen solchen konfiguriert haben. Informationen zum Konfigurieren von Zertifikaten für Front-End-Server oder Front-End-Pools finden Sie unter [Konfigurieren von Zertifikaten für Server in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Bevor Sie beginnen, sollten Sie daran denken, dass Sie entweder ein einzelnes Standardzertifikat in Ihrer Lync Server 2013-Umgebung oder getrennte Zertifikate für "Standard" (dies betrifft alles außer die Webdiensten), WebServicesExternal und WebServicesInternal verwenden. Wie immer Ihre Konfiguration auch aussehen mag, mit den folgenden Anleitungen sollten Ihr Ziel erreichen.

## So aktualisieren Sie Zertifikate mit neuen Antragstellernamen mit der Lync Server-Verwaltungsshell

1.  Melden Sie sich bei Ihrem Lync Server 2013-Server unter einem Konto an, das über Administratorrechte verfügt. Sollten Sie mit dem **Request-CsCertificate**-Cmdlet von PowerShell ab Schritt 12 arbeiten, benötigt das Konto außerdem die Berechtigungen für die angegebene Zertifizierungsstelle (CA).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Vor dem Zuweisen eines aktualisierten Zertifikats, müssen Sie herausfinden, welche Zertifikate dem Server für welche Verwendungszwecke zugewiesen wurden. Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsCertificate

4.  Suchen Sie in der Ausgabe des im vorherigen Schritte eingegebenen Befehls, ob ein einzelnes Zertifikat für mehrere Verwendungszwecke vorhanden ist oder ob für jeden Verwendungszweck ein anderes Zertifikat zugewiesen wurde. Sie können anhand des Use-Parameters feststellen, wie ein Zertifikat verwendet wird. Vergleichen Sie den Thumbprint-Parameter für die angezeigten Zertifikate, um festzustellen, ob ein Zertifikat für mehrere Verwendungszwecke vorgesehen ist. Beahlten Sie den Thumbprint-Parameter im Auge.

5.  Aktualisieren Sie das Zertifikat. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Wenn das **Get-CsCertificate**-Cmdlet beispielsweise drei Zertifikate anzeigt, deren Use-Parameter jeweils einen anderen Wert ("Default", "WebServicesInternal" und "WebServicesExternal") enthält und alle denselben Thumbprint-Wert aufweisen, geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Wichtig:**
    
    Wenn für jeden Verwendungszweck ein getrenntes Zertifikat zugewiesen wurde (und der oben überprüfte Thumbprint-Wert somit für jedes Zertifikat unterschiedlich ist), ist es wichtig, das **Set-CsCertificate**-Cmdlet **nicht** wie im Beispiel oben mit unterschiedlichen Typen auszuführen. Führen Sie das **Set-CsCertificate**-Cmdlet in diesem Fall für jeden Verwendungszweck separat aus. Beispiel:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Um das/die Zertifikate anzuzeigen, klicken Sie auf **Start** und auf **Ausführen** . Geben Sie "MMC" ein, um die Microsoft Management Console zu öffnen.

7.  Wählen Sie im MMC-Menü den Eintrag **Datei** und dann **Snap-In hinzufügen/entfernen** aus. Klicken Sie auf **Hinzufügen** . Wählen Sie das **Computerkonto** , wenn Sie dazu aufgefordert werden, und klicken Sie auf **Weiter** .

8.  Wenn sich das Zertifikat auf diesem Server befindet, wählen Sie **Lokaler Computer** aus. Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **Anderer Computer** aus. Klicken Sie auf **Namen überprüfen** . Nun können Sie entweder den vollqualifizierten Domänennamen des Computers eingeben oder im Feld **Namen des auszuwählenden Objekts eingeben** auf **Durchsuchen** klicken und den Namen des Computers eingeben. Klicken Sie auf **Namen überprüfen**. Wenn der Name des Computers aufgelöst werden kann, wird er unterstrichen. Klicken Sie auf **OK** und dann auf **Fertig stellen** . Klicken Sie auf **OK** , um die Auswahl zu übernehmen und das Dialogfeld **Snap-Ins hinzufügen bzw. entfernen** zu schließen.

9.  Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate** , und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen** .

10. Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.

11. Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus. Alle zugewiesenen alternativen Antragstellernamen werden hier angezeigt. Sie weisen normalerweise den Typ **DNS-Name** auf. Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:
    
      - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
      - Der Name des Servers, dem das Zertifikat zugewiesen wurde.
    
      - Einfache URL-Datensätze, üblicherweise "meet" und "dialin".
    
      - In- und externe Namen von Webdiensten (wie "webpool01.contoso.net" oder "webpool01.contoso.com"), je nachdem, welche Auswahl in Topologie-Generator oder durch Überschreiben von Webdienst-Auswahlmöglichkeiten getroffen wurde.
    
      - Die Datensätze lyncdiscover.\<SIP-Domäne\> und lyncdiscoverinternal.\<SIP-Domäne\>, sofern bereits eine Zuweisung erfolgt ist.
    
    Das letzte Element ist für Sie am interessantesten – falls ein SAN-Eintrag für "lyncdiscover" bzw. für "lyncdiscoverinternal" vorhanden ist.
    
    Wiederholen Sie diese Schritte, wenn Sie mehrere Zertifikate überprüfen müssen. Sobald Sie über die gewünschten Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.

12. Gehen Sie wie folgt vor, wenn ein alternativer Antragstellername für den AutoErmittlungsdienst fehlt und Sie ein einzelnes Standardzertifikat für die Typen "Default", "WebServicesInternal" und "WebServicesExternal" verwenden:
    
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
        
        Bei einer hohen Anzahl an SIP-Domänen kann der neue AllSipDomain-Parameter nicht verwendet werden. Verwenden Sie stattdessen den DomainName-Parameter. Wenn Sie den DomainName-Parameter verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne definieren. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Wenn ein alternativer Antragstellername für einen externen AutoErmittlungsdienst fehlt, geben Sie an der Befehlszeile Folgendes ein:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Bei einer hohen Anzahl an SIP-Domänen kann der neue AllSipDomain-Parameter nicht verwendet werden. Verwenden Sie stattdessen den DomainName-Parameter. Wenn Sie den DomainName-Parameter verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne definieren. Beispiel:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Geben Sie Folgendes ein, um die einzelnen Zertifikattypen zuzuweisen:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten Zertifikate angezeigt wird.
    

    > [!NOTE]
    > Anmerkung: Die Schritte 12 und 13 sollten nur dann ausgeführt werden, wenn über das verwendete Konto mit entsprechenden Berechtigungen auf die Zertifizierungsstelle zugegriffen werden kann. Steht ein Konto mit den entsprechenden Berechtigungen nicht zur Verfügung oder Sie nutzen eine öffentliche oder entfernte Zertifizierungsstelle für Ihre Zertifikate, müssen Sie Ihre Zertifikate über den am Anfang des Artikels angesprochenen Bereitstellungs-Assistenten von Lync Server anfordern.


