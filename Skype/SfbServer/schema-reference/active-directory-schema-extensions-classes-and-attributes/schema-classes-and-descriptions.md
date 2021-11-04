---
title: Schemaklassen und Beschreibungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: In diesem Abschnitt werden alle Schemaklassen beschrieben, die von Skype for Business Server verwendet werden.
ms.openlocfilehash: d7f05cd76074740e49f3972c97875e8993dd7b06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743261"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Schemaklassen und Beschreibungen in Skype for Business Server
 
In diesem Abschnitt werden alle Schemaklassen beschrieben, die von Skype for Business Server verwendet werden. 
  
## <a name="schema-classes-and-descriptions"></a>Schemaklassen und Beschreibungen

|**Klasse**|**Beschreibung**|**Kommentare**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange Unified Messaging (UM)-E-Mail-Empfänger.  <br/> |Diese Hilfsklasse wird für Exchange UM freigegeben.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Diese Klasse ist ein Container für mehrere Anwendungskontakte und enthält selbst keine Attribute.  <br/> |Neu in Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt für eine Instanz von Unified Communications-Anwendungsdiensten.  <br/> |Neu in Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Diese Klasse stellt eine Zuordnung aus einem bestimmten Pool zum Anwendungsdienst bereit.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Diese Hilfsklasse zu msRTCSIP-ApplicationServer enthält Attribute, die Einstellungen für Instanzen des Anwendungsdiensts darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (veraltet)  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf die Archivierung beziehen.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (veraltet)  <br/> |Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungsserver dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungsserver (z. B. ein Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist) aktiviert wird.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von Konferenzverzeichnissen und enthält selbst keine Attribute.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Generischer Dienststeuerungspunkt (Generic Service Control Point, SCP), um den Computer als Server anzugeben, auf dem Skype for Business Server ausgeführt wird.  <br/> |Neu in Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Diese Hilfsklasse enthält die Einstellungen für eine Skype for Business-Web-App Bank.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierung definieren.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Dieser Klassencontainer stellt einen einzelnen Access Edge-Dienst dar. Da ein Zugriffs-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden in der Regel keinen Active Directory Domain Services-Zugriff über das Umkreisnetzwerk zulassen, sind Instanzen des Zugriffs-Edgediensts nicht mit dem Active Directory-Netzwerk des Intranets verbunden. Somit werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das Vorhandensein jeder Instanz des Zugriffs-Edgediensts in AD DS manuell konfigurieren.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-MCU" enthält Attribute, die Einstellungen für Konferenzserver darstellen.  <br/> |Neu in Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-MediationServer" enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.  <br/> |Neu in Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-Server" enthält Attribute, die Einstellungen für SIP-Server darstellen.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf den Partnerverbund beziehen.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Diese Klasse enthält alle Einstellungen, die in einer Skype for Business Server Bereitstellung gelten.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (veraltet)  <br/> |Diese Klasse stellt eine einzelne Office Communications Server-Besprechungsrichtlinie dar.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Das lokale Einstellungsobjekt für die globale Topologie.  <br/> |Neu in Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Container mit Einstellungsobjekten für die globale Topologie.  <br/> |Neu in Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer Standortnormalisierungsregel dar.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Diese Klasse wird vom Konferenzzentralenanwendung erstellt und enthält Attribute, die zum Kategorisieren von Konferenztelefonnummern nach Region verwendet werden.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von Standortkontaktzuordnungen und enthält selbst keine Attribute.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Diese Klasse ist ein Container und stellt ein bestimmtes Standortprofil dar.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere Standortprofile und enthält selbst keine Attribute.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält selbst keine Attribute.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Diese Klasse stellt einen einzelnen Konferenzserver dar.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Diese Klasse enthält mehrere msRTCSIP-MCUFactory-Klassen und weist selbst keine Attribute auf.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Diese Klasse ist ein Container und stellt eine Zuordnungsinstanz für Konferenzserver für einen einzelnen Medientyp dar. Eine Instanz dieser Klasse wird erstellt, sobald der erste Konferenzserver für diesen spezifischen Typ und Hersteller aktiviert wird.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und der dazugehörigen Zuordnungsinstanz für Konferenzserver bereit.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt eines Vermittlungsservers.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (veraltet)  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Container zum Speichern der globalen Mobilitätseinstellungen.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen einzelnen Überwachungsserver darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (veraltet)  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer Least-Cost-Route zu einem Gateway oder einem Satz mehrerer Gateways dar. Diese Informationen werden von allen Enterprise-Pools oder Standard Edition-Servern verwendet, um ausgehende Gespräche möglichst kosteneffizient an das PSTN-Netzwerk weiterzuleiten.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere Least-Cost-Routen und enthält selbst keine Attribute.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-Policies (veraltet)  <br/> |Diese Klasse enthält mehrere Lync Server-Richtlinienklassen und hat selbst keine Attribute.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Diese Klasse stellt einen einzelnen Skype for Business Server Pool dar.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Diese Klasse enthält mehrere Skype for Business Server Pools und hat selbst keine Attribute.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Diese Klasse stellt den Dienststeuerungspunkt eines Pools dar. Das msRTCSIP-PrimaryHomeServer-Attribut von Benutzern in einem Pool zeigt auf eine Instanz dieser Klasse.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Container zum Speichern der globalen Anwesenheitseinstellungen.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die von den SIP-Registrierungsservern verwaltete Benutzereinstellungen darstellen.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (veraltet)  <br/> |Diese Klasse ist ein Container und stellt eine Instanz einer Telefonroutenverwendung dar. Eine Verwendungsklasse für Telefonrouten besteht aus einem Attribut- und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Beschreibungsfeld können Administratoren Hinweise zur Verwendung dieses Attributs in der Telefonroute angeben.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (veraltet)  <br/> |Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-RouteUsage" und weist selbst keine Attribute auf.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die den Umfang von Suchergebnissen begrenzen und steuern.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Diese Klasse stellt einen einzelnen Server dar, auf dem Skype for Business Server ausgeführt wird.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Diese Klasse enthält den Container für globale Einstellungen und msRTCSIP-Domain-Objekte.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedMCU" und weist selbst keine Attribute auf.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Diese Klasse enthält mehrere msRTCSIP-TrustedProxy-Klassen und weist selbst keine Attribute auf.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Diese Klasse ist ein Container und stellt einen Server dar, auf dem ein Proxyserver ausgeführt wird. Eine Instanz dieser Klasse wird erstellt, sobald ein neuer Proxyserver auf einem Computer aktiviert wird, der Mitglied von AD DS ist.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Diese Klasse ist ein Container und stellt einen vertrauenswürdigen Dienst dar, der unter Verwendung einer GRUU-Adresse (Globally Routable User Agent URI) routingfähig ist. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von Skype for Business Server als vertrauenswürdig eingestuft wird. Dieser vertrauenswürdige Server muss Mitglied einer Active Directory-Domäne sein.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Diese Klasse ist ein Container für mehrere GRUU-Server und enthält selbst keine Attribute.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedWebComponentServer" und weist selbst keine Attribute auf.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (veraltet)  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die Unified Communications betreffen.  <br/> |Veraltet in Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Diese Klasse enthält den Dienststeuerungspunkt für Internetinformationsdienste (Internet Information Services, IIS). Sie identifiziert einen Server als Webkomponentenserver.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Diese Klasse liefert eine Zuordnung zwischen einem bestimmten Pool und den Webkomponenten, die für diesen Pool verwendet werden.  <br/> |Neu in Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Diese Erweiterungsklasse zu "msRTCSIP-WebComponents" enthält Attribute, die Einstellungen für Webkomponenten darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
   

