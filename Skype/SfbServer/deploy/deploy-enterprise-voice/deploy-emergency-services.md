---
title: Bereitstellen von Notfalldiensten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Bereitstellen von E9-1-1 in Skype for Business Server Enterprise-VoIP Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: 4373797b8a96f83100a39735cf20b51558eb15d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291270"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Bereitstellen von Notfalldiensten in Skype for Business Server
 
Bereitstellen von E9-1-1 in Skype for Business Server Enterprise-VoIP Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
  
Enhanced 9-1-1 (E9-1-1) ist eine Notfall Benachrichtigungsfunktion, die die Telefonnummer des Anrufers mit einer bürgerlichen oder einer Anschrift verknüpft. Anhand dieser Informationen kann die Rettungsleitstelle umgehend Rettungskräfte an die Unglücksstelle senden.
  
Zur Unterstützung von E9-1-1 muss Skype for Business Server in der Lage sein, einen Standort ordnungsgemäß mit einem Client zu verbinden und sicherzustellen, dass diese Informationen verwendet werden, um den Notruf an den nächstgelegenen PSAP zu leiten.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Voraussetzungen für die Bereitstellung von E9-1-1

Bevor Sie E9-1-1 bereitstellen, müssen Sie Ihre Skype for Business Server-internen Server bereits bereitgestellt haben, einschließlich eines zentralen Verwaltungsspeichers, eines Front-End-Pools oder eines Standard Edition-Servers. Sie müssen auch einen oder mehrere Vermittlungsserver bereitstellen, entweder eigenständig oder mit Front-End-Servern. Darüber hinaus benötigen Sie für eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN).
  
## <a name="deployment-process"></a>Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess.
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von VoIP-Nutzungen, Routen und Trunks  <br/> |1. Erstellen Sie einen neuen PSTN-Verwendungs Eintrag. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung **PSTN-Verwendung** verwendet wird. <br/> 2. Erstellen Sie eine VoIP-Route, und weisen Sie Sie dem im vorherigen Schritt erstellten PSTN-Verwendungsdaten Satz zu, und zeigen Sie das Gateway-Attribut auf den E9-1-1-SIP-Stamm oder das Elin-Gateway.  <br/> 3. für einen SIP Trunk E9-1-1 Service-Anbieter stellen Sie den trunk ein, der mit E9-1-1-Anrufen über das SIP PIDF-Lo-Daten mithilfe des Cmdlets " **CsTrunkConfiguration-EnablePIDFLOSupport** " übergeben wird. <br/> 4. Optional können Sie für einen SIP Trunk E9-1-1 Service Provider eine lokale PSTN-Route für Anrufe erstellen oder zuweisen, die nicht vom SIP-Stamm des E9-1-1-Service-Anbieters behandelt werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer E9-1-1-VoIP-Route in Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen  <br/> |1. Überprüfen Sie die globale Standortrichtlinie.  <br/> 2. Erstellen Sie eine ortungsrichtlinie mit einem Bereich auf Benutzerebene; Wenn die Organisation über mehr als eine Website mit unterschiedlichen Notfall Nutzungen verfügt, erstellen Sie eine ortungsrichtlinie mit einem Bereich auf Netzwerkebene.  <br/> 3. Zuweisen der Standortrichtlinie zu Netzwerk Websites  <br/> 4. Fügen Sie die entsprechenden Subnetze zur Netzwerk Website hinzu.  <br/> 5. (optional) zuweisen der Standortrichtlinie zu Benutzerrichtlinien  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)  <br/> |[Erstellen von Standortrichtlinien in Skype for Business Server](create-location-policies.md) <br/> [Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Konfigurieren der Standortdatenbank  <br/> |1. füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Speicherorten auf.  <br/> 2. für Elin-Gateways fügen Sie die Elins zur Spalte \<CompanyName\> hinzu.  <br/> 3. Konfigurieren Sie die Verbindung mit dem E9-1-1-Dienstanbieter für die Überprüfung von Adressen.  <br/> 4. Überprüfen Sie die Adressen mit dem E9-1-1-Dienstanbieter.  <br/> 5. veröffentlichen Sie die aktualisierte Datenbank.  <br/> 6. für Elin-Gateways laden Sie die Elins in die Datenbank für die automatische Ortungs-ID (Automatic Location Identification, Ali) Ihres PSTN-Netzbetreibers hoch.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Konfigurieren der Standortdatenbank in Skype for Business Server](configure-the-location-database.md) <br/> |
|Konfigurieren von erweiterten Funktionen (optional)  <br/> |1. Konfigurieren Sie die URL für die SNMP-Anwendung.  <br/> 2. Konfigurieren Sie die URL für den Standort des sekundären Standort Informationsdiensts.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer SNMP-Anwendung in Skype for Business Server](configure-an-snmp-application.md) <br/> [Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server](secondary-location-information-service.md) <br/> |
   

