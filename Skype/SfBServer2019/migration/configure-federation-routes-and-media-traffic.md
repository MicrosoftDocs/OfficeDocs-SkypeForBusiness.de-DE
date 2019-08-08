---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren. Nachdem Sie die Migration zu Ihrem Pilot Pool durchgeführt haben, müssen Sie von der Föderations Route ihrer Vorgängerversionen-Edgeserver zur Föderations Route Ihrer Skype for Business Server 2019 Edge-Server wechseln.
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239362"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren. Nachdem Sie die Migration zu Ihrem Pilot Pool durchgeführt haben, müssen Sie von der Föderations Route der Edgeserver Ihrer vorherigen Version zur Föderations Route Ihrer Skype for Business Server 2019 Edge-Server wechseln.
  
Führen Sie die folgenden Verfahren aus, um die Föderations Route und die Mediendaten Verkehrsroute vom Edgeserver und Director der vorherigen Version zu Ihrem Skype for Business Server 2019 Edge-Server für eine Bereitstellung mit einem einzelnen Standort zu wechseln.
  
> [!IMPORTANT]
> Für das Ändern der Route für die Föderations Route und den Mediendatenverkehr müssen Sie Wartungs Ausfälle für die Edgeserver von Skype for Business Server 2019 und früheren Versionen planen. Dieser gesamte Übergangsprozess bedeutet auch, dass der Verbundzugriff für die Dauer des Ausfalls nicht verfügbar ist. Sie sollten die Downtime für eine Zeit planen, wenn Sie eine minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie den Endbenutzern eine ausreichende Benachrichtigung senden. Planen Sie für diesen Ausfall entsprechend, und setzen Sie in Ihrer Organisation angemessene Erwartungen. 
  
> [!IMPORTANT]
> Wenn Ihr Legacy-Edgeserver für die Verwendung desselben FQDN für den Access-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt. Wenn die Legacy Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Benutzer migrieren und dann den Edgeserver für frühere Versionen außer Betrieb setzen, bevor Sie den Verbund auf dem Skype for Business Server 2019 Edge-Server aktivieren. 
  
> [!IMPORTANT]
> Wenn Ihr XMPP-Verbund über einen Skype for Business Server 2019 Edge-Server weitergeleitet wird, können Benutzer der vorherigen Version nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in Skype for Business Server 2019, XMPP-Richtlinien und Es wurden Zertifikate konfiguriert, der XMPP-Verbundpartner wurde in Skype for Business Server 2019 konfiguriert, und schließlich wurden die DNS-Einträge aktualisiert. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>So entfernen Sie die Legacy Federation Association von den Skype for Business Server 2019-Websites

1. Öffnen Sie auf dem Front-End-Server von Skype for Business Server 2019 die vorhandene Topologie im Topologie-Generator. 
    
2. Navigieren Sie im linken Bereich zum Websiteknoten, der sich direkt unter **Skype for Business Server**befindet.
    
3. Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
4. Wählen Sie im linken Bereich **Föderations Route**aus. 
    
5. Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen **SIP-Verbund aktivieren** , um die Föderations Route über die Legacyumgebung zu deaktivieren. 
  
6. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
7. Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus.
    
8. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.
    
9. Klicken Sie auf **weiter** , um den Veröffentlichungsvorgang abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsvorgang abgeschlossen ist. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Legacy-Edgeserver als nicht-Föderations-Edgeserver

1. Navigieren Sie im linken Bereich zum Legacy Installations Knoten und dann zum Knoten Edge- **Pools** . 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich die Option **Allgemein** aus. 
    
4. Deaktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.
    
6. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen. 
    
7. Überprüfen Sie, ob der Verbund für den Legacy-Edgeserver im Topologie-Generator deaktiviert ist.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>So konfigurieren Sie Zertifikate auf dem Legacy-Edgeserver

1. Exportieren Sie das Proxy Zertifikat für den externen Zugriff mit dem privaten Schlüssel vom Legacy-Edgeserver. 
    
2. Klicken Sie auf dem Skype for Business Server 2019-Edgeserver, und importieren Sie das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.
    
3. Weisen Sie das externe Zertifikat des Zugriffsproxys der externen Skype for Business Server 2019-Schnittstelle des Edge-Servers zu.
    
4. Das interne Schnittstellen Zertifikat des Skype for Business Server 2019 Edge-Servers sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>So ändern Sie die Föderations Route der vorherigen Version zur Verwendung von Skype for Business Server 2019 Edge Server

1. Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** . 
    
2. Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Wählen Sie im linken Bereich die Option **Allgemein** aus. 
    
4. Aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)**, und klicken Sie dann auf **OK** , um die Seite zu schließen. 
  
5. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.
    
6. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen. 
    
7. Überprüfen Sie, ob der **Verbund (Port 5061)** im Topologie-Generator auf **aktiviert** festgesetzt ist.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>So aktualisieren Sie den nächsten Hop von Skype for Business Server 2019 Edge Server Federation

1. Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** . 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**. 
    
3. Wählen Sie auf der Seite **Allgemein** unter **Auswahl des nächsten Hop**in der Dropdownliste den Skype for Business Server 2019-Pool aus.
  
4. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
5. Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus. 
    
6. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>So konfigurieren Sie den ausgehenden Medienpfad für Skype for Business Server 2019 Edge Server

1. Navigieren Sie im linken Bereich des Topologie-Generators zum **Skype for Business Server 2019** -Knoten, und klicken Sie dann auf den Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.
    
2. Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** . 
  
4. Wählen Sie im Dropdownfeld den Skype for Business Server 2019 Edge-Server aus.
    
5. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>So aktivieren Sie den Skype for Business Server 2019 Edge Server-Verbund

1. Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** . 
    
2. Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**. 
    
    > [!NOTE]
    > Der Verbund kann nur für einen einzelnen Edge-Pool aktiviert werden. Wenn Sie über mehrere Edge-Pools verfügen, wählen Sie eine aus, die Sie als Föderations-Edge-Pool verwenden möchten. 
  
3. Überprüfen Sie auf der Seite **Allgemein** , ob das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** aktiviert ist. 
  
4. Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen. 
    
5. Navigieren Sie zum Websiteknoten. 
    
6. Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
7. Klicken Sie im linken Bereich auf **Föderations Route**.
    
8. Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann in der Liste den Eintrag Skype for Business Server 2019 Edge Server aus. 
  
9. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen. 
    
     Führen Sie für die Bereitstellung mehrerer Websites dieses Verfahren an jedem Standort aus. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Änderungen an Edge-Server-Konfigurationen

1. Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus. 
    
2. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab. 
    
3. Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung erfolgt.
    
    > [!NOTE]
    > Möglicherweise wird die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als einen Federated Edge-Server. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet. Überprüfen Sie, ob der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Verbund-Edgeserver bereitstellen möchten, um gleichzeitig aktiv zu sein (also kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Skype for Business Server verwenden. Überprüfen Sie, ob der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.** Diese Warnung wird erwartet und kann bedenkenlos ignoriert werden. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>So konfigurieren Sie den Edge-Server für Skype for Business Server 2019

1. Bringen Sie alle Skype for Business Server 2019 Edge-Server online. 
    
2. Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardware-Lastenausgleichsmodul, um SIP-Datenverkehr für externen Zugriff (in der Regel Port 443) und Föderation (in der Regel Port 5061) an den Edgeserver von Skype for Business Server 2019 zu senden, statt auf den Legacy Edge-Server.
    
    > [!NOTE]
    > Wenn Sie nicht über ein Hardware-Lastenausgleichsmodul verfügen, müssen Sie den DNS-a-Eintrag für Federation aktualisieren, damit er auf den neuen Skype for Business Server Access-Edgeserver aufgelöst werden kann. Um dies bei minimaler Unterbrechung zu erreichen, sollten Sie den TLL-Wert für den externen Skype for Business Server Access Edge-FQDN reduzieren, damit die DNS-Aktualisierung so aktualisiert wird, dass Sie auf den neuen Skype for Business Server Access-Edge verweist, Föderation und RAS schnell aktualisiert werden. 
  
3. Beenden Sie den **Skype for Business Server Access-Edge** von jedem Edge-Server-Computer. 
    
4. Öffnen Sie auf jedem Legacy-Edgeserver-Computer das Applet **Dienste** in den **Verwaltungs Tools**.
    
5. Suchen Sie in der Liste "Dienste" **nach Skype for Business Server Access Edge**.
    
6. Klicken Sie mit der rechten Maustaste auf den Namen der Dienste, und wählen Sie dann **Beenden** aus, um den Dienst zu beenden. 
    
7. Setzen Sie den Starttyp auf **disabled**. 
    
8. Klicken Sie auf **OK** , um das **Eigenschaften** Fenster zu schließen. 
    

