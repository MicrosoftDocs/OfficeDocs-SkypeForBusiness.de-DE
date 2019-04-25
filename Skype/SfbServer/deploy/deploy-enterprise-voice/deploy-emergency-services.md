---
title: Notdienste in Skype für Business Server bereitstellen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Bereitstellen von E9-1-1 in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: b24bdfdd40787c8be57b541f3a163e3c21f3012a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223127"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Notdienste in Skype für Business Server bereitstellen
 
Bereitstellen von E9-1-1 in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
  
Erweiterte E9-1-1 (E9-1-1) ist eine Notfall Benachrichtigungsfunktion, die eine oder eine Postanschrift Telefonnummer des Anrufers zuordnet. Anhand dieser Informationen kann die Rettungsleitstelle umgehend Rettungskräfte an die Unglücksstelle senden.
  
Zur Unterstützung der E9-1-1 muss Skype für Business Server möglicherweise ein Client einen Standort korrekt zugeordnet und dafür sorgen, dass diese Informationen zum Weiterleiten des Notrufs an den nächstgelegenen PSAP verwendet wird.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Voraussetzungen für die Bereitstellung von E9-1-1

Vor der Bereitstellung von E9-1-1, müssen Sie bereits Ihrer Skype für Business Server interne Server, einschließlich einer zentralen Verwaltungsspeicher, einem Front-End-Pool oder Standard Edition-Server bereitgestellt haben. Sie müssen auch einen oder mehrere Vermittlungsserver, entweder eigenständig bereitstellen oder mit dem Front-End-Server verbunden. Darüber hinaus benötigen Sie für eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN).
  
## <a name="deployment-process"></a>Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess.
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von VoIP-Nutzungen, Routen und Trunks  <br/> |1. erstellen Sie 1. einen neuen PSTN-verwendungsdatensatz. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung **PSTN-Verwendung** verwendet wird. <br/> 2. erstellen oder Zuweisen einer VoIP-Route, die im vorherigen Schritt erstellten PSTN-Datensatz, und zeigen Sie das gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway.  <br/> 3. Legen Sie für einen SIP-Trunk E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über das SIP, PIDF-LO-Daten zu übergeben, mit dem Cmdlet **Set-CsTrunkConfiguration – EnablePIDFLOSupport** weitergegeben wird. <br/> 4. optional für einen SIP-Trunk E9-1-1-Dienstanbieter erstellen Sie, oder weisen Sie eine lokale PSTN-Route für Anrufe, die vom E9-1-1-Dienstanbieter SIP-Trunk nicht verarbeitet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer E9-1-1-VoIP-Route in Skype für Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen  <br/> |1. Lesen Sie die globale Standortrichtlinie.  <br/> 2. erstellen Sie eine ortungsrichtlinie mit einer auf Benutzerebene; oder, wenn die Organisation über mehr als einen Standort mit verschiedenen notfallverwendungen verfügt, erstellen Sie eine ortungsrichtlinie mit einer auf Netzwerkebene.  <br/> 3. Zuweisen der ortungsrichtlinie zu Netzwerkstandorten.  <br/> 4. den Netzwerkstandort geeignete Subnetze hinzugefügt.  <br/> 5. (Optional) weisen Sie die Standortrichtlinie zu Benutzerrichtlinien.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)  <br/> |[Erstellen von ortungsrichtlinien in Skype für Business Server](create-location-policies.md) <br/> [Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in Skype für Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Konfigurieren der Standortdatenbank  <br/> |1. Füllen der Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten.  <br/> 2. für ELIN-Gateways, fügen Sie die ELINs der \<CompanyName\> Spalte.  <br/> 3. konfigurieren Sie die Verbindung zum E9-1-1-Dienstanbieter zum Überprüfen von Adressen.  <br/> 4. Überprüfen Sie die Adressen mit dem E9-1-1-Dienstanbieter.  <br/> 5. veröffentlichen Sie die aktualisierte Datenbank.  <br/> 6. für ELIN-Gateways Laden Sie die ELINs in die PSTN-Betreibers Automatic Location Identification ()-Datenbank.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Konfigurieren der Standortdatenbank in Skype für Business Server](configure-the-location-database.md) <br/> |
|Konfigurieren von erweiterten Funktionen (optional)  <br/> |1. konfigurieren Sie die URL für die SNMP-Anwendung.  <br/> 2. konfigurieren Sie die URL für den Speicherort des sekundären standortinformationsdienst.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer SNMP-Anwendung in Skype für Business Server](configure-an-snmp-application.md) <br/> [Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server](secondary-location-information-service.md) <br/> |
   

