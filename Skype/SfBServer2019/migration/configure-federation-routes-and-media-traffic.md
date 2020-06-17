---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nachdem Sie zu Ihrem Pilot Pool migriert haben, müssen Sie von der Verbund Route ihrer Vorgängerversionen-Edgeserver zur Verbund Route Ihrer Skype for Business Server 2019-Edgeserver wechseln.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754035"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nachdem Sie zu Ihrem Pilot Pool migriert haben, müssen Sie von der Verbund Route der Edgeserver ihrer Vorgängerversion zur Verbund Route Ihrer Skype for Business Server 2019-Edgeserver wechseln.
  
Verwenden Sie die folgenden Verfahren, um die partnerverbundroute und die Mediendaten Verkehrsroute von der Edgeserver und dem Director der vorherigen Version auf die Skype for Business Server 2019-Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzustellen.
  
> [!IMPORTANT]
> Für das Ändern der Route für partnerverbundroute und Mediendatenverkehr ist es erforderlich, dass Sie Wartungs Ausfälle für die Edgeserver von Skype for Business Server 2019 und früheren Versionen planen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf. 
  
> [!IMPORTANT]
> Wenn Ihr Legacy Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt. Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer migrieren und dann die vorherigen Versionen Edgeserver vor dem Aktivieren des Verbund im Skype for Business Server 2019 Edgeserver außer Betrieb nehmen. 
  
> [!IMPORTANT]
> Wenn Ihr XMPP-Verbund über eine Skype for Business Server 2019 Edgeserver weitergeleitet wird, können Benutzer der vorherigen Version nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer auf Skype for Business Server 2019 verschoben wurden, XMPP-Richtlinien und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner wurde für Skype for Business Server 2019 konfiguriert. und schließlich wurden die DNS-Einträge aktualisiert. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>So entfernen Sie die Legacy-Verbund Zuordnung von Skype for Business Server 2019-Websites

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 die vorhandene Topologie im Topologie-Generator. 
    
2. Navigieren Sie im linken Bereich zum Websiteknoten, der sich direkt unterhalb **Skype for Business Server**befindet.
    
3. Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus. 
    
5. Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über die Legacyumgebung zu deaktivieren. 
  
6. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
7. Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.
    
8. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.
    
9. Klicken Sie auf **weiter** , um den Veröffentlichungsprozess abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsprozess abgeschlossen ist. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1. Navigieren Sie im linken Bereich zum Knoten Legacy Installation und dann zum Knoten Edge- **Pools** . 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Deaktivieren Sie das Kontrollkästchen Partner **Verbund für diese Edgepool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.
    
6. Nach Abschluss des Veröffentlichungs-Assistenten**** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass der Verbund für den Legacy-Edgeserver im Topologie-Generator deaktiviert ist.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>So konfigurieren Sie Zertifikate für die Legacy Edgeserver

1. Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy Edgeserver. 
    
2. Importieren Sie im Skype for Business Server 2019 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.
    
3. Weisen Sie das externe Zertifikat des Zugriffsproxys der externen Skype for Business Server 2019-Schnittstelle des Edgeserver zu.
    
4. Das interne Schnittstellen Zertifikat des Skype for Business Server 2019 Edgeserver sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>So ändern Sie die partnerverbundroute der Vorgängerversion Skype for Business Server 2019 Edgeserver

1. Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** . 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Aktivieren Sie das Kontrollkästchen Partner **Verbund für diesen Edgepool aktivieren (Port 5061)**, und klicken Sie dann auf **OK** , um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.
    
6. Nach Abschluss des Veröffentlichungs-Assistenten**** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass der **Verbund (Port 5061)** im Topologie-Generator auf **aktiviert** festgelegt ist.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>So aktualisieren Sie den nächsten Hop Skype for Business Server 2019 Edgeserver-Partnerverbund

1. Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** . 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**. 
    
3. Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**in der Dropdownliste den Skype for Business Server Pool 2019 aus.
  
4. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
5. Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus. 
    
6. Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>So konfigurieren Sie Skype for Business Server 2019 Edgeserver ausgehenden Medienpfad

1. Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.
    
2. Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.
    
3. Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**. 
  
4. Wählen Sie im Dropdownfeld die Skype for Business Server 2019 Edgeserver aus.
    
5. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>So aktivieren Sie Skype for Business Server 2019 Edgeserver Partnerverbund

1. Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** . 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**. 
    
    > [!NOTE]
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten. 
  
3. Stellen Sie auf der Seite **Allgemein** sicher, dass das Kontrollkästchen Partner **Verbund für diese Edgepool aktivieren (Port 5061)** aktiviert ist. 
  
4. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
5. Navigieren Sie zum Knoten Website. 
    
6. Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.
    
7. Klicken Sie im linken Bereich auf **Partnerverbundroute**.
    
8. Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten Skype for Business Server 2019 Edgeserver aus. 
  
9. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
     Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1. Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus. 
    
2. Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab. 
    
3. Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    
    > [!NOTE]
    > Möglicherweise wird die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als einen Verbund Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts passieren. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet werden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf die richtige Edgeserver verweist. Wenn Sie mehrere Verbund Edgeserver bereitstellen möchten, gleichzeitig aktiv zu sein (also kein Migrationsszenario), überprüfen Sie, ob alle Verbundpartner Skype for Business Server verwenden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.** Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>So konfigurieren Sie Skype for Business Server 2019 Edgeserver

1. Alle Skype for Business Server 2019-Edgeserver online schalten. 
    
2. Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an den Skype for Business Server 2019 Edgeserver anstelle des Legacy Edgeserver zu senden.
    
    > [!NOTE]
    > Wenn Sie nicht über ein Hardwaregerät zum Lastenausgleich verfügen, müssen Sie den DNS-a-Eintrag für den Verbund so aktualisieren, dass er auf den neuen Skype for Business Server Access-Edgeserver aufgelöst wird. Um dies bei minimaler Unterbrechung zu erreichen, reduzieren Sie den TLL-Wert für den externen Skype for Business Server Zugriffs-Edge-FQDN, sodass beim Aktualisieren von DNS auf den neuen Skype for Business Server Zugriffs-Edge der Verbund und der Remotezugriff schnell aktualisiert werden. 
  
3. Beenden Sie die **Skype for Business Server Zugriffs Kante** für jeden Edgeserver Computer. 
    
4. Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.
    
5. Suchen Sie in der Liste Dienste nach **Skype for Business Server Zugriffs-Edge**.
    
6. Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden. 
    
7. Legen Sie als Starttyp **Deaktiviert** fest. 
    
8. Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen. 
    

