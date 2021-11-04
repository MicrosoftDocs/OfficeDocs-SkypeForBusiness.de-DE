---
title: Planen von Notrufdiensten in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Erfahren Sie mehr über erweiterte 9-1-1 (E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerbung und Anrufweiterleitung.
ms.openlocfilehash: f3efcea6747c27e041e581b5d0461fd4c925eb84
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767613"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planen von Notrufdiensten in Skype for Business Server

Erfahren Sie mehr über erweiterte 9-1-1 (E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerbung und Anrufweiterleitung.

Skype for Business Server unterstützt erweiterte 9-1-1 (E9-1-1)-Dienste innerhalb der VEREINIGTEn Staaten als Teil einer Enterprise-VoIP Bereitstellung. E9-1-1 ist eine Notruffunktion, die einen 9-1-1-Anruf einem Notfallstandort (Emergency Response Location, ERL) zuweist, der aus öffentlichen Adressen (d. h. Straßenadressen) und anderen spezifischeren Standortinformationen, z. B. Stocknummern, für Anrufe aus Gebäuden und anderen mehrinstanzenfähigen Einrichtungen besteht. Mithilfe der bereitgestellten ERL kann eine Rettungsleitstelle (Public Safety Answering Point, PSAP) die Erstantworter sofort an den Anrufer weiterleiten, mit reduziertem Risiko, den Antwortenden versehentlich an einen falschen oder mehrdeutigen Ort zu leiten.

> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Weitere Informationen finden Sie unter [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP Features: Anrufsteuerung, Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei dieser Features gelten, finden Sie unter ["Netzwerkeinstellungen" für die erweiterten Enterprise-VoIP Features in Skype for Business Server.](network-settings-for-advanced-features.md)

Skype for Business Server unterstützt E9-1-1-Anrufe (Enhanced 9-1-1) von Skype for Business Clients und Lync Telefon Edition-Geräten. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business oder Lync Telefon Edition getätigt werden, Informationen zum Notfallstandort (Emergency Response Location, ERL) aus der Standortinformationsdienstdatenbank. ERLs bestehen aus öffentlichen Adressen (d. h. Straßenadressen) und anderen Informationen, die dazu beiträgt, einen präziseren Standort in Office-Gebäuden und anderen mehrinstanzenfähigen Einrichtungen zu identifizieren. Wenn ein Benutzer einen Notruf abnimmt, leitet Skype for Business Server die Anrufaudio zusammen mit den Standort- und Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Dienstanbieter weiter. Der E9-1-1-Dienstanbieter verwendet die Adresse des Anrufers, um den Anruf an die Rettungsleitstelle (Public Safety Answering Point, PSAP) weiterzuleiten, die den Standort des Anrufers bedient, und sendet einen Esqk (Emergency Service Query Key), den die PSAP zum Nachschlagen der ERL des Anrufers verwendet.

Skype for Business Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:

- Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

- Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, fügen Sie der Standortinformationsdienstdatenbank ERLs hinzu und überprüfen dann die Standorte anhand eines Master Street Address Guide (MSAG), der vom E9-1-1-Dienstanbieter verwaltet wird. Wenn ein E9-1-1-Dienstanbieter einen Anruf empfängt, der keine Standortinformationen enthält oder über einen Standort verfügt, der nicht anhand der MSAG überprüft wurde, leitet der E9-1-1-Dienstanbieter den Anruf an ein nationales/regionales Notruf-Reaktionscenter (Emergency Call Response Center, ECRC) weiter, das mit speziell geschultem Personal besetzt ist, das den Standort des Anrufers nach Möglichkeit verbal abruft.  und den Anruf manuell an die entsprechende PsAP weiterleiten. (Einige SIP-Trunk-E9-1-1-Dienstanbieter bieten Kunden auch eine DID-Nummer (Direct Inward Dialing) für das PSTN, die eine alternative Methode zum Weiterleiten von 9-1-1-Anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund fehlschlägt.)

Im Gegensatz zu TDM-Telefonen (Time Division Multiplexing) und IP-basierten Nebenstellenanlagen (Private Branch Exchange, PBX), die über feste Standorte verfügen, kann ein Skype for Business Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, hilft Skype for Business Server sicherzustellen, dass der Notruf unabhängig davon, wo sich ein Anrufer befindet, an die Rettungsleitstelle weitergeleitet werden kann, die den Standort des Anrufers bedient. Wenn sich z. B. das Hauptbüro eines Benutzers in Redmond, Washington, befindet, der Benutzer aber einen Notruf von einem Computer in einer Zweigstelle in Wichita abgibt, leitet Der SIP-Trunk oder der PSTN-basierte E9-1-1-Dienstanbieter den Anruf an die PSAP in Wichita weiter, nicht an den PSAP in Redmond.

Wenn Sie ein ELIN-Gateway verwenden, fügen Sie auch ERLs zur Standortinformationsdienstdatenbank hinzu, fügen aber auch eine ELIN-Nummer für jeden Standort hinzu. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

> [!NOTE]
> Skype for Business angeschlossene analoge Geräte können keine Standortinformationen vom Standortinformationsdienst empfangen oder den Standort an den E9-1-1-Dienstanbieter übertragen.

 Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, stehen Ihnen zwei Optionen zur Verfügung:

- **Herkömmliche PS-ALI-Option** Wenn Sie an jedem Standort, an dem analoge Telefone bereitgestellt werden, über lokale PSTN-Gateways verfügen und jedes analoge Telefon über eine DID verfügt, können Sie den Standort des analogen Geräts direkt mit einem Ps-ALI-Dienstanbieter (Private Switch/Automatic Location Identification) bereitstellen. In diesem Fall konfigurieren Sie speziell gestaltete Skype for Business VoIP-Richtlinien und weisen sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter geleitet werden, der den Standort bedient (anstatt den Anruf an einen SIP-Trunk eines E9-1-1-Dienstanbieters weiterzuleiten). Wird ein Notruf getätigt, ordnet eine dem PSTN-Trunk zugewiesene Datenbank beim PS-ALI-Anbieter die DID jedes analogen Telefons einem physischen Standort zu und stellt diesen Standort der Rettungsleitstelle zur Verfügung. Diese Datensätze müssen beim PS-ALI-Dienstanbieter immer dann aktualisiert werden, wenn Telefone zu anderen ERLs verlegt werden.

- **E9-1-1-Dienstanbieteroption** Sie können die DIDs für analoge Telefone und die entsprechenden ERLs beim E9-1-1-Dienstanbieter registrieren, wenn dies vom E9-1-1-Dienstanbieter unterstützt wird. Wenn der Anbieter einen Anruf von Skype for Business Server erhält, der keine PIDF-LO-Daten enthält, kann der Anbieter sehen, ob eine Datenbankübersprechung für die DID-Nummer der aufrufenden Partei vorhanden ist. Mithilfe der aus der Datenbank abgerufenen ERL kann der Anbieter den Notruf automatisch an die richtige Rettungsleitstelle weiterleiten, und die PSAP erhält die DID des analogen Geräts und einen ESQK-Eintrag, mit dem der Verteiler den Standort des Anrufers suchen kann.

Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.

Aus Skype for Business Server Sicht kann der E9-1-1-Prozess in zwei Phasen unterteilt werden:

- Schritt 1: Abrufen eines Standorts

- Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch ermittelt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Ausführliche Informationen zu den möglichen Optionen finden Sie unter [Define the network elements used to determine location in Skype for Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Abrufen eines Standorts

In einer Skype for Business Server E9-1-1-Bereitstellung erhält jeder intern verbundene Skype for Business oder Lync Telefon Edition-Client aktiv seinen eigenen Standort. Nach der SIP-Registrierung stellt der Client alle Netzwerkkonnektivitätsinformationen bereit, die er über sich selbst kennt, in einer Standortanforderung an den Standortinformationsdienst, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server Datenbank unterstützt wird. Jeder zentrale Standortpool verfügt über einen Standortinformationsdienst, der die Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort abzufragen. Wenn eine Übereinstimmung vorliegt, gibt der Standortinformationsdienst einen Standort an den Client zurück. Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der Skype for Business Client enthält die PIDF-LO-Daten als Teil eines Notrufs, und diese Daten werden vom E9-1-1-Dienstanbieter verwendet, um die entsprechende PSAP zu ermitteln und den Anruf zusammen mit dem richtigen ESQK an diese PSAP weiterzuleiten, wodurch der PSAP-Verteiler den Standort des Anrufers abrufen kann.

Das folgende Diagramm zeigt, wie ein Skype for Business-Client einen Standort erwirbt (mit Ausnahme der mac-adressbasierten Standortmethode des Drittanbieterclients):

![So erwirbt der Client ein Standortdiagramm.](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Damit ein Client einen Standort abrufen kann, müssen die folgenden Schritte ausgeführt werden:

1. Der Administrator füllt die Standortinformationsdienst-Datenbank mit der Netzwerk-Wiremap (Tabellen, die verschiedene Typen von Netzwerkadressen den entsprechenden Notfall-Reaktionsstandorten (Emergency Response Locations, ERLs) zuordnen).

2. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, überprüft der Administrator die Teile der ERLs mit den allgemeinen Adressen anhand einer MSAG (Master Street Address Guide)-Datenbank, die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein ELIN-Gateway verwenden, stellt der Administrator sicher, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

3. Bei der Registrierung oder bei einer Netzwerkänderung sendet ein intern verbundener Client eine Standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.

4. Der Standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab und gibt, wenn eine Übereinstimmung gefunden wird, die ERL an den Client im PIDF-LO-Format zurück.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines SIP-Trunks

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1. Nähere Informationen zur Verwendung eines ELIN-Gateway zum Herstellen einer Verbindung mit einem Telefonfestnetzbasierten E9-1-1-Dienstanbieter finden Sie unter [Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an die Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Notrufweiterleitung von Lync Server zu PSAP.](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Wenn ein Notruf von einem kompatiblen Skype for Business Server-Client aus getätigt wird:

1. Eine SIP INVITE, die den Standort, die Rückrufnummer des Anrufers sowie die (optionale) Benachrichtigungs-URL und die Konferenzrückrufnummer enthält, wird an Skype for Business Server weitergeleitet.

2. Skype for Business Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der entsprechenden Standortrichtlinie definierten **PSTN-Verwendungswert)** an einen Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.

3. Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Skype for Business Sofortnachricht für Notfallbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirm(en) der Sicherheitsbeauftragten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Standort des Anrufers, sodass Sicherheitsmitarbeiter schnell mithilfe einer Chatnachricht oder Sprache auf den Notruf reagieren können.

5. Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6. Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines ELIN-Gateways

Einige Partner im Unified Communications Open Interoperability Program bieten qualifizierte ELIN (Emergency Location Identification Number)-fähige Gateways, die eine Alternative zu einer SIP-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter darstellen können. ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting )-Verbindungen mit E9-1-1-Diensten, die auf dem Telefonfestnetz (Public Switched Telephone Network, PSTN) basieren. Ausführliche Informationen zu Partnern, die ELIN-Gateways und Links zu ihrer Dokumentation bereitstellen, finden Sie unter ["Für Microsoft Lync qualifizierte Infrastruktur"](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) und ["Telefonieinfrastruktur für Skype for Business".](../../../SfbPartnerCertification/certification/infra-gateways.md)

Wie SIP-Trunkverbindungen mit E9-1-1-Dienstanbietern bieten auch ELIN-Gateways die Möglichkeit, einen Notruf an die am besten geeignete Rettungsleitstelle (Public Safety Answering Point, PSAP) des Anrufers weiterzuleiten, aber diese Gateways verwenden eine ELIN als Standort-ID. Sie definieren ELINs für jeden Notfallstandort (Emergency Response Location, ERL) in Ihrer Organisation (Ausführliche Informationen finden Sie unter [Verwalten von Standorten für ELIN-Gateways in Skype for Business Server).](elin-gateways.md)

Wenn Sie ein ELIN-Gateway für Notrufe verwenden, verwenden Sie dieselbe Skype for Business Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunkverbindung verwenden würden. Das heißt, die Standortinformationsdienstdatenbank stellt den Speicherort für den Skype for Business Client bereit, und die Standortrichtlinie aktiviert das Feature und definiert das Routing. Bei einem ELIN-Gateway müssen Sie die ELINs jedoch der Standortinformationsdienstdatenbank hinzufügen und ihren PSTN-Netzbetreiber in die ALI-Datenbank (Automatic Location Identification) hochladen lassen.

Wenn ein Skype for Business-Client seinen Standort vom Standortinformationsdienst abruft, enthält der Standort die ELIN. Bei einem Notruf ist die ELIN in dem Standort enthalten, der an das ELIN-Gateway gesendet wird. Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer der anrufenden Person durch die ELIN aus. Das ELIN-Gateway leitet den Anruf dann an das PSTN weiter, wobei die ELIN die Rufnummer ist. Der PSTN-Netzbetreiber für den E9-1-1-Dienst recherchiert die ELIN in der ALI-Datenbank, bei der es sich um eine ergänzende Datenbank der MSAG (Master Street Address Guide)-Datenbank handelt. Das PSTN sendet basierend auf der Recherche in der ALI-Datenbank den Anruf dann an eine geeignete Rettungsleitstelle, und die Rettungsleitstelle sendet basierend auf der Recherche in der ALI-Datenbank Einsatzgruppen zum Standort des Anrufers. Die Nummer, von der der Anruf stammt, wird für einen vordefinierten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen. Bei einem Rückruf kontaktiert die Rettungsleitstelle das ELIN-Gateway, von dem die ELIN mit der DID (Direct Inward Dialing)-Nummer des Anrufers ausgetauscht wird.

ELIN-Gateways unterstützen nur Notrufe innerhalb des Netzwerks Ihrer Organisation. Es werden keine Notrufe von außerhalb Ihres Netzwerks unterstützt.

> [!NOTE]
> Einzelheiten zur Verwendung einer SIP-Trunkverbindung für Notrufe finden Sie unter [Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an die Rettungsleitstelle weitergeleitet wird, wenn Sie ein ELIN-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen mit einem ELIN-Gateway**

![Zeigt, wie ein Anruf bei Notrufdiensten über den Vermittlungsserver und dann zum Notfalldienstanbieter weiter führt. Danach kann optional eine Chatnachricht an die Sicherheit vor Ort und/oder ein Rückruf an den ursprünglichen Aufrufer gesendet werden.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Eine SIP INVITE mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und Konferenzrückrufnummer wird an Skype for Business Server weitergeleitet.

2. Skype for Business Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der entsprechenden Standortrichtlinie definierten **PSTN-Verwendungswert)** an einen Vermittlungsserver und von dort an ein ELIN-Gateway weiter.

3. Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4. Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.

5. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Skype for Business Sofortnachricht für Notfallbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirm(en) der Sicherheitsbeauftragten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Standort des Anrufers, sodass Sicherheitsmitarbeiter schnell mithilfe einer Chatnachricht oder Sprache auf den Notruf reagieren können.

6. Wird der Anruf unterbrochen, verwendet die Rettungsleitstelle die ELIN, um den Anrufer direkt zu kontaktieren. Das ELIN-Gateway tauscht die ELIN durch die DID-Nummer des Anrufers aus.