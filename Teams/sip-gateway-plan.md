---
title: Planen des SIP-Gateways
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über SIP-Gateways, z. B. Anforderungen und Vorteile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bf8e6ab6f2a5ba7303887e9e7d7d72d22c50964
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794683"
---
# <a name="plan-for-sip-gateway"></a>Planen des SIP-Gateways

Mit dem SIP-Gateway kann Ihre Organisation jedes kompatible SIP-Gerät mit Microsoft Teams verwenden, um Ihre Investitionen in SIP-Geräte zu erhalten. Jetzt können Sie sich mit Ihren Unternehmensanmeldeinformationen bei Teams anmelden und Anrufe mit einem kompatiblen SIP-Gerät tätigen und empfangen. Kompatible Geräte können Skype for Business IP-Telefone mit Standard-SIP-Firmware, Cisco-IP-Telefone mit multiplatform SIP-Firmware oder SIP-Geräte von Anbietern wie Poly, Yealink und AudioCodes sein. Informationen zum Konfigurieren Ihrer SIP-Geräte für DAS SIP-Gateway finden [Sie unter Konfigurieren des SIP-Gateways](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Vorteile des SIP-Gateways

Das SIP-Gateway verbindet kompatible SIP-Geräte mit Teams, damit Ihre Benutzer nahtlos zu Teams-Telefonie migrieren können. Mithilfe des SIP-Gateways können Ihre Benutzer folgende Aktionen ausführen:

- **Anrufe tätigen:** Sip-Gerätebenutzer können Anrufe an das Telefonfestnetz (Public Switched Telephone Network, PSTN), an andere SIP-Geräte sowie an Teams und Skype for Business-Benutzer tätigen. SIP-Gerätebenutzer können nur Benutzer anrufen, die über Telefonnummern verfügen.
- **Anrufe empfangen:** Sip-Gerätebenutzer können einen Anruf vom PSTN, von Teams oder Skype for Business Benutzern mit SIP-Geräten sowie von Teams und Skype for Business Clientanwendungen empfangen. Das SIP-Gerät fungiert als Teams-Endpunkt. Eingehende Anrufe werden auch an das SIP-Gerät des Benutzers verzweigt.
- **Mehrere gleichzeitige Anrufe:** Ein SIP-Gerätebenutzer in einem Anruf kann den Anruf in den Haltebereich setzen, um andere Anrufe zu tätigen oder zu empfangen. Ein SIP-Gerätebenutzer kann auch zwei Anrufe konferenzen.
- **Nicht stören:** Ein SIP-Gerätebenutzer kann festlegen, dass das Gerät nicht gestört wird, sodass das Gerät nicht für eingehende Anrufe klingelt. Dies hat keine Auswirkungen auf den Status des Benutzers auf allen anderen Teams-Endpunkten.
- **Halten/Fortsetzen und Stummschalten/Stummschalten aufheben:** Ein SIP-Gerätebenutzer kann einen Anruf mithilfe der Features für diese Aktionen auf dem Gerät halten und fortsetzen oder stummschalten und die Stummschaltung aufheben.
- **Voicemail:** Sip-Gerätebenutzer können elektronisch gespeicherte Sprachnachrichten anhören, die Anrufer für sie verlassen.
- **Warteindikator für Nachrichten:** Sip-Gerätebenutzer können Benachrichtigungen erhalten, die sie benachrichtigen, wenn sie neue Voicemailnachrichten haben.
- **Anmelden und Abmelden:** BENUTZER von SIP-Geräten können sich auf dem Gerät bei Teams anmelden und abmelden.
- **Dualton-Multifrequenz:** Sip-Gerätebenutzer können Nummerntasten drücken, um während interaktiver Sprachantwortanrufe Eingaben bereitzustellen.
- **Teams-Besprechungen:** Ein SIP-Gerätebenutzer kann an einer Teams-Besprechung teilnehmen, indem er die Zugriffsnummer der Besprechung wählt. Besprechungsteilnehmer können der Besprechung einen SIP-Gerätebenutzer hinzufügen, indem sie die Telefonnummer des Benutzers anrufen oder einfach einen Teilnehmer hinzufügen, indem sie auf "Teilnahme anfordern" klicken, wird auch das SIP-Gerät des Benutzers benachrichtigt. Gastbenutzer aus einer anderen Organisation können einer Teams-Besprechung von einem Teilnehmer hinzugefügt werden, der sich an die Nummer eines Gastbenutzers auswählt, um diesen Gast einzuschließen.
- **Anrufüberweisungen:** SIP-Gerätebenutzer können Anrufe übertragen. DAS SIP-Gateway unterstützt sowohl blinde als auch beratende Übertragungen.
- **Lokale Anrufweiterleitung:** Ein SIP-Gerätebenutzer kann Weiterleitungsregeln (immer, bei Timeout und beschäftigt) für das Gerät festlegen. Wenn das Gerät mit dem SIP-Gateway verbunden ist, wird der Anruf basierend auf der vom Gerätebenutzer festgelegten Regel an die Zieladresse umgeleitet. Damit die lokale Anrufweiterleitung funktioniert, muss der Administrator das `AllowCallRedirect` Attribut `Set-CsTeamsCallingPolicy` auf `Enabled`festlegen.

## <a name="requirements-to-use-sip-gateway"></a>Anforderungen für die Verwendung des SIP-Gateways

Teams-Benutzer müssen über eine Telefonnummer verfügen, bei der PSTN-Anrufe aktiviert sind, um SIP-Gateway verwenden zu können.

### <a name="hardware-software-and-licenses"></a>Hardware, Software und Lizenzen

Wenn Sie über ein 3PIP- oder SIP-Gerät verfügen, müssen Sie über Folgendes verfügen:

- Eine Lizenz für das Telefonsystem (über E5 oder eine eigenständige Lizenz)
- PSTN-Aktivierung (d. h. eine Telefonnummer) über einen Microsoft Teams-Anrufplan, Direct Routing oder Telefonieanbieter
- Eine Common Area Phone-Lizenz für alle Geräte im einheitlichen Bereich

## <a name="compatible-devices"></a>Kompatible Geräte

|Anbieter    |Modell      |Mindestversion der Firmware|Genehmigte Firmwareversion|Hinweise|Links|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Geräte mit Unternehmensfirmware müssen in Multiplatform-Firmware konvertiert werden. Lesen Sie den Leitfaden auf der rechten Seite, um zu erfahren, wie das geht.|[Cisco Firmware Konvertierungshandbuch](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Poly**  |           |            |           |Das Gerät wird automatisch neu gestartet und die ausgewählte Firmware installiert.|   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Yealink-Unterstützung](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Einige AudioCodes-SIP-Geräte benötigen eine Bereitstellungs-URL-Einstellung. Laden Sie Upgradedateien für die betroffenen AudioCodes-Geräte auf der rechten Seite herunter, und installieren Sie sie. |[Herunterladbare Dateien für betroffene Geräte unter AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |RX50        |3.2.1      |3.4.6.687  |   |   |
|**Spektrenlink**|       |           |           |   |[Spektrenlink-Unterstützung](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7212        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7502        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7522        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7532        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7622        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7642        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7722        |PCS22B     |PCS22B     |Mobilteil |   |
|          |7742        |PCS22B     |PCS22B     |Mobilteil |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |IP-DECT-Server |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |IP-DECT-Server |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |IP-DECT-Server |   |
|          |Virtual IP-DECT Server One |PCS22Ab |PCS22Ab |IP-DECT-Server |   |
|          |IP-DECT-Basisstation |PCS22Ab |PCS22Ab |IP-DECT-Server |   |

> [!NOTE]
> Spectralink Handsets empfangen Firmwareupdates über die Luft von Denklink IP-DECT-Servern.

> [!NOTE]
> Für Supportanfragen sollten Kunden, die IP-DECT-Systeme mit Teams SIP Gateway verwenden, sich an ihren DECT-Hersteller oder ihre Implementierungskanalpartner wenden.

> [!NOTE]
> Bei einigen Geräten ist die Minimale Firmwareversion größer als die genehmigte Firmwareversion. Dies liegt daran, dass die 3.X-Version die Skype for Business-Version ist. Wir aktualisieren die SIP-Version 2.X.
