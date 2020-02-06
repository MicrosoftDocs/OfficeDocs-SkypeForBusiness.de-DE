---
title: Schema Klassen und Beschreibungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: In diesem Abschnitt werden alle von Skype for Business Server verwendeten Schemaklassen beschrieben.
ms.openlocfilehash: 6cb67c47c20ecb9cc6af79e51ebc05c332fd0bf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815473"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Schema Klassen und Beschreibungen in Skype for Business Server
 
In diesem Abschnitt werden alle von Skype for Business Server verwendeten Schemaklassen beschrieben. 
  
## <a name="schema-classes-and-descriptions"></a>Schema Klassen und Beschreibungen

|**Klasse**|**Beschreibung**|**Anmerkungen**|
|:-----|:-----|:-----|
|E-Mail-Empfänger  <br/> |Exchange Unified Messaging (um)-e-Mail-Empfänger.  <br/> |Diese Auxiliary-Klasse wird für Exchange um freigegeben.  <br/> |
|Attribut msRTCSIP-ApplicationContacts  <br/> |Diese Klasse ist ein Container für mehrere Anwendungskontakte und enthält keine Attribute selbst.  <br/> |Neu in Microsoft Office Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-ApplicationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienst Kontrollpunkt für eine Instanz von Unified Communications Application Services (UCAS).  <br/> |Neu in Office Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-ApplicationServerService  <br/> |Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu seinem Anwendungsdienst bereit.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-ApplicationServerSettings  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-ApplicationServer enthält Attribute, die Einstellungen für Instanzen des Anwendungsdiensts darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-Archiv (veraltet)  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält alle Einstellungen im Zusammenhang mit der Archivierung.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-ArchivingServer (veraltet)  <br/> |Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungs Server dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungs Server aktiviert wird, beispielsweise einen Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-ConferenceDirectories  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von Konferenz Verzeichnissen und enthält keine Attribute selbst.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-ConferenceDirectory  <br/> |Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-ConnectionPoint  <br/> |Generic Service Control Point (SCP), um den Computer als einen Server anzugeben, auf dem Skype for Business Server ausgeführt wird.  <br/> |Neu in lync 2010.  <br/> |
|Attribut msRTCSIP-DefaultCWABank  <br/> |Diese Auxiliary-Klasse enthält die Einstellungen für eine Skype for Business Web App Bank.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-Domäne  <br/> |Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierungsstelle definieren.  <br/> |-  <br/> |
|Attribut msRTCSIP-EdgeProxy  <br/> |Dieser Klassencontainer stellt einen einzelnen Access-Edgedienst dar. Da ein Access-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden in der Regel keinen Zugriff auf Active Directory-Domänendienste aus dem Umkreisnetzwerk zulassen, sind Instanzen des Access-Edgedienst nicht dem Active Directory-Netzwerk des Intranets beigetreten. Daher werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das vorhanden sein jeder Instanz von Access Edge Service in AD DS manuell konfigurieren.  <br/> |-  <br/> |
|Attribut msRTCSIP-EnterpriseMCUSettings  <br/> |Diese Erweiterungsklasse für Attribut msRTCSIP-MCU enthält Attribute, die Einstellungen für Konferenzserver darstellen.  <br/> |Neu in Microsoft Office Communications Server 2007.  <br/> |
|Attribut msRTCSIP-EnterpriseMediationServerSettings  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-MediationServer enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.  <br/> |Neu in Office Communications Server 2007.  <br/> |
|Attribut msRTCSIP-EnterpriseServerSettings  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Server enthält Attribute, die Einstellungen für SIP-Server darstellen.  <br/> |-  <br/> |
|Attribut msRTCSIP-Federation  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält alle Einstellungen, die sich auf den Verbund beziehen.  <br/> |-  <br/> |
|Attribut msRTCSIP-Global Container  <br/> |Diese Klasse enthält alle Einstellungen, die in einer Skype for Business Server-Bereitstellung gelten.  <br/> |-  <br/> |
|Attribut msRTCSIP-GlobalUserPolicy (veraltet)  <br/> |Diese Klasse stellt eine einzelne Office Communications Server-Besprechungsrichtlinie dar.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-GlobalTopologySetting  <br/> |Das Setting-Objekt der lokalen globalen Topologie.  <br/> |Neu in lync Server 2010.  <br/> |
|Attribut msRTCSIP-GlobalTopologySettings  <br/> |Container, in dem globale Topologie-Einstellungsobjekte enthalten sind.  <br/> |Neu in lync Server 2010.  <br/> |
|Attribut msRTCSIP-LocalNormalization  <br/> |Diese Klasse ist ein Container, der eine Instanz einer Standort Normalisierungsregel darstellt.  <br/> |-  <br/> |
|Attribut msRTCSIP-LocationContactMapping  <br/> |Diese Klasse wird von der Conferencing Attendant-Anwendung erstellt und enthält Attribute, mit denen Konferenz Telefonnummern nach Regionen kategorisiert werden.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-LocationContactMappings  <br/> |Diese Klasse ist ein Container für mehrere Instanzen von Standortkontaktzuordnungen und enthält keine Attribute selbst.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-LocationProfile  <br/> |Diese Klasse ist ein Container, der ein bestimmtes Standortprofil darstellt.  <br/> |-  <br/> |
|Attribut msRTCSIP-LocationProfiles (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere Standortprofile und enthält keine Attribute selbst.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-LocalNormalizations (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält keine Attribute selbst.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-MCU  <br/> |Diese Klasse stellt einen einzelnen Konferenzserver dar.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-MCUFactories  <br/> |Diese Klasse enthält mehrere Attribut msRTCSIP-MCUFactory-Klassen und besitzt keine Attribute selbst.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-MCUFactory  <br/> |Bei dieser Klasse handelt es sich um einen Container, der eine Konferenz Server Factory für einen einzelnen Medientyp darstellt. Eine Instanz dieser Klasse wird erstellt, wenn der erste Konferenzserver für diesen bestimmten Typ und Lieferanten aktiviert ist.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-MCUFactoryService  <br/> |Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu seiner Konferenz Server Factory bereit.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-MediationServer  <br/> |Diese Klasse enthält den Eintrag für den Dienst Kontrollpunkt für einen Vermittlungs Server.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-Besprechung (veraltet)  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP – Mobilität  <br/> |Container, in dem die globalen Mobilitätseinstellungen gespeichert sind.  <br/> |-  <br/> |
|Attribut msRTCSIP-MonitoringServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen einzelnen Überwachungs Server darstellen.  <br/> |Neu in Communications Server 2007 R2.  <br/> |
|Attribut msRTCSIP-PhoneRoute (veraltet)  <br/> |Bei dieser Klasse handelt es sich um einen Container, der eine Instanz einer Least Cost-Route zu einem Gateway oder einer Gruppe von Gateways darstellt. Diese Informationen werden von allen Enterprise-Pools oder Servern mit Standard Edition verwendet, um ausgehende Anrufe auf die kostengünstigste Weise an das öffentlich geschaltete Telefonnetz (PSTN) weiterzuleiten.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-PhoneRoutes (veraltet)  <br/> |Diese Klasse ist ein Container für mehrere, kostengünstigste Routen und enthält keine Attribute selbst.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-Richtlinien (veraltet)  <br/> |Diese Klasse enthält mehrere lync Server-Richtlinien Klassen und hat keine Attribute selbst.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-Pool  <br/> |Diese Klasse stellt einen einzelnen Skype for Business-Server Pool dar.  <br/> |-  <br/> |
|Attribut msRTCSIP-Pools  <br/> |Diese Klasse enthält mehrere Skype for Business Server-Pools und hat keine Attribute selbst.  <br/> |-  <br/> |
|Attribut msRTCSIP-PoolService  <br/> |Diese Klasse stellt den Kontrollpunkt des Dienst Steuerelements pointservice eines Pools dar. Für Benutzer, die in einem Pool gehostet werden, wird Ihr Attribut msRTCSIP-PrimaryHomeServer-Attribut auf eine Instanz dieser Klasse verweisen.  <br/> |-  <br/> |
|Attribut msRTCSIP-Anwesenheitsinformationen  <br/> |Container, in dem die globalen Anwesenheitseinstellungen gespeichert sind.  <br/> |-  <br/> |
|Attribut msRTCSIP-Registrar  <br/> |Diese Hilfsklasse für Attribut msRTCSIP-Global Container enthält Attribute, die Benutzereinstellungen darstellen, die von den SIP-Registrierungs Servern verwaltet werden.  <br/> |-  <br/> |
|Attribut msRTCSIP-RouteUsage (veraltet)  <br/> |Bei dieser Klasse handelt es sich um einen Container, der eine Instanz einer Telefonrouten Verwendung darstellt. Eine Telefonroute-Nutzungsklasse besteht aus einem Attributfeld und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Feld Beschreibung können Administratoren die Verwendung dieses Attributs auf der Telefonroute beschreiben.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-RouteUsages (veraltet)  <br/> |Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-RouteUsage-Klasse und hat keine Attribute selbst.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-Suche  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die den Umfang der Suchergebnisse einschränken und steuern.  <br/> |-  <br/> |
|Attribut msRTCSIP-Server  <br/> |Diese Klasse steht für einen einzelnen Server, auf dem Skype for Business Server ausgeführt wird.  <br/> |-  <br/> |
|Attribut msRTCSIP-Service  <br/> |Diese Klasse enthält den Container für globale Einstellungen und Attribut msRTCSIP-Domänenobjekte.  <br/> |-  <br/> |
|Attribut msRTCSIP-TrustedMCU  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedMCUs  <br/> |Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-TrustedMCU-Klasse und hat keine Attribute selbst.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedProxies  <br/> |Diese Klasse enthält mehrere Attribut msRTCSIP-TrustedProxy-Klassen und enthält keine Attribute selbst.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedProxy  <br/> |Diese Klasse ist ein Container, der einen Server mit Proxy Server darstellt. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Proxy Server auf einem Computer aktiviert wird, der mit AD DS verbunden ist.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedServer  <br/> |Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.  <br/> |-  <br/> |
|Attribut msRTCSIP-TrustedService  <br/> |Diese Klasse ist ein Container, der einen vertrauenswürdigen Dienst darstellt, der mithilfe einer Global routingfähigen Benutzer-Agent-URI-Adresse (GRUU) geroutet werden kann. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von Skype for Business Server als vertrauenswürdig eingestuft wird. Dieser vertrauenswürdige Server muss einer Active Directory-Domäne angehören.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedServices  <br/> |Diese Klasse ist ein Container für mehrere GRUU-Server und enthält keine Attribute selbst.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedWebComponentsServer  <br/> |Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-TrustedWebComponentsServers  <br/> |Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-TrustedWebComponentServer-Klasse und hat keine Attribute selbst.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-UnifiedCommunications (veraltet)  <br/> |Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die sich auf Unified Communications beziehen.  <br/> |In lync Server 2010 veraltet.  <br/> |
|Attribut msRTCSIP-Webkomponenten  <br/> |Diese Klasse enthält den pointservice-Kontrollpunkt für Dienst Steuerelemente für Internet Information Server (IIS). Es identifiziert einen Server als Web Components-Server.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-WebComponentsService  <br/> |Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu den Webkomponenten bereit, die vom Pool verwendet werden.  <br/> |Neu in Communications Server 2007.  <br/> |
|Attribut msRTCSIP-WebComponentSettings  <br/> |Diese zusätzliche Klasse für Attribut msRTCSIP-Webkomponenten enthält Attribute, die Einstellungen für Webkomponenten darstellen.  <br/> |Neu in Communications Server 2007.  <br/> |
   

