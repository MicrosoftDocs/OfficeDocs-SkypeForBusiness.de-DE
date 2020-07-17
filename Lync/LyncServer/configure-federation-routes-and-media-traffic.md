---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5e9b7ad3f08d9ebf129c478bbcf94bed7845ef1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nachdem Sie zu Ihrem lync Server 2013 Pilot-Pool migriert haben, müssen Sie von der Verbund Route ihrer lync Server 2010-Edgeserver zur Verbund Route ihrer lync Server 2013 Edgeserver wechseln.

Führen Sie die folgenden Verfahren aus, um die partnerverbundroute und die Mediendaten Verkehrsroute von Ihrem lync Server 2010 Edgeserver und Director zu Ihrem lync Server 2013 Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzuleiten.

<div>


> [!IMPORTANT]  
> Zum Ändern der Route für partnerverbundroute und Mediendatenverkehr müssen Sie Wartungs Ausfälle für die lync Server 2013-und lync Server 2010-Edgeserver planen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.



</div>

<div>


> [!IMPORTANT]  
> Wenn Ihr Legacy lync Server 2010 Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt. Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von lync Server 2010 zu lync Server 2013 migrieren und dann die lync Server 2010 Edgeserver vor dem Aktivieren des partnerverbunds auf dem lync Server 2013 Edgeserver außer Betrieb nehmen.



</div>

<div>


> [!IMPORTANT]  
> Wenn Ihr XMPP-Verbund über eine lync Server 2013 Edgeserver weitergeleitet wird, können Legacy lync Server 2010 Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013 verschoben wurden, XMPP-Richtlinien und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner für lync Server 2013 konfiguriert wurde und schließlich die DNS-Einträge aktualisiert wurden.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>So entfernen Sie die Partnerverbundzuordnung der Vorversion von Lync Server 2013-Standorten

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server die vorhandene Topologie im Topologie-Generator.

2.  Navigieren Sie im linken Bereich zum Knoten "Standort", der sich direkt unter dem **Lync Server** befindet.

3.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich **Partnerverbundroute** aus.

5.  Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über die Legacy lync Server 2010 Umgebung zu deaktivieren.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"")

6.  Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.

7.  Wählen Sie im Topologie-Generator**** den obersten Knoten **Lync Server** aus.

8.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.

9.  Klicken Sie auf **Weiter**, um den Veröffentlichungsvorgang zu beenden, und klicken Sie dann auf **Fertig stellen**, wenn der Veröffentlichungsvorgang abgeschlossen ist.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1.  Navigieren Sie im linken Bereich zum Knoten **Lync Server 2010** und dann zum Knoten **Edgepools**.

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.

3.  Wählen Sie im linken Bereich **Allgemein** aus.

4.  Deaktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**, und wählen Sie **OK** aus, um die Seite zu schließen.
    
    ![Eigenschaften bearbeiten, allgemein, Clear Federation aktivieren](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Clear Federation aktivieren")

5.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.

6.  Nach Abschluss des Veröffentlichungs-Assistenten**** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

7.  Stellen Sie sicher, dass der Partnerverbund für die Edgeserver der Vorversion deaktiviert ist.
    
    ![Topologie-Generator, Edgepool, Verbund deaktiviert](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topologie-Generator, Edgepool, Verbund deaktiviert")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>So konfigurieren Sie Zertifikate auf dem Lync Server 2010-Edgeserver

1.  Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy lync Server 2010 Edgeserver.

2.  Importieren Sie im lync Server 2013 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zertifikat des Zugriffsproxys der externen lync Server 2013-Schnittstelle des Edgeserver zu.

4.  Das interne Schnittstellen Zertifikat des lync Server 2013 Edgeserver sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>So legen Sie für die Lync Server 2010-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013 ** und dann zum Knoten **Edgepools**.

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.

3.  Wählen Sie im linken Bereich **Allgemein** aus.

4.  Aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**, und klicken Sie dann auf **OK**, um die Seite zu schließen.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")

5.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.

6.  Nach Abschluss des Veröffentlichungs-Assistenten**** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

7.  Stellen Sie sicher, dass die Option **Partnerverbund (Port 5061)** auf **Aktiviert** festgelegt wurde.
    
    ![Topologie-Generator, Edgepool, Verbund aktiviert](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topologie-Generator, Edgepool, Verbund aktiviert")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>So aktualisieren Sie den nächsten Partnerverbundhop für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013 ** und dann zum Knoten **Edgepools**.

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.

3.  Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**in der Dropdownliste den lync Server 2013 Pool aus.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Nächster Abschnitt"](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Nächster Abschnitt"")

4.  Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.

5.  Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server** aus.

6.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **lync Server 2013** und dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**.
    
    ![Eigenschaften bearbeiten, allgemein, zuordnen Edgepool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, zuordnen Edgepool")

4.  Wählen Sie im Dropdownfeld die lync Server 2013 Edgeserver aus.

5.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013 ** und dann zum Knoten **Edgepools**.

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.
    
    <div>
    

    > [!NOTE]  
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten.

    
    </div>

3.  Stellen Sie auf der Seite **Allgemein** sicher, dass die Einstellung **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aktiviert wurde.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")

4.  Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.

5.  Navigieren Sie anschließend zum Knoten Standort.

6.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.

7.  Klicken Sie im linken Bereich auf **Partnerverbundroute**.

8.  Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten lync Server 2013 Edgeserver aus.
    
    ![Eigenschaften bearbeiten, Verbund Route (Seite)](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Eigenschaften bearbeiten, Verbund Route (Seite)")

9.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1.  Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server** aus.

2.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    
    <div>
    

    > [!NOTE]  
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration zu einer höheren Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Lync Server verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>So konfigurieren Sie Lync Server 2013-Edgeserver

1.  Alle lync Server 2013-Edgeserver online schalten.

2.  Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an die lync Server 2013 Edgeserver anstelle des Legacy Edgeserver zu senden.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie kein Hardwaregerät zum Lastenausgleich zur Verfügung haben, müssen Sie den DNS-A-Eintrag für den Partnerverbund aktualisieren, um das Problem für den neuen Lync Server-Zugriffs-Edgeserver zu lösen. Damit es mit geringstmöglicher Störung abgeschlossen werden kann, sollte Sie den TLL-Wert für den externen FQDN des Lync Server-Zugriffsedge reduzieren, sodass der Partnerverbund und der Remotezugriff schnell aktualisiert werden können, wenn die DNS aktualisiert wird, damit auf den neuen Lync Server-Zugriffsedge verwiesen werden kann.

    
    </div>

3.  Beenden Sie als nächstes die **lync Server Zugriffs Kante** für jeden Edgeserver Computer.

4.  Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.

5.  Suchen Sie in der Liste mit den Diensten nach **Lync Server-Zugriffsedge**.

6.  Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden.

7.  Legen Sie als Starttyp **Deaktiviert** fest.

8.  Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

