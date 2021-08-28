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
ms.localizationpriority: medium
description: Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zu Ihrem Pilotpool müssen Sie von der Partnerverbundroute Ihrer früheren Edgeserverversionen zur Verbundroute Ihrer Skype for Business Server 2019-Edgeserver wechseln.
ms.openlocfilehash: f051321667e12a468df1186147f6fab1d7bbe5cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613404"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zu Ihrem Pilotpool müssen Sie von der Partnerverbundroute der Edgeserver Ihrer vorherigen Version zur Partnerverbundroute Ihrer Skype for Business Server 2019-Edgeserver wechseln.
  
Verwenden Sie die folgenden Verfahren, um die Partnerverbundroute und die Mediendatenverkehr-Route für eine Bereitstellung mit einem einzigen Standort vom Edgeserver und Director Ihrer vorherigen Version auf Ihren Skype for Business Server 2019-Edgeserver zu übertragen.
  
> [!IMPORTANT]
> Wenn Sie die Partnerverbundroute und die Mediendatenverkehrroute ändern, müssen Sie Wartungsausfallzeiten für die Edgeserver der Skype for Business Server 2019 und der früheren Version planen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf. 
  
> [!IMPORTANT]
> Wenn Ihr Legacy-Edgeserver für die Verwendung desselben FQDN für den Zugriffs-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt. Wenn die älteren Edgedienste so konfiguriert sind, dass sie denselben FQDN verwenden, müssen Sie zuerst alle Ihre Benutzer migrieren und dann den Edgeserver der vorherigen Versionen außer Betrieb nehmen, bevor Sie den Partnerverbund auf dem Skype for Business Server 2019-Edgeserver aktivieren. 
  
> [!IMPORTANT]
> Wenn Ihr XMPP-Partnerverbund über einen Skype for Business Server 2019-Edgeserver weitergeleitet wird, können Benutzer der vorherigen Version erst dann mit dem XMPP-Verbundpartner kommunizieren, wenn alle Benutzer zu Skype for Business Server 2019 verschoben wurden, XMPP-Richtlinien und -Zertifikate konfiguriert wurden, der XMPP-Verbundpartner am Skype for Business Server 2019 konfiguriert wurde und schließlich die DNS-Einträge aktualisiert wurden. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>So entfernen Sie die Legacyverbundzuordnung aus Skype for Business Server 2019-Websites

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 die vorhandene Topologie im Topologie-Generator. 
    
2. Navigieren Sie im linken Bereich zum Websiteknoten, der sich direkt unter **Skype for Business Server** befindet.
    
3. Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus. 
    
5. Deaktivieren Sie unter **Standortverbundroutenzuweisung** das Kontrollkästchen **SIP-Partnerverbund aktivieren,** um die Partnerverbundroute über die Legacyumgebung zu deaktivieren. 
  
6. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
7. Wählen Sie im **Topologie-Generator** den oberen Knoten **Skype for Business Server** aus.
    
8. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.
    
9. Klicken Sie auf **"Weiter",** um den Veröffentlichungsprozess abzuschließen, und klicken Sie dann auf **"Fertig stellen",** wenn der Veröffentlichungsprozess abgeschlossen ist. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1. Navigieren Sie im linken Bereich zum Legacyinstallationsknoten und dann zum **Edgepoolknoten.** 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Deaktivieren Sie das **Kontrollkästchen "Partnerverbund für diesen Edgepool aktivieren" (Port 5061),** und wählen Sie **"OK"** aus, um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.
    
6. Nach Abschluss des Veröffentlichungs-Assistenten klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass der Partnerverbund für den älteren Edgeserver im Topologie-Generator deaktiviert ist.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>So konfigurieren Sie Zertifikate auf dem Legacy-Edgeserver

1. Exportieren Sie das externe Zugriffsproxyzertifikat mit dem privaten Schlüssel aus dem älteren Edgeserver. 
    
2. Importieren Sie auf dem Skype for Business Server 2019-Edgeserver das externe Zertifikat des Zugriffsproxys aus dem vorherigen Schritt.
    
3. Weisen Sie das externe Zertifikat des Zugriffsproxys der externen Skype for Business Server 2019-Schnittstelle des Edgeservers zu.
    
4. Das interne Schnittstellenzertifikat des Skype for Business Server 2019-Edgeservers sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>So ändern Sie die Partnerverbundroute der vorherigen Version so, dass Skype for Business Server 2019-Edgeserver verwendet wird

1. Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum **Knoten "Edgepools".** 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich **Allgemein** aus. 
    
4. Aktivieren Sie das Kontrollkästchen zum Aktivieren des **Partnerverbunds für diesen Edgepool (Port 5061),** und klicken Sie dann auf **OK,** um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.
    
6. Nach Abschluss des Veröffentlichungs-Assistenten klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen. 
    
7. Stellen Sie sicher, dass **der Partnerverbund (Port 5061)** im Topologie-Generator auf **"Aktiviert"** festgelegt ist.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>So aktualisieren Sie den nächsten Hop für Skype for Business Server 2019-Edgeserververbund

1. Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum **Knoten "Edgepools".** 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**. 
    
3. Wählen Sie auf der Seite **"Allgemein"** unter **"Nächster Hop"** in der Dropdownliste den Pool Skype for Business Server 2019 aus.
  
4. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
5. Wählen Sie im **Topologie-Generator** den oberen Knoten **Skype for Business Server** aus. 
    
6. Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>So konfigurieren Sie Skype for Business Server ausgehenden Medienpfad des Edgeservers 2019

1. Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Pool unter **Standard Edition Front-End-Servern** oder **Enterprise Edition Front-End-Pools.**
    
2. Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.
    
3. Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**. 
  
4. Wählen Sie im Dropdownfeld den edgeserver Skype for Business Server 2019 aus.
    
5. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>So aktivieren Sie Skype for Business Server 2019-Edgeserververbund

1. Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum **Knoten "Edgepools".** 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**. 
    
    > [!NOTE]
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten. 
  
3. Überprüfen Sie auf der Seite **"Allgemein",** ob das **Kontrollkästchen "Partnerverbund für diesen Edgepool aktivieren" (Port 5061)** aktiviert ist. 
  
4. Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen. 
    
5. Navigieren Sie zum Websiteknoten. 
    
6. Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.
    
7. Klicken Sie im linken Bereich auf **Partnerverbundroute**.
    
8. Wählen Sie unter **Standortverbundroutenzuweisung** **SIP-Partnerverbund aktivieren** aus, und wählen Sie dann in der Liste den aufgeführten Skype for Business Server 2019-Edgeserver aus. 
  
9. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
     Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1. Wählen Sie im **Topologie-Generator** den oberen Knoten **Skype for Business Server** aus. 
    
2. Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab. 
    
3. Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    
    > [!NOTE]
    > Möglicherweise wird die folgende Meldung angezeigt: **Warnung: Die Topologie enthält mehr als einen Partner-Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver gleichzeitig bereitstellen möchten (d. h. kein Migrationsszenario), überprüfen Sie, ob alle Verbundpartner Skype for Business Server verwenden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag alle Partnerverbund-aktivierten Edgeserver auflistet.** Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>So konfigurieren Sie Skype for Business Server 2019-Edgeserver

1. Stellen Sie alle Skype for Business Server 2019-Edgeserver online. 
    
2. Aktualisieren Sie die Regeln für das Routing externer Firewalls oder die Einstellungen für den Hardwarelastenausgleich, um SIP-Datenverkehr für externen Zugriff (in der Regel Port 443) und Partnerverbund (in der Regel Port 5061) an den Skype for Business Server 2019-Edgeserver anstelle des Legacy-Edgeservers zu senden.
    
    > [!NOTE]
    > Wenn Sie nicht über ein Hardwaregerät zum Lastenausgleich verfügen, müssen Sie den DNS A-Eintrag für den Partnerverbund aktualisieren, um den neuen Skype for Business Server Access Edge-Server aufzulösen. Um dies mit minimalen Unterbrechungen zu erreichen, reduzieren Sie den TLL-Wert für den externen Skype for Business Server Zugriffs-Edge-FQDN, sodass beim Aktualisieren von DNS auf die neue Skype for Business Server Zugriffs-Edge, Partnerverbund und Remotezugriff schnell aktualisiert werden. 
  
3. Beenden Sie die **Skype for Business Server Zugriffs-Edge** von jedem Edgeservercomputer aus. 
    
4. Öffnen Sie auf jedem Edgeservercomputer der Vorversion das **Dienst-Applet** aus den **Verwaltungstools.**
    
5. Suchen Sie in der Dienstliste **nach Skype for Business Server Access Edge**.
    
6. Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden. 
    
7. Legen Sie als Starttyp **Deaktiviert** fest. 
    
8. Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen. 
    

