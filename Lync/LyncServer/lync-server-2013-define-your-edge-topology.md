---
title: 'Lync Server 2013: Definieren der Edgetopologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definieren der Edgetopologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Sie müssen den Topologie-Generator verwenden, um Ihre Topologie zu erstellen, und Sie müssen mindestens einen internen Front-End-Pool oder Standard Edition-Server einrichten, bevor Sie den Edgeserver bereitstellen können. Gehen Sie wie folgt vor, um die Edge-Topologie für einen einzelnen Edgeserver zu definieren, und verwenden Sie dann die Verfahren unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md) , und [exportieren Sie Ihre lync Server 2013-Topologie, und kopieren Sie Sie für die Edge-Installation auf externe Medien](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) , um die Topologie zu veröffentlichen und für Ihren Edgeserver verfügbar zu machen.

<div>


> [!NOTE]  
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



</div>

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, müssen Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. Sie können auch die Administratorrechte und-Berechtigungen erteilen, die für das Hinzufügen von Serverrollen zu einem Benutzerkonto erforderlich sind. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung. Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.

Wenn Sie Ihre Edge-Topologie beim Definieren und Veröffentlichen Ihrer internen Topologie definiert haben und für die zuvor definierte Edge-Topologie keine Änderungen erforderlich sind, müssen Sie Sie nicht definieren und erneut veröffentlichen. Führen Sie das folgende Verfahren nur aus, wenn Sie Änderungen an ihrer Edge-Topologie vornehmen müssen. Sie müssen die zuvor definierte und veröffentlichte Topologie für Ihre Edgeserver verfügbar machen, indem Sie das Verfahren zum [Exportieren Ihrer lync Server 2013-Topologie verwenden und Sie für die Edge-Installation auf externe Medien kopieren](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Sie können den Topology Builder nicht auf einem Edgeserver ausführen. Sie müssen es auf dem Front-End-Server oder auf Standard Edition-Servern ausführen.



</div>

Der Prozess zum Definieren Ihrer Edge-Server-Topologie erfolgt im Topologie-Generator. Die drei Haupttypen von Edge-Server-Topologien, die Sie planen und konfigurieren, sind nachfolgend aufgeführt:

  - So definieren Sie die Topologie für einen einzelnen Edgeserver

  - So definieren Sie die Topologie für einen Lastenausgleichs-Edge-Server Pool

  - So definieren Sie die Topologie für einen Hardware Lastenausgleich-Edge-Pool

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>So definieren Sie die Topologie für einen einzelnen Edgeserver

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die Website, auf der Sie einen Edgeserver bereitstellen möchten.

3.  Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.

4.  Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.

5.  Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:
    
      - Geben Sie in **Pool FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Schnittstelle für den Edgeserver ein.
        
        <div>
        

        > [!IMPORTANT]  
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein kurzer Name und kein FQDN. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss). Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.

        
        </div>
    
      - Klicken Sie auf **Einzelcomputer Pool**, und klicken Sie dann auf **weiter**.

6.  Gehen **Sie unter Features auswählen**wie folgt vor:
    
      - Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriffsdienst, den lync Server 2013-Webkonferenzdienst und a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden. Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server. Wenn Ihre Bereitstellung beispielsweise einen Edge-Pool oder einen einzelnen Edgeserver umfasst, der in New York bereitgestellt und in London bereitgestellt wurde, und Sie die Unterstützung der Föderation auf dem New York Edge-Pool oder einem Single Edge-Server aktivieren, wird der Signal Verkehr für verbundene Benutzer durch das New York durchlaufen. Edge-Pool oder Single Edge-Server. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .

7.  Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:
    
      - **Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
    Sie können auch den Edgeserver oder den Edge-Pool so konfigurieren, dass für die externen IP-Adressen eine Adresse für die Netzwerkadressübersetzung verwendet wird. Aktivieren Sie dazu das Kontrollkästchen, um **die externe IP-Adresse dieses Edge-Pools von NAT zu übersetzen**.

8.  Führen Sie in **externen FQDNs**die folgenden Aktionen aus:
    
      - Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst). Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.

        
        </div>
    
      - Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie die externen FQDNs für **SIP-Zugriff**, **Webkonferenz** und **Audiovideo**ein, wobei die Standardanschlüsse beizubehalten sind.

9.  Klicken Sie auf **Weiter**.

10. Geben Sie unter interne **IP-Adresse definieren**die IP-Adresse Ihres Edge-Servers unter **interner IPv4-Adresse** und **interner IPv6** -Adresse ein, wie dies für Ihre Anforderungen angemessen ist. Klicken Sie auf **Weiter**.

11. Gehen Sie unter **externe IP-Adresse definieren**wie folgt vor:
    
      - Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenzdienst und a/V-Edgedienst entschieden haben, geben Sie die externe IPv4-Adresse des Edgeserver in **SIP Access**ein, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie sich für die Verwendung von IPv6-Adressen entschieden haben, geben Sie die externe IPv6-Adresse des Edge-Servers in **SIP Access**ein, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie keinen einzelnen FQDN und keine IP-Adresse für den SIP Access-, Webkonferenzdienst und einen/v-Edgedienst verwendet haben, geben Sie die externen IPv4-Adressen des Edgeserver in **SIP Access**, **Web Conferencing**und **a/v Conferencing ein**, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie sich für die Verwendung von IPv6-Adressen entschieden haben und sich nicht für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und den a/v-Edgedienst entschieden haben, geben Sie die externen IPv6-Adressen des Edgeserver in **SIP Access**, **Web Conferencing**und **a/v Conferencing ein**, und klicken Sie dann auf **weiter**.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.

        
        </div>

12. Wenn Sie sich für die Verwendung von NAT entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie unter **öffentliche IPv4-Adresse für den A/V-Edgedienst**die öffentliche IPv4-Adresse ein, die von NAT übersetzt werden soll, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies sollte die externe IP-Adresse des A/V-Edgedienst sein.

    
    </div>

13. Wenn Sie sich für die Verwendung von NAT-und IPv6-Adressen entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie in **der öffentlichen IPv6-Adresse für den A/V-Edgedienst**die öffentliche IPv6-Adresse ein, die von NAT übersetzt werden soll, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies sollte die externe IP-Adresse des A/V-Edgedienst sein.

    
    </div>

14. Wählen Sie im Bereich "nächsten Hop **definieren**" im Pool für den **nächsten Hop**den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann. Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Director aus. Klicken Sie dann auf **weiter**.

15. Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, um diesem Edgeserver zugeordnet zu werden, indem Sie die Namen der internen Pools auswählen, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden sollen.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist. Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

16. Klicken Sie auf **Fertig stellen**.

17. Veröffentlichen Sie Ihre Topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>So definieren Sie die Topologie für einen DNS Load Balancing Edge-Server Pool

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die Website, auf der Sie Edgeserver bereitstellen möchten.

3.  Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.

4.  Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.

5.  Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:
    
      - Geben Sie in **Pool FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die interne Verbindung des Edge-Pools ein.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Name, den Sie für den Pool angeben, muss der Name des internen Edge-Pools sein. Dieser muss als FQDN definiert werden. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).

        
        </div>
    
      - Klicken Sie auf **Pool mit mehreren Computern**, und klicken Sie dann auf **weiter**.

6.  Gehen **Sie unter Features auswählen**wie folgt vor:
    
      - Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP Access, lync Server 2013 Web Conferencing Service und a/V Edge Services verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** . Klicken Sie auf **weiter** .
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden. Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder den einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder den einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .

7.  Klicken Sie auf **Weiter**.

8.  Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:
    
      - **Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
    Sie können auch den Edgeserver oder den Edge-Pool so konfigurieren, dass für die externen IP-Adressen eine Adresse für die Netzwerkadressübersetzung verwendet wird. Aktivieren Sie dazu das Kontrollkästchen, um **die externe IP-Adresse dieses Edge-Pools von NAT zu übersetzen**.

9.  Führen Sie in **externen FQDNs**die folgenden Aktionen aus:
    
      - Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst). Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.

        
        </div>
    
      - Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**den FQDN ein, den Sie für die öffentlich zugängliche Seite des Edge-Pools ausgewählt haben. Geben Sie in **Audio/Video**den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools ausgewählt haben. Verwenden Sie die Standardanschlüsse.

10. Klicken Sie auf **Weiter**.

11. Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**.

12. Gehen Sie unter **Interner FQDN und IP-Adresse**wie folgt vor:
    
      - Geben Sie unter **interne IPv4-Adresse**die IPv4-Adresse und die **interne IPv6-Adresse** ein, die für Ihre Anforderungen für den ersten Edgeserver, den Sie in diesem Pool erstellen möchten, geeignet sind.
    
      - Geben Sie im **internen FQDN**den FQDN des ersten Edge-Servers ein, den Sie in diesem Pool erstellen möchten.
        
        <div>
        

        > [!NOTE]  
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie beim Zuweisen von FQDNs ihrer lync-Server,-Edgeserver,-Pools und-Arrays nur Standardzeichen (einschließlich a – z, a – z, 0 – 9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss). Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.

        
        </div>

13. Klicken Sie auf **Weiter**.

14. Gehen Sie unter **externe IP-Adressen definieren**wie folgt vor:
    
      - Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IP-Adresse des Edgeserver in **SIP Access**ein.
    
      - Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben. Geben Sie in **A/V-Konferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.

15. Klicken Sie auf **Weiter**.

16. Wenn Sie sich für die Aktivierung von IPv6-Adressen entschieden haben, gehen Sie unter **definieren externer IP-Adressen**wie folgt vor:
    
      - Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IPv6-Adresse des Edgeserver in **SIP Access**ein.
    
      - Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben. Geben Sie in **A/V-Konferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.

    
    </div>

17. Klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Der erste Edge-Server, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.

    
    </div>

18. Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**, und wiederholen Sie dann die Schritte 11 bis 14 für den zweiten Edgeserver, den Sie dem Edge-Pool hinzufügen möchten.

19. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie unter **Definieren der Computer in diesem Pool**auf **weiter** .
    
    <div>
    

    > [!NOTE]  
    > An dieser Stelle können Sie die beiden Edgeserver in Ihrem Pool sehen.

    
    </div>

20. Wenn Sie sich für die Verwendung von NAT entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie unter **öffentliche IP-Adresse**die öffentlichen IPv4-und IPv6-Adressen (sofern erforderlich) ein, die von NAT übersetzt werden sollen, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies sollte die externe IP-Adresse der A/V-Kante sein.

    
    </div>

21. Wählen Sie im **Feld nächsten Hop definieren**in der Liste **Nächster Hop-Pool** den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann. Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors aus. Klicken Sie dann auf **weiter**.

22. Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, die diesem Edgeserver zugeordnet werden sollen, indem Sie die Namen der internen Pools auswählen, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden sollen.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist. Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

23. Klicken Sie auf **Fertig stellen**.

24. Veröffentlichen Sie Ihre Topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>So definieren Sie die Topologie für einen Hardwarelastenausgleich-Edgeserver-Pool

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die Website, auf der Sie Edgeserver bereitstellen möchten.

3.  Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und wählen Sie dann **neuer Edge-Pool**aus.

4.  Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.

5.  Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:
    
      - Geben Sie in **FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den Sie für die interne Seite des Edge-Pools ausgewählt haben.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Name, den Sie für den Pool angeben, muss der Name des internen Edge-Pools sein. Dieser muss als FQDN definiert werden. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).

        
        </div>
    
    <!-- end list -->
    
      - Klicken Sie auf **Pool für mehrere Computer**und dann auf **weiter**.

6.  Gehen **Sie unter Features auswählen** wie folgt vor:
    
      - Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriffsdienst, den lync Server-Webkonferenzdienst und den a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN #a0 IP-Adresse verwenden** .
    
      - Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, es kann jedoch nur ein Edge-Pool oder ein Edgeserver in Ihrer Organisation extern für den Verbund veröffentlicht werden. Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder den einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder den einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .

7.  Klicken Sie auf **Weiter**.

8.  Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:
    
      - **Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
      - **Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Aktivieren Sie <STRONG>nicht</STRONG> das Kontrollkästchen <STRONG>externe IP-Adresse des Edge-Pools, der von NAT übersetzt wird</STRONG> . Netzwerkadressübersetzung (Network Address Translation, NAT) wird nicht unterstützt, wenn Sie den Hardwarelastenausgleich verwenden.

    
    </div>

9.  Führen Sie in **externen FQDNs**die folgenden Aktionen aus:
    
      - Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst). Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.

        
        </div>
    
      - Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**den FQDN ein, den Sie für die öffentlich zugängliche Seite des Edge-Pools ausgewählt haben. Geben Sie in **Audio/Video**den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools ausgewählt haben. Verwenden Sie die Standardanschlüsse.
        
        <div>
        

        > [!NOTE]  
        > Hierbei handelt es sich um die öffentlich zugänglichen VIP-FQDNs (Virtual IP) für den Pool.

        
        </div>

10. Klicken Sie auf **Weiter**.

11. Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**.

12. Gehen Sie unter **externe IP-Adressen definieren**wie folgt vor:
    
      - Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenzdienst und a/V-Edgedienst entschieden haben, geben Sie die externe IPv4-Adresse des Edgeserver in **SIP Access**ein. externe IP-Adresse des Edge-Servers in **SIP Access**.
    
      - Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben. Geben Sie in **A/V-Konferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.

13. Klicken Sie auf **Weiter**.

14. Wenn Sie sich für die Aktivierung von IPv6-Adressen entschieden haben, gehen Sie unter **definieren externer IP-Adressen**wie folgt vor:
    
      - Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IPv6-Adresse des Edgeserver in **SIP Access**ein.
    
      - Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben. Geben Sie in **Webkonferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben. Geben Sie in **A/V-Konferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.

    
    </div>

15. Klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Der erste Edge-Server, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.

    
    </div>

16. Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**, und wiederholen Sie dann die Schritte 11 bis 14 für den zweiten Edgeserver, den Sie Ihrem Edge-Pool hinzufügen möchten.

17. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie unter **Definieren der Computer in diesem Pool**auf **weiter** .
    
    <div>
    

    > [!NOTE]  
    > An dieser Stelle können Sie die beiden Edgeserver in Ihrem Pool sehen.

    
    </div>

18. Wählen Sie im **Feld nächsten Hop definieren**in der Liste **Nächster Hop-Pool** den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann. Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors aus. Klicken Sie dann auf **weiter**.

19. Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, die diesem Edgeserver zugeordnet werden sollen, indem Sie die Namen der internen Pools auswählen, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden sollen.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden. Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist. Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

20. Klicken Sie auf **Fertig stellen**.

21. Veröffentlichen Sie Ihre Topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

