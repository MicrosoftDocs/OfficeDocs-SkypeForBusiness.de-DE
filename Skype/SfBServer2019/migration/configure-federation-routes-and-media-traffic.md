---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verbund bezeichnet eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zum pilotpool müssen Sie für den Übergang von der partnerverbundroute Ihrer früherer Versionen Edge-Servern auf die partnerverbundroute von Ihrer Skype für Business Server 2019 Edge-Server.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880228"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

Verbund bezeichnet eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zum pilotpool müssen Sie für den Übergang von der partnerverbundroute des Edge-Server der Vorversion auf die partnerverbundroute von Ihrer Skype für Business Server 2019 Edge-Server.
  
Verwenden Sie die folgenden Verfahren, um die partnerverbundroute und die mediendatenverkehrsroute aus der vorherigen Version Edge-Server und Director auf Ihre Skype für Business Server 2019 Edge-Server für die Bereitstellung mit einem einzigen Standort umzustellen.
  
> [!IMPORTANT]
> Ändern die partnerverbundroute und die mediendatenverkehrsroute erfordert, dass Sie Ausfallzeiten Wartung für die Skype für Business Server 2019 und die vorherige Version Edge-Servern planen. Dieser Übergangsprozess für die gesamte bedeutet auch, dass federated Zugriff für die Dauer des Ausfalls verfügbar sind. Sie sollten die Downtime für einen Zeitraum planen, wenn Sie eine minimale Benutzeraktivität erwarten. Sie sollten auch über ausreichende Benachrichtigung für die Endbenutzer angeben. Planen Sie entsprechend für diese Ausfall und Festlegen der entsprechenden erwartet innerhalb Ihrer Organisation. 
  
> [!IMPORTANT]
> Wenn Ihrem älteren Edge-Server, zum Verwenden von des FQDN für Zugriffs-edgedienst, Webkonferenz-edgedienst und A konfiguriert ist / V-Edgeserver die Verfahren in diesem Abschnitt werden nicht unterstützt. Wenn die legacy-Edge-Diensten für die Verwendung von des FQDN konfiguriert sind, müssen Sie zuerst alle Ihre Benutzer migrieren dann außer Betrieb nehmen die früheren Versionen Edge-Server, bevor Sie auf die Skype-Verbund für Business Server 2019 Edge-Server aktivieren. 
  
> [!IMPORTANT]
> Wenn Sie über einen Skype XMPP-Verbund für Business Server 2019 Edge-Server weitergeleitet wird, Benutzer auf die vorherige Version werden nicht mit den XMPP-Verbundpartner zu kommunizieren, bis alle Benutzer zu Skype für Business Server 2019, XMPP-Richtlinien verschoben wurden und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner auf Skype für Business Server 2019 konfiguriert wurde und, schließlich die DNS-Einträge wurden aktualisiert. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Um die partnerverbundzuordnung der Vorversion aus Skype für Business Server 2019 Websites zu entfernen.

1. Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server die bestehende Topologie im Topologie-Generator. 
    
2. Navigieren Sie im linken Bereich zum Standortknoten, die sich direkt unterhalb **Skype für Business Server**befindet.
    
3. Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **partnerverbundroute**aus. 
    
5. Deaktivieren Sie das Kontrollkästchen **SIP-Partnerverbund aktivieren** , um die partnerverbundroute über die legacy-Umgebung zu deaktivieren, klicken Sie unter **Zuweisung der partnerverbundroute Route**. 
  
6. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
7. Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein.
    
8. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.
    
9. Klicken Sie auf **Weiter** , um die Veröffentlichung abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsvorgang abgeschlossen ist. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie die Edgeserver der Vorversion als nicht-Partnerverbund-Edgeserver

1. Navigieren Sie im linken Bereich auf den Knoten legacy installieren und dann auf den Knoten **Edge-Pools** . 
    
2. Maustaste auf den Edge-Server, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Deaktivieren Sie das Kontrollkästchen **Partnerverbund für diesen edgepool (Port 5061) aktivieren** , und wählen Sie **OK** , um die Seite zu schließen. 
  
5. Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen**aus, und klicken Sie dann auf **Weiter**.
    
6. Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass im Topologie-Generator-Verbund für Edgeserver der Vorversion deaktiviert ist.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>So konfigurieren Sie Zertifikate auf dem Edgeserver der Vorversion

1. Exportieren Sie das externe zugriffsproxyzertifikat, mit dem privaten Schlüssel, aus dem legacy-Edge-Server. 
    
2. Auf der Skype für Business Server 2019 Edge-Server und importieren die Zugriffsproxy externe Zertifikat aus dem vorherigen Schritt.
    
3. Weisen Sie das externe zugriffsproxyzertifikat der Skype für Business Server 2019 externe Schnittstelle des Edgeservers.
    
4. Das interne schnittstellenzertifikat des der Skype für Business Server 2019 Edge-Server sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>So ändern Sie die vorherige Version partnerverbundroute die Verwendung Skype für Business Server 2019 Edge-Server verwenden

1. Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** . 
    
2. Maustaste auf den Edge-Server, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Aktivieren Sie das Kontrollkästchen für **Partnerverbund für diesen edgepool (Port 5061) aktivieren**, und klicken Sie dann auf **OK** , um die Seite zu schließen. 
  
5. Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen**aus, und klicken Sie dann auf **Weiter**.
    
6. Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass **Partnerverbund (Port 5061)** **aktiviert** im Topologie-Generator ist.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>So aktualisieren Sie Skype für Business Server 2019 Edge-Server den nächsten partnerverbundhop

1. Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** . 
    
2. Erweitern Sie den Knoten rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**. 
    
3. Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**aus der Dropdown Liste der Skype für Business Server 2019 Pool.
  
4. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
5. Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein. 
    
6. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** und schließen Sie den Assistenten ab. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>So konfigurieren Sie Skype für ausgehenden Medienpfad Business Server 2019 Edge-Server

1. Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**aus.
    
2. Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **edgepool zuordnen (für Medienkomponenten)** . 
  
4. Wählen Sie aus dem Dropdown-Feld die Skype für Business Server 2019 Edge-Server.
    
5. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>So aktivieren Sie Skype für den Verbund Business Server 2019 Edge-Server

1. Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** . 
    
2. Erweitern Sie den Knoten rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**. 
    
    > [!NOTE]
    > Verbund kann nur für einen einzelnen edgepool aktiviert werden. Wenn Sie mehrere edgepools haben, wählen Sie eine als der Föderationspartner Edge-Pool verwenden. 
  
3. Stellen Sie auf der Seite **Allgemein** sicher, dass das Kontrollkästchen **Partnerverbund für diesen edgepool (Port 5061) aktivieren** aktiviert ist. 
  
4. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
5. Navigieren Sie zum Standortknoten. 
    
6. Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
7. Klicken Sie im linken Bereich auf **partnerverbundroute**.
    
8. Klicken Sie unter **Zuweisung der partnerverbundroute Route**wählen Sie **SIP-Partnerverbund aktivieren**aus, und wählen Sie dann in der Liste der Skype für Business Server 2019 Edge-Server aufgeführt. 
  
9. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
     Führen Sie für Bereitstellungen mit mehreren Standorten dieses Verfahren an jedem Standort. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Edgeserver-konfigurationsänderungen

1. Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein. 
    
2. Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen** , und schließen Sie den Assistenten ab. 
    
3. Warten Sie Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt wurde.
    
    > [!NOTE]
    > Sie können die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als eine Federated Edge-Server. Dies kann vorkommen, während der Migration zu einer neueren Version des Produkts. In diesem Fall würde nur einen Edge-Server aktiv für den Verbund verwendet werden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den entsprechenden Edge-Server verweist. Wenn Sie mehrere Verbund Edge-Server bereitstellen möchten gleichzeitig aktiv (d. h., keinem Migrationsszenario), stellen Sie sicher, dass alle Verbundpartnern Skype für Business Server verwenden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag alle Edgeserver für den Verbund aktiviert sind.** Diese Warnung entspricht der Erwartung und kann ignoriert werden. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>So konfigurieren Sie Skype für Business Server 2019 Edge-Server

1. Schalten Sie alle die Skype online für Business Server 2019 Edge-Server. 
    
2. Aktualisieren der externen Firewall Routingregeln oder die Hardware Load Balancer Einstellungen zum Senden von SIP-Datenverkehr für den externen Zugriff (normalerweise port 443) und Verbund (normalerweise port 5061), der Skype für Business Server 2019 Edge-Server, anstatt Edgeserver der Vorversion.
    
    > [!NOTE]
    > Wenn Sie nicht über ein Hardwaregerät zum Lastenausgleich verfügen, müssen Sie den DNS-A-Eintrag für den Verbund zum Auflösen in die neue Skype für Business Server-Zugriffs-Edgeserver zu aktualisieren. Zu diesem Zweck mit minimaler Beeinträchtigung verringern Sie den Wert TLL für die externe Skype für Business Server Access Edge-FQDN, so, dass bei einer Aktualisierung DNS so zeigen Sie auf die neue Skype für Business Server-Zugriffsedge partnerverbunds und Remotezugriffs schnell aktualisiert werden. 
  
3. Beenden Sie die **Skype für Business Server-Zugriffsedge** auf jedem Computer mit Edge-Server. 
    
4. Öffnen Sie auf jedem Computer mit älteren Edge-Server das Applet **Dienste** in **Verwaltung**.
    
5. Suchen Sie in der Dienstliste **Skype für Business Server-Zugriffsedge**.
    
6. Maustaste auf die Dienste, und wählen Sie dann auf **Beenden** , um den Dienst zu beenden. 
    
7. Legen Sie den Starttyp auf **deaktiviert**. 
    
8. Klicken Sie auf **OK** , um **das Eigenschaftenfenster** zu schließen. 
    

