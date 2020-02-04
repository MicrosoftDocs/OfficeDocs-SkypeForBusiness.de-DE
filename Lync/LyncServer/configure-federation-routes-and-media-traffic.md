---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren. Nachdem Sie die Migration zu Ihrem lync Server 2013-Pilot Pool durchgeführt haben, müssen Sie von der Verbund Route ihrer lync Server 2010-Edgeserver zur Föderations Route ihrer lync Server 2013-Edgeserver wechseln.

Führen Sie die folgenden Verfahren aus, um die Föderations Route und die Medien Verkehrsroute vom lync Server 2010-Edgeserver und-Director auf Ihren lync Server 2013-Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzustellen.

<div>


> [!IMPORTANT]  
> Für das Ändern der Route für die Verbund Route und den Mediendatenverkehr müssen Sie Wartungs Ausfälle für die Edgeserver lync Server 2013 und lync Server 2010 planen. Dieser gesamte Übergangsprozess bedeutet auch, dass der Verbundzugriff für die Dauer des Ausfalls nicht verfügbar ist. Sie sollten die Downtime für eine Zeit planen, wenn Sie eine minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie den Endbenutzern eine ausreichende Benachrichtigung senden. Planen Sie für diesen Ausfall entsprechend, und setzen Sie in Ihrer Organisation angemessene Erwartungen.



</div>

<div>


> [!IMPORTANT]  
> Wenn Ihr Legacy lync Server 2010-Edgeserver so konfiguriert ist, dass derselbe FQDN für den Access-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst verwendet wird, werden die Verfahren in diesem Abschnitt nicht unterstützt. Wenn die Legacy Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von lync Server 2010 zu lync Server 2013 migrieren und dann den lync Server 2010-Edgeserver außer Betrieb setzen, bevor Sie den Verbund auf dem lync Server 2013-Edgeserver aktivieren.



</div>

<div>


> [!IMPORTANT]  
> Wenn Ihr XMPP-Verbund über einen lync Server 2013-Edgeserver weitergeleitet wird, können Legacy-lync Server 2010-Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013 verschoben wurden, XMPP-Richtlinien und-Zertifikate wurden konfiguriert, wurde der XMPP-Verbundpartner auf lync Server 2013 konfiguriert, und zuletzt wurden die DNS-Einträge aktualisiert.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>So entfernen Sie die Legacy Verbund Zuordnung von lync Server 2013-Websites

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server die vorhandene Topologie im Topologie-Generator.

2.  Navigieren Sie im linken Bereich zu dem Websiteknoten, der sich direkt unter **lync Server**befindet.

3.  Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich **Föderations Route**aus.

5.  Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen **SIP-Verbund aktivieren** , um die Verbund Route über die Legacy-lync Server 2010-Umgebung zu deaktivieren.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"")

6.  Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.

7.  Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem obersten Knoten aus.

8.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.

9.  Klicken Sie auf **weiter** , um den Veröffentlichungsvorgang abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsvorgang abgeschlossen ist.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Legacy-Edgeserver als nicht-Föderations-Edgeserver

1.  Navigieren Sie im linken Bereich zum Knoten **lync Server 2010** und dann zum Knoten Edge- **Pools** .

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Wählen Sie im linken Bereich die Option **Allgemein** aus.

4.  Deaktivieren Sie das Kontrollkästchen Eintrag **Föderation für diesen Edge-Pool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen.
    
    ![Eigenschaften bearbeiten, allgemein, deaktivieren Föderation aktivieren](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, deaktivieren Föderation aktivieren")

5.  Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.

6.  Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.

7.  Überprüfen Sie, ob der Verbund für den Legacy-Edgeserver deaktiviert ist.
    
    ![Topologie-Generator, Edge-Pool, Verbund deaktiviert](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topologie-Generator, Edge-Pool, Verbund deaktiviert")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>So konfigurieren Sie Zertifikate auf dem lync Server 2010-Edgeserver

1.  Exportieren Sie das Proxy Zertifikat für den externen Zugriff mit dem privaten Schlüssel vom Legacy lync Server 2010-Edgeserver.

2.  Importieren Sie auf dem lync Server 2013-Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zertifikat des Zugriffsproxys zur externen lync Server 2013-Schnittstelle des Edgeserver zu.

4.  Das interne Schnittstellen Zertifikat des lync Server 2013-Edge-Servers sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>So ändern Sie die lync Server 2010-Verbund Route zur Verwendung des lync Server 2013 Edge-Servers

1.  Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **lync Server 2013** und dann zum Knoten Edge- **Pools** .

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Wählen Sie im linken Bereich die Option **Allgemein** aus.

4.  Aktivieren Sie den Kontrollkästchen Eintrag für **enable Federation for this Edge Pool (Port 5061)** , und klicken Sie dann auf **OK** , um die Seite zu schließen.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")

5.  Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.

6.  Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.

7.  Überprüfen Sie, ob der **Verbund (Port 5061)** auf **aktiviert**festgesetzt ist.
    
    ![Topologie-Generator, Edge-Pool, Verbund aktiviert](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topologie-Generator, Edge-Pool, Verbund aktiviert")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>So aktualisieren Sie den nächsten Hop von lync Server 2013 Edge Server Federation

1.  Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **lync Server 2013** und dann zum Knoten Edge- **Pools** .

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Wählen Sie auf der Seite **Allgemein** unter Auswahl für den **nächsten Hop**in der Dropdownliste den lync Server 2013-Pool aus.
    
    ![Dialogfeld ' Eigenschaften bearbeiten ', Seite ' nächster Hop '](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', Seite ' nächster Hop '")

4.  Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.

5.  Wählen Sie im **Topologie-Generator**den **lync-Server** mit dem obersten Knoten aus.

6.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>So konfigurieren Sie den ausgehenden Medienpfad von lync Server 2013 Edge Server

1.  Navigieren Sie vom Topologie-Generator im linken Bereich zu dem **lync Server 2013** -Knoten, und klicken Sie dann auf den Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** .
    
    ![Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools")

4.  Wählen Sie im Dropdownfeld den lync Server 2013-Edgeserver aus.

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>So aktivieren Sie den lync Server 2013-Edgeserver-Verbund

1.  Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **lync Server 2013** und dann zum Knoten Edge- **Pools** .

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
    <div>
    

    > [!NOTE]  
    > Der Verbund kann nur für einen einzelnen Edge-Pool aktiviert werden. Wenn Sie über mehrere Edge-Pools verfügen, wählen Sie eine aus, die Sie als Föderations-Edge-Pool verwenden möchten.

    
    </div>

3.  Überprüfen Sie auf der Seite **Allgemein** , ob die Einstellung **Föderation für diesen Edge-Pool aktivieren (Port 5061)** aktiviert ist.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")

4.  Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.

5.  Navigieren Sie als nächstes zum Websiteknoten.

6.  Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Klicken Sie im linken Bereich auf **Föderations Route**.

8.  Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann in der Liste den Eintrag lync Server 2013 Edge Server aus.
    
    ![Eigenschaften bearbeiten, Seite "Verbund Route"](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Eigenschaften bearbeiten, Seite "Verbund Route"")

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    Führen Sie für die Bereitstellung mehrerer Websites dieses Verfahren an jedem Standort aus.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Änderungen an Edge-Server-Konfigurationen

1.  Wählen Sie im **Topologie-Generator**den **lync-Server** mit dem obersten Knoten aus.

2.  Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung erfolgt.
    
    <div>
    

    > [!NOTE]  
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: die Topologie enthält mehr als einen Federated-Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet. Überprüfen Sie, ob der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Verbund-Edgeserver bereitstellen möchten, um gleichzeitig aktiv zu sein (also kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner lync Server verwenden. Überprüfen Sie, ob der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung wird erwartet und kann bedenkenlos ignoriert werden.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>So konfigurieren Sie den lync Server 2013-Edgeserver

1.  Bringen Sie alle lync Server 2013-Edgeserver online.

2.  Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwarelastenausgleich, um SIP-Datenverkehr für externen Zugriff (normalerweise Port 443) und Föderation (in der Regel Port 5061) an den lync Server 2013-Edgeserver anstelle des Legacy-Edgeserver zu senden.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht über ein Hardware-Lastenausgleichsmodul verfügen, müssen Sie den DNS-a-Eintrag für die Föderation aktualisieren, damit er auf den neuen lync Server Access-Edgeserver aufgelöst werden kann. Um dies bei minimaler Unterbrechung zu erreichen, verringern Sie den TLL-Wert für den externen lync Server Access-Edge-FQDN, sodass beim Aktualisieren von DNS auf den neuen lync Server Access-Edge die Föderation und der Remotezugriff schnell aktualisiert werden.

    
    </div>

3.  Beenden Sie als nächstes den **lync Server Access-Edge** von jedem Edgeserver-Computer.

4.  Öffnen Sie auf jedem Legacy-Edgeserver-Computer das Applet **Dienste** in den **Verwaltungs Tools**.

5.  Suchen Sie in der Liste Dienste nach **lync Server Access Edge**.

6.  Klicken Sie mit der rechten Maustaste auf den Namen der Dienste, und wählen Sie dann **Beenden** aus, um den Dienst zu beenden.

7.  Setzen Sie den Starttyp auf **disabled**.

8.  Klicken Sie auf **OK** , um das **Eigenschaften** Fenster zu schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

