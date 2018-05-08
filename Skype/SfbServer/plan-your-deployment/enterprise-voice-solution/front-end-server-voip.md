---
title: VoIP-Komponenten der Front-End-Server für Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Informationen Sie zu den Enterprise-VoIP-Komponenten, die sich auf Front-End-Servern in Skype für Business Server, einschließlich Übersetzungsdienst und verschiedenen Routingkomponenten befinden.
ms.openlocfilehash: a95b437128f7ddb8dd78462d3a8443e972dd75bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a>VoIP-Komponenten der Front-End-Server für Skype for Business Server 2015
 
Informationen Sie zu den Enterprise-VoIP-Komponenten, die sich auf Front-End-Servern in Skype für Business Server, einschließlich Übersetzungsdienst und verschiedenen Routingkomponenten befinden.
  
Die VoIP-Komponenten auf Front-End-Servern lauten wie folgt:
  
- Übersetzungsdienst
    
- Eingangsroutingkomponente
    
- Ausgangsroutingkomponente
    
- Routingkomponente für Exchange UM
    
- Komponente für das clusterübergreifende Routing
    
- [Vermittlungsserverkomponente in Skype für Business Server 2015](mediation-server.md)
    
## <a name="translation-service"></a>Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.
  
## <a name="inbound-routing-component"></a>Eingangsroutingkomponente

Die Eingangsroutingkomponente verarbeitet eingehende Anrufe im Wesentlichen anhand der Einstellungen, die von Benutzern in ihrer Enterprise-VoIP-Clients angegeben sind. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern dies vom Benutzer konfiguriert ist. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die anrufweiterleitung aktiviert ist, können Benutzer angeben, ob Unbeantwortete Anrufe weitergeleitet werden soll, an eine andere Nummer oder an einen Exchange UM-Server, der zum Bereitstellen von Anrufbeantwortung konfiguriert wurde. Die Eingangsroutingkomponente wird standardmäßig auf allen Standard Edition-Server und Front-End-Servern installiert. 
  
## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Es gilt Anruf Autorisierungsregeln, wie von VoIP-Richtlinie des Benutzers zu den Anrufern definiert und bestimmt das optimale PSTN-Gateway für jeden Anruf geroutet wird. Die Ausgangsroutingkomponente wird standardmäßig auf allen Standard Edition-Server und Front-End-Servern installiert.
  
Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird. 
  
## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange UM Routingkomponente verarbeitet das routing zwischen Skype für Business Server und Servern mit Exchange Unified Messaging (UM), Skype für Business Server mit Unified Messaging-Funktionen integriert. 
  
Die Exchange UM Routingkomponente behandelt auch die Umleitung von Voicemail über das Telefonfestnetz, wenn Exchange UM-Server nicht verfügbar sind. Wenn Sie Enterprise-VoIP-Benutzern am haben Zweigniederlassungen, deren keine ausfallsichere WAN mit einem zentralen Standort, der Survivable Branch Appliance zu verknüpfen, die Sie am Zweigstellenstandort bereitstellen bietet ausfallsichere VoIP-Funktionen für Zweigstellenbenutzer während eines WAN-Ausfalls. Wenn die WAN-Verbindung nicht verfügbar ist, führt der Survivable Branch Appliance Folgendes aus:
  
- Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet
    
- Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen
    
- Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist.
    
Zum Aktivieren der voicemailumleitung wird empfohlen, Ihre Exchange-Administrator Exchange UM Auto Attendant zum Akzeptieren von Nachrichten nur konfiguriert.
  
Ausführliche Informationen zu diesen Features finden Sie unter [On-Premises Exchange Unified Messaging Integration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) und [Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx).
  
## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Die Routingkomponente für das Clusterübergreifende ist verantwortlich für Anrufe an die primären registrierungspool des angerufenen. Wenn dies nicht verfügbar ist, leitet die Komponente den Anruf an den sicherungsregistrierungspool des angerufenen. Wenn der primäre und der sicherungsregistrierungspool des angerufenen über das IP-Netzwerk nicht erreichbar sind, leitet die Routingkomponente für das Clusterübergreifende den Anruf über das Telefonfestnetz an Telefonnummer des Benutzers.
  
## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Die folgenden: weiteren Komponenten auf dem Front-End-Server oder dem Director darstellen, die grundlegende Unterstützung für VoIP bieten, jedoch selbst keine VoIP-Komponenten
  
- **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Information verteilt die Eingangsroutingkomponente den Anruf an die registrierten SIP-Endpunkte des Benutzers. Benutzerdienste ist eine Hauptkomponente auf allen Front-End-Servern und Directors.
    
- **Der Benutzerreplikationsdienst.** Extrahieren von Telefonnummern aus Active Directory Domain Services, und schreibt sie in Tabellen in der RTC-Datenbank, in dem sie für Benutzerdienste und des Adressbuchservers verfügbar sind. Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.
    
- **Adressbuchserver.** Enthält Informationen aus der globalen Adressliste von Active Directory-Domänendienste Skype für Business Server-Clients. Es ruft auch Benutzer-und Kontaktinformationen aus der RTC-Datenbank, schreibt die Informationen in die Adressbuchdateien und speichert dann die Dateien auf einen freigegebenen Ordner, in dem sie von Skype für Business Clients heruntergeladen werden. Der Adressbuchserver schreibt die Informationen in der RTCAb-Datenbank, die vom Adressbuch-Webabfragedienst-Dienst verwendet wird, um auf der Suchabfragen von Benutzern von Skype für mobile Unternehmen zu reagieren. Optional normalisiert sie Telefonnummern, die in die Datenbank RTC Benutzerkontakte in Skype für Unternehmen geschrieben werden. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Der Adressbuch-Webabfragedienst-Dienst wird standardmäßig mit den Webdiensten auf jedem Front-End-Servern installiert.
    

