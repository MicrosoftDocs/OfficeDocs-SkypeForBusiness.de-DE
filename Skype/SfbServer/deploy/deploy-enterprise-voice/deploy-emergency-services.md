---
title: Bereitstellen von E9-1-1 in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Bereitstellen von E9-1-1 in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: 82e14f2fb86ec949a60b95746fc3ef41f9cf3b50
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>Bereitstellen von E9-1-1 in Skype for Business Server 2015
 
Bereitstellen von E9-1-1 in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
  
Erweiterte E9-1-1 (E9-1-1) ist eine Notfall Benachrichtigungsfunktion, die eine oder eine Postanschrift Telefonnummer des Anrufers zuordnet. Anhand dieser Informationen kann die Rettungsleitstelle umgehend Rettungskräfte an die Unglücksstelle senden.
  
Zur Unterstützung der E9-1-1 muss Skype für Business Server möglicherweise ein Client einen Standort korrekt zugeordnet und dafür sorgen, dass diese Informationen zum Weiterleiten des Notrufs an den nächstgelegenen PSAP verwendet wird.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Voraussetzungen für die Bereitstellung von E9-1-1

Vor der Bereitstellung von E9-1-1, müssen Sie bereits Ihrer Skype für Business Server interne Server, einschließlich einer zentralen Verwaltungsspeicher, einem Front-End-Pool oder Standard Edition-Server bereitgestellt haben. Sie müssen auch einen oder mehrere Vermittlungsserver, entweder eigenständig bereitstellen oder mit dem Front-End-Server verbunden. Darüber hinaus benötigen Sie für eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN).
  
## <a name="deployment-process"></a>Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess.
  
|**Phase**|**Schritte**|**Rollen**|**Dokumentation zur Bereitstellung**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von VoIP-Nutzungen, Routen und Trunks  <br/> |1. erstellen Sie 1. einen neuen PSTN-verwendungsdatensatz. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung **PSTN-Verwendung** verwendet wird. <br/> 2. erstellen oder Zuweisen einer VoIP-Route, die im vorherigen Schritt erstellten PSTN-Datensatz, und zeigen Sie das gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway.  <br/> 3. Legen Sie für einen SIP-Trunk E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über das SIP, PIDF-LO-Daten zu übergeben, mit dem Cmdlet **Set-CsTrunkConfiguration – EnablePIDFLOSupport** weitergegeben wird. <br/> 4. optional für einen SIP-Trunk E9-1-1-Dienstanbieter erstellen Sie, oder weisen Sie eine lokale PSTN-Route für Anrufe, die vom E9-1-1-Dienstanbieter SIP-Trunk nicht verarbeitet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer E9-1-1-VoIP-Route in Skype für Business Server 2015](configure-an-e9-1-1-voice-route.md) <br/> |
|Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen  <br/> |1. Lesen Sie die globale Standortrichtlinie.  <br/> 2. erstellen Sie eine ortungsrichtlinie mit einer auf Benutzerebene; oder, wenn die Organisation über mehr als einen Standort mit verschiedenen notfallverwendungen verfügt, erstellen Sie eine ortungsrichtlinie mit einer auf Netzwerkebene.  <br/> 3. Zuweisen der ortungsrichtlinie zu Netzwerkstandorten.  <br/> 4. den Netzwerkstandort geeignete Subnetze hinzugefügt.  <br/> 5. (Optional) weisen Sie die Standortrichtlinie zu Benutzerrichtlinien.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)  <br/> |[Erstellen von ortungsrichtlinien in Skype für Business Server 2015](create-location-policies.md) <br/> [Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in Skype für Business Server 2015](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Konfigurieren der Standortdatenbank  <br/> |1. Füllen der Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten.  <br/> 2. für ELIN-Gateways, fügen Sie die ELINs der \<CompanyName\> Spalte.  <br/> 3. konfigurieren Sie die Verbindung zum E9-1-1-Dienstanbieter zum Überprüfen von Adressen.  <br/> 4. Überprüfen Sie die Adressen mit dem E9-1-1-Dienstanbieter.  <br/> 5. veröffentlichen Sie die aktualisierte Datenbank.  <br/> 6. für ELIN-Gateways Laden Sie die ELINs in die PSTN-Betreibers Automatic Location Identification ()-Datenbank.  <br/> |CSVoiceAdmin  <br/> Cslocationadmin bei  <br/> |[Konfigurieren der Standortdatenbank in Skype für Business Server 2015](configure-the-location-database.md) <br/> |
|Konfigurieren von erweiterten Funktionen (optional)  <br/> |1. konfigurieren Sie die URL für die SNMP-Anwendung.  <br/> 2. konfigurieren Sie die URL für den Speicherort des sekundären standortinformationsdienst.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer SNMP-Anwendung in Skype für Business Server 2015](configure-an-snmp-application.md) <br/> [Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server 2015](secondary-location-information-service.md) <br/> |
   

