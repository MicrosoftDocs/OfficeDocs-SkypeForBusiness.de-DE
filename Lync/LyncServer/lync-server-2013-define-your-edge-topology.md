---
title: 'Lync Server 2013: Definieren Ihrer Edge-Topologie'
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
ms.openlocfilehash: 9bd7c52eef58d4e40c767f48a296a83a8c056525
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definieren Ihrer Edge-Topologie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Sie müssen den Topologie-Generator verwenden, um Ihre Topologie zu erstellen, und Sie müssen mindestens eine interne Front-End-Pool oder Standard Edition-Server einrichten, bevor Sie Ihre Edgeserver bereitstellen können. Verwenden Sie das folgende Verfahren, um die Edge-Topologie für einen einzelnen Edgeserver zu definieren, und verwenden Sie dann die Verfahren unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md) , und [exportieren Sie Ihre lync Server 2013 Topologie, und kopieren Sie Sie in externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) , um die Topologie zu veröffentlichen und Sie für Ihre Edgeserver verfügbar zu machen.

<div>


> [!NOTE]  
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



</div>

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, müssen Sie als Benutzer angemeldet sein, der Mitglied der Gruppe RTCUniversalServerAdmins und Domänenadministratoren ist. Sie können auch die Administratorrechte und-Berechtigungen erteilen, die für das Hinzufügen von Serverrollen zu einem Benutzerkonto erforderlich sind. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

Wenn Sie die Edge-Topologie bei der Definition und Veröffentlichung ihrer internen Topologie definiert haben und keine Änderungen an der zuvor definierten Edge-Topologie erforderlich sind, müssen Sie Sie nicht definieren und erneut veröffentlichen. Verwenden Sie das folgende Verfahren nur, wenn Sie Änderungen an ihrer Edge-Topologie vornehmen müssen. Sie müssen die zuvor definierte und veröffentlichte Topologie für Ihre Edgeserver zur Verfügung stellen, und zwar mithilfe des Verfahrens unter [Exportieren Ihrer lync Server 2013 Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Sie können den Topologie-Generator nicht aus einem Edgeserver ausführen. Er muss entweder auf dem Front-End-Server oder auf Standard Edition-Servern ausgeführt werden.



</div>

Der Vorgang zum Definieren Ihrer Edgeserver Topologie erfolgt im Topologie-Generator. Die drei primären Edgeserver-Topologietypen, die Sie planen und konfigurieren, werden nachfolgend aufgelistet:

  - So definieren Sie die Topologie für einen einzelnen Edgeserver

  - So definieren Sie die Topologie für einen Edgeserverpool mit Lastenausgleich

  - So definieren Sie die Topologie für einen Edgeserverpool mit Hardwarelastenausgleich

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>So definieren Sie die Topologie für einen einzelnen Edgeserver

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem ein Edgeserver bereitgestellt werden soll.

3.  Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Schnittstelle für den Edgeserver ein.
        
        <div>
        

        > [!IMPORTANT]  
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.

        
        </div>
    
      - Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter**.

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst, lync Server 2013 Webkonferenzdienst und a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise ff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienje einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.

7.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
      - **IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
    Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.

8.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.

        
        </div>
    
      - Wenn Sie in **Funktionen auswählen** nicht festgelegt haben, dass ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie die externen FQDNs für **SIP-Zugriff**, **Webkonferenzen** und **Audio/Video** ein. Behalten Sie dabei die Standardports bei.

9.  Klicken Sie auf **Weiter**.

10. Geben Sie unter **Interne IP-Adresse definieren** in **Interne IPv4-Adresse** bzw. **Interne IPv6-Adresse** die IP-Adresse Ihres Edgeservers ein, und klicken Sie anschließend auf **Weiter**.

11. Führen Sie in **Externe IP-Adresse definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter**.
    
      - Wenn Sie IPv6-Adressen verwenden möchten, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter**.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff**, **Webkonferenzen** und **A/V-Konferenzen** die externen IPv4-Adressen der Edgeserver ein, und klicken Sie dann auf **Weiter**.
    
      - Wenn Sie IPv6-Adressen nutzen möchten und nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff**, **Webkonferenzen** und **A/V-Konferenzen** die externen IPv6-Adressen der Edgeserver ein. Klicken Sie anschließend auf **Weiter**.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.

        
        </div>

12. Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv4-Adresse des A/V-Edgediensts** die öffentliche IPv4-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies muss die externe IP-Adresse des A/V-Edgediensts sein.

    
    </div>

13. Wenn Sie sich für die Verwendung der Netzwerkadressenübersetzung und IPv6-Adressen entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv6-Adresse des A/V-Edgediensts** die öffentliche IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies muss die externe IP-Adresse des A/V-Edgediensts sein.

    
    </div>

14. Wählen Sie in **Nächsten Hop definieren** unter **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Alternativ können Sie, wenn Ihre Bereitstellung einen Director umfasst, den Namen des Directors auswählen. Klicken Sie anschließend auf **Weiter**.

15. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

16. Klicken Sie auf **Fertig stellen**.

17. Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>So definieren Sie die Topologie für einen Edgeserverpool mit DNS-Lastenausgleich

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.

3.  Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die interne Verbindung des Edgepools an.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein. Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Verwenden Sie nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Lync-Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

        
        </div>
    
      - Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter**.

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriff verwenden möchten, aktivieren Sie lync Server 2013 Webkonferenzdienst-und a/V-Edgedienst das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund aktivieren (Port 5061)**. Klicken Sie auf **Weiter**.
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.

7.  Klicken Sie auf **Weiter**.

8.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
      - **IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
    Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.

9.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.

        
        </div>
    
      - Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.

10. Klicken Sie auf **Weiter**.

11. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**.

12. Führen Sie in **Interner FQDN und interne IP-Adresse** die folgenden Schritte aus:
    
      - Geben Sie entsprechend Ihren Anforderungen in **Interne IPv4-Adresse** die IPv4-Adresse bzw. in **Interne IPv6-Adresse** die IPv6-Adresse des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.
    
      - Geben Sie in **Interner FQDN** den FQDN des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.
        
        <div>
        

        > [!NOTE]  
        > Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver, Pools und Arrays nur Standardzeichen (A-Z, a-z, 0-9 und Bindestriche). Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt. Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.

        
        </div>

13. Klicken Sie auf **Weiter**.

14. Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie in **SIP-Zugriff** die externe IP-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.

15. Klicken Sie auf **Weiter**.

16. Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.

    
    </div>

17. Klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.

    
    </div>

18. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**, und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der zum Edgepool hinzugefügt werden soll.

19. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.

    
    </div>

20. Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IP-Adresse** die öffentliche IPv4- bzw. IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Dies muss die externe IP-Adresse des A/V-Edgeservers sein.

    
    </div>

21. Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter**.

22. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

23. Klicken Sie auf **Fertig stellen**.

24. Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>So definieren Sie die Topologie für einen Edgeserverpool mit Hardwaregerät zum Lastenausgleich

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.

3.  Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und wählen Sie dann **neuer Edge-Pool**aus.

4.  Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.

5.  Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **FQDN** den vollqualifizierten Domänennamen ein, den Sie für die interne Seite des Edgepools ausgewählt haben.
        
        <div>
        

        > [!IMPORTANT]  
        > Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein. Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Verwenden Sie nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Lync-Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

        
        </div>
    
    <!-- end list -->
    
      - Klicken Sie auf **Pool mit mehreren Computern**und dann auf **weiter**.

6.  Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:
    
      - Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst verwenden möchten, aktivieren Sie lync Server Webkonferenzdienst und A/V-Edgedienst das Kontrollkästchen **einen einzelnen FQDN & IP-Adresse verwenden** .
    
      - Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

        
        </div>
    
      - Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.

7.  Klicken Sie auf **Weiter**.

8.  Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:
    
      - **IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
      - **IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
      - **IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
    <div>
    

    > [!IMPORTANT]  
    > Aktivieren Sie <STRONG>nicht</STRONG> das Kontrollkästchen <STRONG>Die externe IP-Adresse des Edgepools wird von der Netzwerkadressenübersetzung übersetzt</STRONG>. Die Netzwerkadressenübersetzung wird bei Verwendung eines Hardwaregeräts zum Lastenausgleich nicht unterstützt.

    
    </div>

9.  Führen Sie in **Externe FQDNs** die folgenden Schritte aus:
    
      - Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.

        
        </div>
    
      - Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.
        
        <div>
        

        > [!NOTE]  
        > Dabei handelt es sich um die FQDNs der virtuellen IP-Adressen (VIP) für die öffentliche Seite des Pools.

        
        </div>

10. Klicken Sie auf **Weiter**.

11. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**.

12. Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den **SIP-Zugriff**, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.

13. Klicken Sie auf **Weiter**.

14. Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:
    
      - Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.
    
      - Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.

    
    </div>

15. Klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.

    
    </div>

16. Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**, und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der dem Edgepool hinzugefügt werden soll.

17. Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.

    
    </div>

18. Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter**.

19. Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.
    
    <div>
    

    > [!NOTE]  
    > Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.

    
    </div>

20. Klicken Sie auf **Fertig stellen**.

21. Veröffentlichen Sie die Topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

