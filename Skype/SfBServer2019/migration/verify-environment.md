---
title: Überprüfen der legacy-Umgebung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Müssen Sie vor der Bereitstellung von Skype für Business Server 2019 zusammen, um sicherzustellen, dass legacy-Diensten konfiguriert und gestartet wurden. Es ist wichtig, identifizieren wichtige Dienste und Features, die in der vorgängerumgebung vor der Bereitstellung einer Skype für Business Server 2019 pilotpool vorhanden sind. Vor der Bereitstellung von Microsoft Skype für Business Server 2019 XMPP zusammen mit einer Vorversion XMPP-Bereitstellung, müssen Sie überprüfen, ob der Vorversion XMPP-Dienste gestartet und konfiguriert wurden, und Bestimmen der Verbundpartner die Vorversion XMPP-Konfiguration ist Sie unterstützen.
ms.openlocfilehash: d6e4585e127009117345d1220458196b5b461b6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030427"
---
# <a name="verify-the-legacy-environment"></a>Überprüfen der Vorversionen Umgebung

Müssen Sie vor der Bereitstellung von Skype für Business Server 2019 zusammen, um sicherzustellen, dass legacy-Diensten konfiguriert und gestartet wurden. Es ist wichtig, identifizieren wichtige Dienste und Features, die in der Vorversion Umgebung vor der Bereitstellung einer Skype für Business Server 2019 pilotpool vorhanden sind. Vor der Bereitstellung von Microsoft Skype für Business Server 2019 XMPP zusammen mit einer Vorversion XMPP-Bereitstellung, müssen Sie sicherstellen, dass die Vorversion XMPP-Dienste gestartet und konfiguriert wurden, und Bestimmen der Partner die Vorversion XMPP federated Konfiguration wird unterstützt. Überprüfen der Bereitstellung die Vorgängerversion umfasst Folgendes:
  
- Sicherstellen, dass die legacy-Dienste gestartet wurden
    
- Überprüfen der Topologie und Benutzer
    
- Überprüfen der Partnerverbund- und edgeservereinstellungen
    
- Überprüfen der XMPP-Dienste und Verbundpartner
    
## <a name="verify-that-legacy-services-are-started"></a>Stellen Sie sicher, dass legacy-Dienste gestartet wurden

1. Navigieren Sie aus der Vorversion Front-End-Server zum Applet verwaltungstools\dienste.
    
2. Stellen Sie sicher, dass die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
     ![Liste der Dienste, die auf Front-End-Server ausgeführt werden.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Überprüfen der vorversionstopologie in Skype Business Server-Systemsteuerung

1. Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.
    
2. Öffnen Sie die Skype Business Server-Systemsteuerung.
    
3. Wählen Sie **Topologie**aus. Stellen Sie sicher, dass die verschiedenen Server in Ihrer Bereitstellung der Vorversion aufgeführt sind.
    
     ![Topologieseite in der Systemsteuerung steuern](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Überprüfen von legacybenutzern in Skype Business Server-Systemsteuerung

1. Öffnen Sie die Skype Business Server-Systemsteuerung.
    
2. Wählen Sie **Benutzer**aus, und klicken Sie dann auf **Suchen**.
    
3. Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** auf den Pool der Vorgängerversion für jeden aufgeführten Benutzer zeigt. 
    
     ![Systemsteuerung Auflisten von Benutzern](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Überprüfen Sie die Einstellungen für legacy Edge und Verbund

1. Starten Sie Topologie-Generator.
    
2. Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus.
    
3. Wählen Sie einen Dateinamen ein, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.
    
4. Erweitern Sie den Knoten Vorversion installiert, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
5. Wählen Sie den Websiteknoten, und stellen Sie sicher, dass ein **Zuweisung der partnerverbundroute Route** Wert festgelegt ist. 
    
     ![Topologie-Generator Partnerverbundroute des Standorts](../media/migration_lyncserver_w14_federation.jpg)
  
6. Wählen Sie den Standard Edition-Server oder Enterprise Edition-Front-End-Pool aus. Bestimmen Sie, ob für Medien unter **Zuordnungen**ein edgepool konfiguriert wurde. 
    
     ![Topologie-Generator mit Servern und pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Wählen Sie den edgepool aus, und identifizieren Sie, ob unter **Auswahl für nächsten Hop**ein nächster hoppool konfiguriert ist.
    
     ![Topologie-Generator Auswahl für nächsten hop](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Legacy XMPP-Verbundpartner Konfiguration überprüfen

1. Die XMPP-vorversionsserver zum Applet verwaltungstools\dienste navigieren.
    
2. Stellen Sie sicher, dass der Office Communications Server-XMPP-Gateway-Dienst gestartet wird. 
    
     ![Office Communications Server-XMPP-Gatewaydienst](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

