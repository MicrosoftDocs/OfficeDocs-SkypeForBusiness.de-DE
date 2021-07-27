---
title: Für Direct Routing zertifizierte Sitzungsrahmencontroller
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Der Administrator kann erfahren, welche Session Border Controller (SBCs) für Direct Routing zertifiziert wurden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d7103ecb4183674fe1e92c7d7e3a37182c0d50
ms.sourcegitcommit: beb66bc2ce70edbaf6c77eee6d8c050c5cb37fe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2021
ms.locfileid: "53515170"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Liste der für direktes Routing zertifizierten Session Border Controller

Microsoft arbeitet mit ausgewählten SBC-Anbietern (Session Border Controller) zusammen, um ihre SBCs für den Einsatz mit direktem Routing zu zertifizieren.

Microsoft arbeitet mit jedem Anbieter zusammen, um folgende Schritte zu unternehmen:

- Gemeinsam an den SIP-Verbindungsprotokollen zu arbeiten.
- Intensive Tests mithilfe eines Drittanbieterlabors durchzuführen. Nur Geräte, die die Tests bestehen, sind zertifiziert.
- Alle zertifizierten Geräte werden täglich in Produktions- und Präproduktionsumgebungen getestet. Die Validierung der Geräte in Präproduktionsumgebungen gewährleistet, dass neue Versionen des Codes für direktes Routing in der Cloud auf zertifizierten SBCs funktionieren.
- Einen gemeinsamen Supportprozess mit den SBC-Anbietern bereitzustellen.

  > [!NOTE]
  > Microsoft unterstützt das Telefonsystem nur, wenn ein zertifiziertes Gerät oder Geräte über Direct Routing verbunden sind. Microsoft behält sich das Recht vor, Supportfälle abzulehnen, in denen ein nicht zertifiziertes Gerät über Direct Routing mit dem Telefonsystem verbunden ist. Wenn Microsoft feststellt, dass das Direct Routing-Problem eines Kunden mit dem SBC-Gerät eines Anbieters auftritt, muss der Kunde den SBC-Anbieter um Support bitten.

Die folgende Tabelle enthält eine Liste der für direktes Routing zertifizierten Geräte. (Informationen dazu, welche SBC-Anbieter die Lokale Medienoptimierung unterstützen, finden Sie unter [Optimierung lokaler Medien für Direktes Routing konfigurieren](direct-routing-media-optimization-configure.md).)

[Hier finden Sie weitere Informationen zu direktem Routing](https://aka.ms/dr).
Wenn Sie Fragen zum SBC-Zertifizierungsprogramm für direktes Routing haben, wenden Sie sich per E-Mail an drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>Zertifizierte SBC-Anbieter

|                                                       Anbieter                                                        |       Produkt       | Nicht-Medienumgehung | Medienumgehung | Softwareversion | Notruf-Dienstanbieterfähig* | ELIN-fähig |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Ausstehend     |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  Unterstützt 7.20A.250 (empfohlen 7.20A.258)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Unterstützt 7.20A.250 (empfohlen 7.20A.258) |  &#10004;    |  &#10004;  |
|  [Menübandkommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Unterstützt 8.2 und 7.2 (empfohlen 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Unterstützt 8.2 und 7.2 (empfohlen 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Unterstützt 8.2 und 7.2 (empfohlen 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Unterstützt 8.2 und 7.2 (empfohlen 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Unterstützt 8.2 und 7.2 (empfohlen 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x oder 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x oder 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    Lite SBC Schwedisch     |     &#10004;     |  &#10004;    |      8.x oder 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc-Serie |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Unterstützt 3.20 (empfohlen 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta-SBC        |     &#10004;   | &#10004; |      4.7 (4.9 für Medienumgehung)      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) für Router der Serie 1000 Integrated Services        |     &#10004;   | &#10004; |      Unterstützte IOS XE Amsterdam- und 17.2.1r-Versionen (empfohlen: 17.3.2)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) für Router der Serie 4000 Integrated Services        |     &#10004;   | &#10004; |   Unterstützte IOS XE Amsterdam- und 17.2.1r-Versionen (empfohlen: 17.3.2)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) für Cloud Services Router der 1000V-Serie       |     &#10004;   | &#10004; |      Unterstützte IOS XE Amsterdam- und 17.2.1r-Versionen (empfohlen: 17.3.2)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) für Aggregation Services-Router der 1000-Serie      |     &#10004;   | &#10004; |      Unterstützte IOS XE Amsterdam- und 17.2.1r-Versionen (empfohlen: 17.3.2)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) für 8000 Edge Platforms      |     &#10004;   | &#10004; |      IOS XE-Amsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya-Sitzungsrahmencontroller für Unternehmen (ASBCE)    |     &#10004;     |       &#10004;     |       Release 8.1.1 (8.1.2 für Medienumgehung)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Unterstützt 5.0 (empfohlen 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid-Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams-SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape-Sitzungsrahmencontroller   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse-Netzwerke](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogischer BorderNet-SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (früher bekannt als Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel-Serie   |     &#10004;     |         |      DGW 48.0.2340 (Recommended DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops-Sitzungsrahmencontroller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperkonvergente Stimme   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

* Notruf-Dienstanbieter

- [Dynamisches Routing von Bandbreitenstandorten](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado-Notfallroutingdienst (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado-Notfallgateway (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Direktes Routing und Interoperabilität analoger Geräte

In der folgenden Tabelle sind Geräte aufgeführt, die für Interoperabilität zwischen Direct Routing und Analog Devices verifiziert sind.

|                                                       Anbieter                                                        |       Produkt       | Überprüfte
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 Multiplatform Analog-Telefonadapter |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 Software Version 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME Software Version 8.3.0.1.2 |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Softwareversion: 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Softwareversion: 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode mit Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Um uns Produktfeedback zu Teams zu geben, z. B. Ideen für neue Features, gehen Sie auf [Uservoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Beachten Sie die Zertifizierung, die einer Hauptversion erteilt wurde. Das bedeutet, dass Firmware mit einer beliebigen Anzahl in der SBC-Firmware nach der Hauptversion unterstützt wird.
