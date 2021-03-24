---
title: Planen von Notrufdiensten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Erfahren Sie mehr über erweiterte 9-1-1(E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerb und Anrufrouting.
ms.openlocfilehash: d480a679367da4e8b6070c69127735b7ab59252d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101551"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planen von Notrufdiensten in Skype for Business Server

Erfahren Sie mehr über erweiterte 9-1-1(E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerb und Anrufrouting.

Skype for Business Server unterstützt erweiterte 9-1-1-Dienste (E9-1-1) innerhalb der USA als Teil einer Enterprise-VoIP Bereitstellung. E9-1-1 ist ein Notfallversandfeature, das einen 9-1-1-Anruf einem Notrufstandort (Emergency Response Location, ERL) zu ordnet, der aus öffentlichen (d. h. Straßen)-Adressen und anderen spezifischeren Standortinformationen besteht, z. B. Bodennummern, für Anrufe von Bürogebäuden und anderen mehrstufigen Einrichtungen. Mithilfe der bereitgestellten ERL kann ein Öffentlicher Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) sofort Erstbeantworter an den Anrufer in Not schicken, mit dem reduzierten Risiko, den Responder versehentlich an einen falschen oder mehrdeutigen Ort zu verweisen.

> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Weitere Informationen finden Sie [unter Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP: Anrufsteuerung, Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über Planungsinformationen, die allen drei dieser Features gemeinsam sind, finden Sie unter [Netzwerkeinstellungen](network-settings-for-advanced-features.md)für die erweiterten Enterprise-VoIP in Skype for Business Server .

Skype for Business Server unterstützt erweiterte 9-1-1-Anrufe (E9-1-1) von Skype for Business-Clients und Lync Phone Edition-Geräten. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business oder Lync Phone Edition ausgeführt werden, Informationen zum Notfallansprechort (Emergency Response Location, ERL) aus der Standortinformationsdienstdatenbank. ErLs bestehen aus öffentlichen Adressen (d. h. Straßenadressen) und anderen Informationen, die helfen, einen genaueren Standort in Bürogebäuden und anderen mehrstufigen Einrichtungen zu identifizieren. Wenn ein Benutzer einen Notruf abruft, leitet Skype for Business Server den Anrufaudio zusammen mit den Standort- und Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Dienstanbieter weiter. Der E9-1-1-Dienstanbieter verwendet die bürgerschaftliche Adresse des Anrufers, um den Anruf an den öffentlichen Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) weiter zu leitet, der den Anruferstandort bedient, und sendet einen Notrufabfrageschlüssel (Emergency Service Query Key, ESQK), den das PSAP zum Suchen der ERL des Anrufers verwendet.

Skype for Business Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:

- Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

- Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, fügen Sie der Standortinformationsdienstdatenbank ERLs hinzu, und überprüfen Sie die Standorte anhand eines Master Street Address Guide (MSAG), der vom E9-1-1-1-Dienstanbieter verwaltet wird. Wenn ein E9-1-1-Dienstanbieter einen Anruf empfängt, der über keine Standortinformationen verfügt oder über einen Standort verfügt, der nicht mit der MSAG überprüft wurde, leitet der E9-1-1-Dienstanbieter den Anruf an ein nationales/regionales Emergency Call Response Center (ECRC) weiter, das mit speziell geschultem Personal besetzt ist, das den Anruferstandort nach Möglichkeit mündlich abruft und den Anruf manuell an das entsprechende PSAP weiter leitet. (Einige SIP-Trunk-E9-1-1-Dienstanbieter stellen Kunden auch eine PSTN-Direktwahlnummer (Direct InWard Dialing, DID) an das ECRC zur Verfügung, die eine alternative Möglichkeit zum Routing von 9-1-1-Anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund ausfällt.)

Im Gegensatz zu TdM(Time Division Multiplexing) und IP-basierten Nebenstellentelefonen (Private Branch Exchange, PBX) mit festen Standorten kann ein Skype for Business-Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, trägt Skype for Business Server dazu bei, sicherzustellen, dass der Notruf unabhängig davon, wo sich ein Anrufer befindet, an das PSAP umgeschaltet werden kann, das den Anruferstandort bedient. Wenn sich beispielsweise die Hauptniederlassung eines Benutzers in Redmond, Washington befindet, der Benutzer jedoch einen Notruf von einem Computer in einer Zweigstelle in Wichita, Kansas, abbricht, wird der Anruf vom SIP-Trunk oder vom PSTN-basierten E9-1-1-1-Dienstanbieter an die PSAP in Wichita und nicht an das PSAP in Redmond weitergeroutet.

Wenn Sie ein ELIN-Gateway verwenden, fügen Sie der Standortinformationsdienstdatenbank auch ERLs hinzu, fügen jedoch auch eine ELIN-Nummer für jeden Standort hinzu. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

> [!NOTE]
> Mit Skype for Business verbundene analoge Geräte können keine Standortinformationen vom Standortinformationsdienst empfangen oder den Standort an den E9-1-1-Dienstanbieter übertragen.

 Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, stehen Ihnen zwei Optionen zur Verfügung:

- **Herkömmliche PS-ALI-Option** Wenn Sie über lokale PSTN-Gateways an jedem Standort verfügen, an dem analoge Telefone bereitgestellt werden und jedes analoge Telefon über ein DID verfügt, können Sie den Standort des analogen Geräts direkt mit einem Ps-ALI(Private Switch/Automatic Location Identification)-Dienstanbieter bereitstellen. In diesem Fall konfigurieren Sie speziell gestaltete Skype for Business-Voicerichtlinien und weisen sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter, der den Standort verarbeitet, weiterleiten (anstatt den Anruf an einen E9-1-1-Dienstanbieter-SIP-Trunk weiter zu weiterleiten). Wird ein Notruf getätigt, ordnet eine dem PSTN-Trunk zugewiesene Datenbank beim PS-ALI-Anbieter die DID jedes analogen Telefons einem physischen Standort zu und stellt diesen Standort der Rettungsleitstelle zur Verfügung. Diese Datensätze müssen beim PS-ALI-Dienstanbieter immer dann aktualisiert werden, wenn Telefone zu anderen ERLs verlegt werden.

- **E9-1-1-Dienstanbieteroption** Sie können die analogen Telefon-DIDs und die entsprechenden ERLs beim E9-1-1-Dienstanbieter registrieren, wenn dies vom E9-1-1-Dienstanbieter unterstützt wird. Wenn der Anbieter einen Anruf von Skype for Business Server empfängt, der keine PIDF-LO-Daten enthält, kann der Anbieter sehen, ob eine Datenbank übereinstimmung für die DID-Nummer des Anrufers vorhanden ist. Mithilfe der aus der Datenbank abgerufenen ERL kann der Anbieter den Notruf automatisch an das richtige PSAP weiterführen, und die PSAP erhält die DID des analogen Geräts und einen ESQK-Eintrag, mit dem der Disponent den Standort des Anrufers suchen kann.

Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.

Aus Sicht von Skype for Business Server kann der E9-1-1-Prozess in zwei Phasen unterteilt werden:

- Schritt 1: Abrufen eines Standorts

- Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch ermittelt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Weitere Informationen zu den möglichen Optionen finden Sie unter [Define the network elements used to determine location in Skype for Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Abrufen eines Standorts

In einer Skype for Business Server E9-1-1-Bereitstellung erwirbt jeder intern verbundene Skype for Business- oder Lync Phone Edition-Client aktiv einen eigenen Standort. Nach der SIP-Registrierung gibt der Client alle Netzwerkverbindungsinformationen an, die er über sich selbst kennt, in einer Standortanforderung an den Standortinformationsdienst, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server wird. Jeder zentrale Standortpool verfügt über einen Standortinformationsdienst, der die Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort zu abfragen. Wenn eine Übereinstimmung vorkommt, gibt der Standortinformationsdienst einen Speicherort an den Client zurück. Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der Skype for Business-Client enthält die PIDF-LO-Daten als Teil eines Notrufs, und diese Daten werden vom E9-1-1-Dienstanbieter verwendet, um das entsprechende PSAP zu ermitteln und den Anruf zusammen mit dem richtigen ESQK an diese PSAP weiter zu routen, wodurch der PSAP-Disponent den Standort des Anrufers abrufen kann.

Das folgende Diagramm zeigt, wie ein Skype for Business-Client einen Standort erwirbt (mit Ausnahme der adressbasierten Standortmethode des Drittanbieterclients):

![So erwirbt der Client ein Standortdiagramm](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Damit ein Client einen Standort abrufen kann, müssen die folgenden Schritte ausgeführt werden:

1. Der Administrator füllt die Standortinformationsdienstdatenbank mit der Netzwerk-Drahtkarte auf (Tabellen, die verschiedene Arten von Netzwerkadressen den entsprechenden Notfallreaktionsspeicherorten (Emergency Response Locations, ERLs) zuordnungen.

2. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, überprüft der Administrator die Teile der ERLs mit den allgemeinen Adressen anhand einer MSAG (Master Street Address Guide)-Datenbank, die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein ELIN-Gateway verwenden, stellt der Administrator sicher, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

3. Während der Registrierung oder immer dann, wenn eine Netzwerkänderung auftritt, sendet ein intern verbundener Client eine Standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.

4. Der Standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab und gibt, wenn eine Übereinstimmung gefunden wird, die ERL an den Client im PIDF-LO-Format zurück.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines SIP-Trunks

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1. Nähere Informationen zur Verwendung eines ELIN-Gateway zum Herstellen einer Verbindung mit einem Telefonfestnetzbasierten E9-1-1-Dienstanbieter finden Sie unter [Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an den öffentlichen Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) geroutet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Routing von Notrufen von Lync Server zu PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Wenn ein Notruf von einem kompatiblen Skype for Business Server-Client abgeschaltet wird:

1. Eine SIP-EINLADUNG, die den Standort, die Rückrufnummer des Anrufers sowie die (optionale) Benachrichtigungs-URL und die Konferenzrückrufnummer enthält, wird an Skype for Business Server geroutet.

2. Skype for Business Server entspricht der Notrufnummer  und leitet den Anruf (basierend auf dem in der entsprechenden Standortrichtlinie definierten PSTN-Nutzungswert) an einen Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.

3. Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für Skype for Business-Notfallbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirmen der Sicherheitsbeamten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Ort des Anrufers, sodass Sicherheitsmitarbeiter mithilfe einer Sofortnachricht oder Einer-Sprache schnell auf den Notrufer reagieren können.

5. Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6. Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines ELIN-Gateways

Einige Partner im Unified Communications Open Interoperability Program bieten qualifizierte ELIN (Emergency Location Identification Number)-fähige Gateways, die eine Alternative zu einer SIP-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter darstellen können. ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting )-Verbindungen mit E9-1-1-Diensten, die auf dem Telefonfestnetz (Public Switched Telephone Network, PSTN) basieren. Ausführliche Informationen zu Partnern, die ELIN-Gateways und Links zu ihrer Dokumentation bereitstellen, finden Sie unter [Infrastructure qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) and Telephony Infrastructure for Skype for [Business](../../../SfbPartnerCertification/certification/infra-gateways.md).

Wie SIP-Trunkverbindungen zu E9-1-1-Dienstanbietern bieten AUCH ELIN-Gateways die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) des Anrufers weiter zu weiterleiten, aber diese Gateways verwenden ein ELIN als Standort-ID. Sie definieren ELINs für jeden Notfallstandort (Emergency Response Location, ERL) in Ihrer Organisation (Weitere Informationen finden Sie unter [Manage locations for ELIN gateways in Skype for Business Server](elin-gateways.md)).

Wenn Sie ein ELIN-Gateway für Notrufe verwenden, verwenden Sie dieselbe Skype for Business Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunkverbindung verwenden würden. Das heißt, die Standortinformationsdienstdatenbank stellt den Speicherort für den Skype for Business-Client zur Verfügung, und die Standortrichtlinie aktiviert das Feature und definiert das Routing. Bei einem ELIN-Gateway müssen Sie die ELINs jedoch der Standortinformationsdienstdatenbank hinzufügen und von Ihrem PSTN-Netzbetreiber in die Datenbank für die automatische Standortidentifizierung (Automatic Location Identification, ALI) hochladen lassen.

Wenn ein Skype for Business-Client seinen Standort vom Standortinformationsdienst erhält, enthält der Standort das ELIN. Bei einem Notruf ist die ELIN in dem Standort enthalten, der an das ELIN-Gateway gesendet wird. Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer der anrufenden Person durch die ELIN aus. Das ELIN-Gateway leitet den Anruf dann an das PSTN weiter, wobei die ELIN die Rufnummer ist. Der PSTN-Netzbetreiber für den E9-1-1-Dienst recherchiert die ELIN in der ALI-Datenbank, bei der es sich um eine ergänzende Datenbank der MSAG (Master Street Address Guide)-Datenbank handelt. Das PSTN sendet basierend auf der Recherche in der ALI-Datenbank den Anruf dann an eine geeignete Rettungsleitstelle, und die Rettungsleitstelle sendet basierend auf der Recherche in der ALI-Datenbank Einsatzgruppen zum Standort des Anrufers. Die Nummer, von der der Anruf stammt, wird für einen vordefinierten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen. Bei einem Rückruf kontaktiert die Rettungsleitstelle das ELIN-Gateway, von dem die ELIN mit der DID (Direct Inward Dialing)-Nummer des Anrufers ausgetauscht wird.

ELIN-Gateways unterstützen nur Notrufe innerhalb des Netzwerks Ihrer Organisation. Es werden keine Notrufe von außerhalb Ihres Netzwerks unterstützt.

> [!NOTE]
> Einzelheiten zur Verwendung einer SIP-Trunkverbindung für Notrufe finden Sie unter [Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an die PSAP geroutet wird, wenn Sie ein ELIN-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen mit einem ELIN-Gateway**

![Zeigt, wie ein Notruf über den Vermittlungsserver und dann zum Notrufanbieter geht. Danach kann optional ein Anrufer an die Sicherheit vor Ort und/oder ein Rückruf an den ursprünglichen Anrufer gesendet werden.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Eine SIP-EINLADUNG, die den Standort, die Rückrufnummer des Anrufers sowie die (optionale) Benachrichtigungs-URL und die Konferenzrückrufnummer enthält, wird an Skype for Business Server geroutet.

2. Skype for Business Server entspricht der Notrufnummer und leitet den Anruf (basierend auf dem in der geltenden Standortrichtlinie definierten **PSTN-Nutzungswert)** an einen Vermittlungsserver und von dort an ein ELIN-Gateway weiter.

3. Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4. Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.

5. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für Skype for Business-Notfallbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirmen der Sicherheitsbeamten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Ort des Anrufers, sodass Sicherheitsmitarbeiter mithilfe einer Sofortnachricht oder Einer-Sprache schnell auf den Notrufer reagieren können.

6. Wird der Anruf unterbrochen, verwendet die Rettungsleitstelle die ELIN, um den Anrufer direkt zu kontaktieren. Das ELIN-Gateway tauscht die ELIN durch die DID-Nummer des Anrufers aus.