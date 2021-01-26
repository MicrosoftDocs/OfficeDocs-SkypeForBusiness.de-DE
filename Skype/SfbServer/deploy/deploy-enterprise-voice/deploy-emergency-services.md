---
title: Bereitstellen von Notrufdiensten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Stellen Sie E9-1-1 in Skype for Business Server Enterprise-VoIP. Umfasst die Voraussetzungen und die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812525"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Bereitstellen von Notrufdiensten in Skype for Business Server
 
Stellen Sie E9-1-1 in Skype for Business Server Enterprise-VoIP. Umfasst die Voraussetzungen und die Prüfliste für den Bereitstellungsprozess.
  
9-1-1 (erweitert) (E9-1-1) ist eine Notfallbenachrichtigungsfunktion, die die Telefonnummer des Anrufers mit einer Anschrift oder einer Anschrift verknüpft. Anhand dieser Informationen kann die Rettungsleitstelle umgehend Rettungskräfte an die Unglücksstelle senden.
  
Zur Unterstützung von E9-1-1 muss Skype for Business Server in der Lage sein, einen Standort ordnungsgemäß einem Client zuzuordnen und sicherzustellen, dass diese Informationen zum Routen des Notrufs an die nächste Rettungsstelle verwendet werden.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Voraussetzungen für die Bereitstellung von E9-1-1

Bevor Sie E9-1-1 bereitstellen, müssen Sie bereits Ihre internen Skype for Business Server-Server bereitgestellt haben, einschließlich eines zentralen Verwaltungsspeichers, eines Front-End-Pools oder eines Standard Edition-Servers. Sie müssen auch einen oder mehrere Vermittlungsserver bereitstellen, entweder eigenständig oder mit Front-End-Servern. Darüber hinaus erfordert eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN).
  
## <a name="deployment-process"></a>Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess.
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von VoIP-Nutzungen, -Routen und Trunkkonfigurationen  <br/> |1. Erstellen Sie einen neuen PSTN-Verwendungsdatensatz. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung **PSTN-Verwendung** verwendet wird. <br/> 2. Erstellen oder weisen Sie dem im vorherigen Schritt erstellten PSTN-Verwendungsdatensatz eine Sprachroute zu, und verweisen Sie dann das Gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway.  <br/> 3. Legen Sie für einen SIP-Trunk-E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über das SIP abnimmt, so fest, dass PIDF-LO-Daten mithilfe des Cmdlets **"Set-CsTrunkConfiguration -EnablePIDFLOSupport"** übergeben werden. <br/> 4. Optional können Sie für einen SIP-Trunk-E9-1-1-Dienstanbieter eine lokale Festnetzroute für Anrufe erstellen oder zuweisen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer E9-1-1-Voiceroute in Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen  <br/> |1. Überprüfen Sie die globale Standortrichtlinie.  <br/> 2. Erstellen einer Standortrichtlinie auf Benutzerebene; Oder erstellen Sie eine Standortrichtlinie auf Netzwerkebene, wenn die Organisation über mehrere Standorte mit unterschiedlichen Notfallverwendungen verfügt.  <br/> 3. Weisen Sie die Standortrichtlinie Netzwerkstandorten zu.  <br/> 4. Fügen Sie dem Netzwerkstandort die entsprechenden Subnetze hinzu.  <br/> 5. (Optional) Weisen Sie die Standortrichtlinie Benutzerrichtlinien zu.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)  <br/> |[Erstellen von Standortrichtlinien in Skype for Business Server](create-location-policies.md) <br/> [Hinzufügen einer Standortrichtlinie zu einem Netzwerkstandort in Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Konfigurieren der Standortdatenbank  <br/> |1. Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.  <br/> 2. Fügen Sie bei ELIN-Gateways die ELINs zur Spalte \<CompanyName\> hinzu.  <br/> 3. Konfigurieren Sie die Verbindung mit dem E9-1-1-Dienstanbieter zum Überprüfen von Adressen.  <br/> 4. Überprüfen Sie die Adressen mit dem E9-1-1-Dienstanbieter.  <br/> 5. Veröffentlichen Sie die aktualisierte Datenbank.  <br/> 6. Laden Sie für ELIN-Gateways die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Netzbetreibers hoch.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Konfigurieren der Standortdatenbank in Skype for Business Server](configure-the-location-database.md) <br/> |
|Konfigurieren von erweiterten Funktionen (optional)  <br/> |1. Konfigurieren Sie die URL für die SNMP-Anwendung.  <br/> 2. Konfigurieren Sie die URL für den Speicherort des sekundären Standortinformationsdiensts.  <br/> |CSVoiceAdmin  <br/> |[Konfigurieren einer SNMP-Anwendung in Skype for Business Server](configure-an-snmp-application.md) <br/> [Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server](secondary-location-information-service.md) <br/> |
   

