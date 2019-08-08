---
title: Überprüfen der Legacyumgebung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vor der Bereitstellung von Skype for Business Server 2019 in einem Koexistenzmodus müssen Sie überprüfen, ob Legacy Dienste konfiguriert und gestartet wurden. Vor der Bereitstellungeines Skype for Business Server 2019-pilotpools ist es wichtig, die wichtigsten Dienste und Features zu identifizieren, die in ihrer Legacyumgebung vorhanden sind. Bevor Sie Microsoft Skype for Business Server 2019 xmpp in einem koexistenzstatus mit einer Legacy-XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die Legacy-XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welchen Verbundpartner die Legacy-XMPP-Konfiguration ist stützen.
ms.openlocfilehash: 4c648dbbadeca50c12eb6047958ef63066ed7a3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243775"
---
# <a name="verify-the-legacy-environment"></a>Überprüfen der Legacyumgebung

Vor der Bereitstellung von Skype for Business Server 2019 in einem Koexistenzmodus müssen Sie überprüfen, ob Legacy Dienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in ihrer Legacyumgebung vorhanden sind, bevor Sie einen Skype for Business Server 2019-Pilot Pool bereitstellen. Bevor Sie Microsoft Skype for Business Server 2019 xmpp in einem koexistenzstatus mit einer Legacy-XMPP-Bereitstellung bereitstellen, müssen Sie sicherstellen, dass die Legacy-XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welchen Partner das Legacy-XMPP die Konfiguration unterstützt. Die Überprüfung Ihrer Legacy Bereitstellung umfasst Folgendes:
  
- Überprüfen, ob die Legacy Dienste gestartet wurden
    
- Überprüfen der Topologie und der Benutzer
    
- Überprüfen der Einstellungen für den Verbund und den Edgeserver
    
- Überprüfen von XMPP-Diensten und Verbundpartnern
    
## <a name="verify-that-legacy-services-are-started"></a>Überprüfen, ob Legacy Dienste gestartet wurden

1. Navigieren Sie vom Legacy-Front-End-Server zum Applet administrative Tools\Services.
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
     ![Liste der Dienste, die auf dem Front-End-Server ausgeführt werden](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Überprüfen der Legacy Topologie in der Skype for Business Server-Systemsteuerung

1. Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Wählen Sie **Topologie**aus. Überprüfen Sie, ob die verschiedenen Server in Ihrer Legacy Bereitstellung aufgelistet sind.
    
     ![Seite "System Steuerungs Topologie"](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Überprüfen von Legacy Benutzern in der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.
    
3. Überprüfen Sie, ob die Spalte des **registrierungspools** auf den Legacy Pool für jeden aufgelisteten Benutzer verweist. 
    
     ![Control Panel-Auflistung der Benutzer](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Überprüfen von Legacy Edge-und Federation-Einstellungen

1. Starten Sie den Topologie-Generator.
    
2. Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**.
    
3. Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.
    
4. Erweitern Sie den Knoten Legacy Installationen, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
5. Wählen Sie den Websiteknoten aus, und überprüfen Sie, ob ein **Standort Verbund-Routen Zuordnungs** Wert festgesetzt ist. 
    
     ![Topologie-Generator, Website Verbund Route](../media/migration_lyncserver_w14_federation.jpg)
  
6. Wählen Sie den Standard Edition-Server oder Enterprise Edition-Front-End-Pool aus. Ermitteln Sie, ob ein Edge-Pool für Medien unter **Zuordnungen**konfiguriert wurde. 
    
     ![Topologie-Generator mit Servern und Pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Wählen Sie den Edge-Pool aus, und ermitteln Sie, ob unterhalb des nächsten Hop- **Auswahlbereichs**ein nächster Hop-Pool konfiguriert ist.
    
     ![Topologie-Generator, Auswahl des nächsten Hops](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern

1. Navigieren Sie vom Legacy-XMPP-Server zum Administrator Tools\Services-Applet.
    
2. Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewayserver gestartet wurde. 
    
     ![Office Communications Server-XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

