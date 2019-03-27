---
title: Schemaklassen und Beschreibungen in Skype für Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: In diesem Abschnitt werden alle von Skype für Business Server verwendeten Schemaklassen beschrieben.
ms.openlocfilehash: 0bb34a93ec23df67d19026e82e29769e0aeb9ab2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926560"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Schemaklassen und Beschreibungen in Skype für Business Server
 
In diesem Abschnitt werden alle von Skype für Business Server verwendeten Schemaklassen beschrieben. 
  
## <a name="schema-classes-and-descriptions"></a>Schemaklassen und Beschreibungen

|**Klasse**|**Beschreibung**|**Anmerkungen**|
|:-----|:-----|:-----|
|E-Mail-Empfänger  <br/> |Exchange Unified Messaging (UM) e-Mail-Empfänger.  <br/> |Diese Erweiterungsklasse wird gemeinsam mit Exchange UM verwendet.  <br/> |
|MsRTCSIP-ApplicationContacts  <br/> |Diese Klasse ist ein Container für mehrere anwendungskontakte und ist nicht selbst keine Attribute.  <br/> |Neu in Microsoft Office Communications Server 2007 R2.  <br/> |
|MsRTCSIP-ApplicationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt für eine Instanz von Unified Communications Application Services (UCAS).  <br/> |Neu in Office Communications Server 2007 R2.  <br/> |
|MsRTCSIP-ApplicationServerService  <br/> |Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und seine Anwendungsdienst.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-ApplicationServerSettings  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-ApplicationServer enthält Attribute, die Einstellungen für Instanzen des Anwendungsdiensts.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-Archive (veraltet)  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält alle Einstellungen im Zusammenhang mit der Archivierung.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-ArchivingServer (veraltet)  <br/> |Diese Klasse stellt einen einzelnen Instant messaging-Archivierungsserver dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als instant messaging Archivierungsserver, aktiviert ist, wie ein Computer mit Instant Messaging-Archivierungsdienst installiert.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-ConferenceDirectories  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von konferenzverzeichnissen und ist nicht selbst keine Attribute.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-ConferenceDirectory  <br/> |Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-ConnectionPoint  <br/> |Generischer Dienststeuerungspunkt zur Angabe des Computers als Server mit Skype für Business Server (SCP).  <br/> |Neu in Lync 2010.  <br/> |
|MsRTCSIP-DefaultCWABank  <br/> |Diese Erweiterungsklasse enthält die Einstellungen für einen Skype für Business Web App-Bank.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-Domain  <br/> |Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierung zu definieren.  <br/> |-  <br/> |
|MsRTCSIP-EdgeProxy  <br/> |Dieser klassencontainer stellt einen einzelnen Zugriffs-Edgeservers-Dienst. Da Zugriffs-edgediensts im Umkreisnetzwerk bereitgestellt wird und Kunden in der Regel nicht Zugriff aus dem Umkreisnetzwerk Active Directory Domain Services zulassen, werden Instanzen des Zugriffs-edgedienst mit Active Directory-Netzwerk im Intranet nicht verbunden. Aus diesem Grund werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das Vorhandensein jeder einzelnen Instanz der Zugriffs-edgedienst in AD DS manuell konfigurieren.  <br/> |-  <br/> |
|MsRTCSIP-EnterpriseMCUSettings  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-MCU enthält Attribute, die Einstellungen für Konferenzserver darstellen.  <br/> |Neu in Microsoft Office communicationsserver 2007.  <br/> |
|MsRTCSIP-EnterpriseMediationServerSettings  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-MediationServer enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.  <br/> |Neu in Office communicationsserver 2007.  <br/> |
|MsRTCSIP-EnterpriseServerSettings  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-Server enthält Attribute, die Einstellungen für SIP-Server darstellen.  <br/> |-  <br/> |
|MsRTCSIP-Verbund  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält alle Einstellungen im Zusammenhang mit den Verbund.  <br/> |-  <br/> |
|MsRTCSIP-GlobalContainer  <br/> |Diese Klasse enthält alle Einstellungen, die innerhalb einer Skype für Business Server-Bereitstellung angewendet werden.  <br/> |-  <br/> |
|MsRTCSIP-GlobalUserPolicy (veraltet)  <br/> |Diese Klasse stellt eine einzelne Office Communications Server-besprechungsrichtlinie dar.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-GlobalTopologySetting  <br/> |Das Einstellungsobjekt für lokale globale Topologie.  <br/> |Neu in Lync Server 2010.  <br/> |
|MsRTCSIP-GlobalTopologySettings  <br/> |Container zum Einstellungsobjekten globale Topologie.  <br/> |Neu in Lync Server 2010.  <br/> |
|MsRTCSIP-LocalNormalization  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer standortnormalisierungsregel dar.  <br/> |-  <br/> |
|MsRTCSIP-LocationContactMapping  <br/> |Diese Klasse wird von der Konferenzzentrale-Anwendung erstellt und enthält Attribute, die zum Kategorisieren konferenztelefonnummern nach Region verwendet.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-LocationContactMappings  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von standortkontaktzuordnungen und ist nicht selbst keine Attribute.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-LocationProfile  <br/> |Diese Klasse ist ein Container und stellt Sie ein bestimmtes Standortprofil dar.  <br/> |-  <br/> |
|MsRTCSIP-LocationProfiles (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere Standortprofile und ist nicht selbst keine Attribute.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-LocalNormalizations (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und ist nicht selbst keine Attribute.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-MCU  <br/> |Diese Klasse stellt einen einzelnen Konferenzserver dar.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-MCUFactories  <br/> |Diese Klasse enthält mehrere MsRTCSIP-MCUFactory-Klassen und selbst keine Attribute.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-MCUFactory  <br/> |Diese Klasse ist ein Container und stellt ein Konferenzserver für einen einzelnen Medientyp dar. Eine Instanz dieser Klasse wird erstellt, wenn der erste Konferenzserver für diesen spezifischen Typ und Hersteller aktiviert wird.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-MCUFactoryService  <br/> |Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und seine für Konferenzserver bereit.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-MediationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt eines Vermittlungsservers.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-Meeting (veraltet)  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält Attribute, die konfigurierbare besprechungseinstellungen darstellen.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-Mobilität  <br/> |Container zum Speichern der globalen mobilitätseinstellungen.  <br/> |-  <br/> |
|MsRTCSIP-MonitoringServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen einzelnen Monitoring Server darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|MsRTCSIP-PhoneRoute (veraltet)  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer least-Cost-Route zu einem Gateway oder Satz mehrerer Gateways dar. Diese Informationen werden von allen Enterprise-Pools oder Standard Edition-Servern verwendet, ausgehende Anrufe bei dem öffentlichen Telefonfestnetz (PSTN) in die möglichst kosteneffizient weitergeleitet.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-PhoneRoutes (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere, least-Cost-Routen und ist nicht selbst keine Attribute.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-Policies (veraltet)  <br/> |Diese Klasse enthält mehrere Lync Server-richtlinienklassen und ist nicht selbst keine Attribute.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-Pool  <br/> |Diese Klasse stellt einen einzelnen Skype für Business Server-Pool dar.  <br/> |-  <br/> |
|MsRTCSIP-Pools  <br/> |Diese Klasse enthält mehrere Skype für Business Server-Pools und ist nicht selbst keine Attribute.  <br/> |-  <br/> |
|MsRTCSIP-Pooldienstes  <br/> |Diese Klasse stellt den Pointservice Steuerelement Dienststeuerungspunkt eines Pools dar. In einem Pool gehostete Benutzer haben ihre MsRTCSIP-PrimaryHomeServer-Attribut zeigen auf eine Instanz dieser Klasse.  <br/> |-  <br/> |
|MsRTCSIP-Anwesenheit  <br/> |Container zum Speichern der globalen anwesenheitseinstellungen.  <br/> |-  <br/> |
|MsRTCSIP-Registrierung  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält Attribute, die von den SIP-Registrierungsservern verwaltete benutzereinstellungen darstellen.  <br/> |-  <br/> |
|MsRTCSIP-RouteUsage (veraltet)  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer telefonroutenverwendung dar. Eine Verwendungsklasse besteht aus einem Attribut- und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Beschreibungsfeld können Administratoren die Verwendung dieses Attributs in der Telefonroute beschreiben.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-RouteUsages (veraltet)  <br/> |Diese Klasse enthält mehrere Instanzen der MsRTCSIP-RouteUsage-Klasse und wird nicht selbst keine Attribute.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-Suche  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält Attribute, die den Umfang von Suchergebnissen begrenzen und steuern.  <br/> |-  <br/> |
|MsRTCSIP-Server  <br/> |Diese Klasse stellt einen einzelnen Server mit Skype für Business Server dar.  <br/> |-  <br/> |
|MsRTCSIP-Dienst  <br/> |Diese Klasse enthält den Container für globale Einstellungen und MsRTCSIP-Domain-Objekte.  <br/> |-  <br/> |
|MsRTCSIP-TrustedMCU  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedMCUs  <br/> |Diese Klasse enthält mehrere Instanzen der MsRTCSIP-TrustedMCU-Klasse und wird nicht selbst keine Attribute.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedProxies  <br/> |Diese Klasse enthält mehrere MsRTCSIP-TrustedProxy-Klassen und ist nicht selbst keine Attribute.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedProxy  <br/> |Diese Klasse ist ein Container und stellt einen Server Proxyserver ausgeführt wird. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Proxyserver auf einem Computer zu aktivieren, die in AD DS beigetreten ist.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.  <br/> |-  <br/> |
|MsRTCSIP-ein TrustedService  <br/> |Diese Klasse ist ein Container und stellt einen vertrauenswürdigen Dienst, der eine Route über eine Adresse Global routingfähige User Agent URI (GRUU) ist. Eine Instanz dieser Klasse wird erstellt, wenn Sie ein neuer Server, der Skype für Business Server vertraut aktiviert ist. Dieser vertrauenswürdige Server mit einer Active Directory-Domäne verknüpft werden muss.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedServices  <br/> |Diese Klasse ist ein Container für mehrere GRUU-Server und ist nicht selbst keine Attribute.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedWebComponentsServer  <br/> |Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-TrustedWebComponentsServers  <br/> |Diese Klasse enthält mehrere Instanzen der MsRTCSIP-TrustedWebComponentServer-Klasse und wird nicht selbst keine Attribute.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-UnifiedCommunications (veraltet)  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-GlobalContainer enthält Attribute, die im Zusammenhang mit unified Communications.  <br/> |In Lync Server 2010 veraltet.  <br/> |
|MsRTCSIP-WebComponents  <br/> |Diese Klasse enthält den Dienststeuerungspunkt eines Steuerelements Pointservice für Internet Information Server (IIS). Einen Server identifiziert als eines webkomponentenservers.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-WebComponentsService  <br/> |Diese Klasse liefert eine Zuordnung zwischen einem bestimmten Pool und den Webkomponenten, die der Pool verwendet werden.  <br/> |Neu in communicationsserver 2007.  <br/> |
|MsRTCSIP-WebComponentSettings  <br/> |Diese Erweiterungsklasse zu MsRTCSIP-WebComponents enthält Attribute, die Einstellungen für Webkomponenten darstellen.  <br/> |Neu in communicationsserver 2007.  <br/> |
   

