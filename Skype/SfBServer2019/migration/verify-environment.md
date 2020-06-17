---
title: Überprüfen der Legacyumgebung
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
description: Bevor Sie Skype for Business Server 2019 in einem koexistenzstatus bereitstellen, müssen Sie sicherstellen, dass ältere Dienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features, die in ihrer Vorgänger Umgebung vorhanden sind, vor der Bereitstellungeines Skype for Business Server 2019-pilotpools zu identifizieren. Bevor Sie Microsoft Skype for Business Server 2019 XMPP im koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die vorhandenen XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751677"
---
# <a name="verify-the-legacy-environment"></a>Überprüfen der Vorgänger Umgebung

Bevor Sie Skype for Business Server 2019 in einem koexistenzstatus bereitstellen, müssen Sie sicherstellen, dass ältere Dienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features in ihrer Legacyumgebung vor der Bereitstellungeines Skype for Business Server 2019-pilotpools zu identifizieren. Bevor Sie Microsoft Skype for Business Server 2019 XMPP im koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie sicherstellen, dass die vorhandenen XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird. Die Überprüfung Ihrer Legacy-Bereitstellung umfasst Folgendes:
  
- Überprüfen, ob die Legacy Dienste gestartet wurden
    
- Überprüfen der Topologie und der Benutzer
    
- Überprüfen der Einstellungen für den Verbund und den Edgeserver
    
- Überprüfen der XMPP-Dienste und Verbundpartner
    
## <a name="verify-that-legacy-services-are-started"></a>Überprüfen, ob ältere Dienste gestartet wurden

1. Navigieren Sie in der Legacy Front-End-Server zum Applet für administrative verwaltungstools\dienste..
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
     ![Liste der auf Front-End-Server ausgeführten Dienste](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Überprüfen der Legacy Topologie in Skype for Business Server Systemsteuerung

1. Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Wählen Sie **Topologie** aus. Stellen Sie sicher, dass die verschiedenen Server in Ihrer Legacy Bereitstellung aufgelistet sind.
    
     ![System Steuerungs Topologie (Seite)](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Überprüfen von älteren Benutzern in Skype for Business Server Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.
    
3. Stellen Sie sicher, dass die Spalte **Registrierungspool** für jeden aufgelisteten Benutzer auf den Legacy Pool verweist. 
    
     ![Systemsteuerung, die Benutzer auflistet](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Überprüfen der Legacy-Edge-und Verbund Einstellungen

1. Starten Sie den Topologie-Generator.
    
2. Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.
    
3. Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem Dateityp default. tbxml.
    
4. Erweitern Sie den Knoten Legacy installs, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
5. Wählen Sie den Knoten Website aus, und stellen Sie sicher, dass ein **Standort Verbund-Routen Zuordnungs** Wert festgelegt ist. 
    
     ![Topologie-Generator, Standort Verbund Route](../media/migration_lyncserver_w14_federation.jpg)
  
6. Wählen Sie den Front-End-Pool Standard Edition-Server oder Enterprise Edition aus. Bestimmen Sie, ob ein Edgepool für Medien unterhalb von **Zuordnungen**konfiguriert wurde. 
    
     ![Topologie-Generator mit Servern und Pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Wählen Sie die Edgepool aus, und bestimmen Sie, ob ein nächster Hop-Pool unterhalb der **nächsten Hop-Auswahl**konfiguriert ist.
    
     ![Topologie-Generator, Auswahl des nächsten Hops](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Überprüfen der Vorgänger Konfiguration für XMPP-Verbundpartner

1. Navigieren Sie auf dem XMPP-Vorversionsserver zum Applet Verwaltungstools\Dienste.
    
2. Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist. 
    
     ![Office Communications Server XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

