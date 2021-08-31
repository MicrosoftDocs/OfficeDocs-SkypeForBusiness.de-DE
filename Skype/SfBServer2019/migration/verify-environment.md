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
ms.localizationpriority: medium
description: Bevor Sie Skype for Business Server 2019 in einem Koexistenzstatus bereitstellen, müssen Sie überprüfen, ob Legacydienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in Ihrer älteren Umgebung vorhanden sind, bevor Sie einen Skype for Business Server 2019-Pilotpool bereitstellen. Bevor Sie Microsoft Skype for Business Server 2019 XMPP in einem Koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die älteren XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird.
ms.openlocfilehash: 208b508eb6b2b5c62da51aa6317cde6e2a95bbb7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727744"
---
# <a name="verify-the-legacy-environment"></a>Überprüfen der Legacyumgebung

Bevor Sie Skype for Business Server 2019 in einem Koexistenzstatus bereitstellen, müssen Sie überprüfen, ob Legacydienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in Ihrer älteren Umgebung vorhanden sind, bevor Sie einen Skype for Business Server 2019-Pilotpool bereitstellen. Bevor Sie Microsoft Skype for Business Server 2019 XMPP in einem Koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die älteren XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird. Die Überprüfung Der Legacybereitstellung umfasst Folgendes:
  
- Überprüfen, ob die Legacydienste gestartet wurden
    
- Überprüfen der Topologie und der Benutzer
    
- Überprüfen der Verbund- und Edgeservereinstellungen
    
- Überprüfen von XMPP-Diensten und Verbundpartnern
    
## <a name="verify-that-legacy-services-are-started"></a>Überprüfen, ob Legacydienste gestartet werden

1. Navigieren Sie vom älteren Front-End-Server zum Applet "Administrative Tools\Services".
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
     ![Liste der Auf dem Front-End-Server ausgeführten Dienste.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Überprüfen der Legacytopologie in Skype for Business Server Systemsteuerung

1. Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.
    
2. Öffnen Sie die Skype for Business Server Systemsteuerung.
    
3. Wählen Sie **Topologie** aus. Stellen Sie sicher, dass die verschiedenen Server in Ihrer Legacybereitstellung aufgeführt sind.
    
     ![Seite "Systemsteuerungstopologie".](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Überprüfen von älteren Benutzern in Skype for Business Server Systemsteuerung

1. Öffnen Sie die Skype for Business Server Systemsteuerung.
    
2. Wählen Sie **"Benutzer"** aus, und klicken Sie dann auf **"Suchen".**
    
3. Stellen Sie sicher, dass die Spalte **"Registrierungsstellenpool"** für jeden aufgeführten Benutzer auf den Legacypool verweist. 
    
     ![Systemsteuerung, die Benutzer auflistet.](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Überprüfen der älteren Edge- und Verbundeinstellungen

1. Starten Sie den Topologie-Generator.
    
2. Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.
    
3. Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem Standardmäßigen TBXML-Dateityp.
    
4. Erweitern Sie den Legacyinstallationsknoten, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
5. Wählen Sie den Standortknoten aus, und stellen Sie sicher, dass ein **Standortverbund-Routenzuweisungswert** festgelegt ist. 
    
     ![Topologie-Generator, Standortverbundroute.](../media/migration_lyncserver_w14_federation.jpg)
  
6. Wählen Sie den Standard Edition Server oder Enterprise Edition Front-End-Pool aus. Bestimmen Sie, ob ein Edgepool für Medien unter **Zuordnungen** konfiguriert wurde. 
    
     ![Topologie-Generator mit Servern und Pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Wählen Sie den Edgepool aus, und identifizieren Sie, ob unter der Auswahl des nächsten Hops ein **Next-Hop-Pool** konfiguriert ist.
    
     ![Topologie-Generator, Auswahl des nächsten Hops.](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern

1. Navigieren Sie auf dem XMPP-Vorversionsserver zum Applet Verwaltungstools\Dienste.
    
2. Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist. 
    
     ![Office Communications Server-XMPP-Gatewaydienst.](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

