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
description: Erfahren Sie mehr über erweiterte 9-1-1-Dienste (E9-1-1) in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerb und Anrufrouting.
ms.openlocfilehash: e8eb805a4e4d55f08a4c6aec1a57618c74bcfa02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825765"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planen von Notrufdiensten in Skype for Business Server

Erfahren Sie mehr über erweiterte 9-1-1-Dienste (E9-1-1) in Skype for Business Server Enterprise-VoIP, einschließlich Standorterwerb und Anrufrouting.

Skype for Business Server unterstützt erweiterte 9-1-1-Dienste (E9-1-1) innerhalb der USA im Rahmen einer Enterprise-VoIP Bereitstellung. E9-1-1 ist eine Notfallverteilerfunktion, die einen 9-1-1-Anruf einem Notrufstandort (Emergency Response Location, ERL) zu ordnet, der aus ortsspezifischen (d. h. Straße)-Adressen und anderen spezifischeren Standortinformationen, z. B. Grundnummern, für Anrufe aus Bürogebäuden und anderen mehrstufigen Einrichtungen besteht. Mithilfe der bereitgestellten ERL kann eine Öffentliche Sicherheits-Antwortstelle (Public Safety Answering Point, PSAP) sofort Erstantworten an den Anrufer in Notrufen mit reduziertem Risiko versenden, dass der Antwortdienst versehentlich an einen falschen oder mehrdeutigen Standort umgedeutet wird.

> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Weitere Informationen finden Sie unter [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP: Anrufsteuerung, Notrufdienste (E9-1-1) und Medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Features verwendet werden, finden Sie unter "Netzwerkeinstellungen" für die erweiterten Enterprise-VoIP [in Skype for Business Server.](network-settings-for-advanced-features.md)

Skype for Business Server unterstützt anrufe mit erweiterten 9-1-1 -Geräten (E9-1-1) von Skype for Business-Clients und Lync Phone Edition-Geräten. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business oder Lync Phone Edition ausgeführt werden, ErL(Emergency Response Location)-Informationen aus der Datenbank des Standortinformationsdiensts. ErLs bestehen aus anschriftlichen Adressen (d. h. Straßenadressen) und anderen Informationen, mit deren Hilfe sie einen genaueren Standort in Bürogebäuden und anderen mehrstufigen Einrichtungen identifizieren können. Wenn ein Benutzer einen Notruf abruft, leitet Skype for Business Server die Anrufaudiodaten zusammen mit den Standort- und Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Dienstanbieter weiter. Der E9-1-1-Dienstanbieter verwendet die anschriftliche Adresse des Anrufers, um den Anruf an die Rettungsstelle (Public Safety Answering Point, PSAP) weiter zu leitet, die den Standort des Anrufers bedient, und sendet einen Notrufabfrageschlüssel (Emergency Service Query Key, ESQK), den die Rettungsstelle zum Nachschauen der ERL des Anrufers verwendet.

Skype for Business Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:

- Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

- Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, fügen Sie der Standortinformationsdienstdatenbank ERLs hinzu und überprüfen dann die Standorte anhand einer Master Street Address Guide (MSAG), die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn ein E9-1-1-Dienstanbieter einen Anruf empfängt, der über keine Standortinformationen verfügt oder über einen Standort verfügt, der nicht anhand der MSAG überprüft wurde, leitet der E9-1-1-Dienstanbieter den Anruf an ein nationales/regionales EcRC (Emergency Call Response Center) weiter, das mit speziell geschulten Mitarbeitern besetzt ist, die den Standort des Anrufers nach Möglichkeit erhalten und den Anruf manuell an die entsprechende Rettungsstelle weiterführen. (Einige SIP-Trunk-E9-1-1-Dienstanbieter stellen Kunden auch eine PSTN Direct Inward Dialing (DID)-Nummer an das ECRC zur Verfügung, die eine alternative Möglichkeit zum Weiterleiten von 9-1-1-Anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund ausfällt.)

Im Gegensatz zu TDM-Telefonen (Time Division Multiplexing) und IP-basierten Nebenstellentelefonen (Private Branch Exchange, PBX), die feste Standorte haben, kann ein Skype for Business-Endpunkt sehr mobil sein. Wenn Sie die E9-1-1-Funktion bereitstellen, hilft Skype for Business Server sicherzustellen, dass der Notruf unabhängig davon, wo sich ein Anrufer befindet, an die Rettungsstelle geroutet werden kann, die den Standort des Anrufers bedient. Wenn sich beispielsweise das Hauptbüro eines Benutzers in Redmond, Washington, befindet, der Benutzer jedoch einen Notruf von einem Computer in einer Filiale in Wichita, Seattle, abbricht, wird der Anruf vom SIP-Trunk- oder PSTN-basierten E9-1-1-Dienstanbieter an die Rettungsstelle in Wichita und nicht an die Rettungsstelle in Redmond geroutet.

Wenn Sie ein ELIN-Gateway verwenden, fügen Sie der Standortinformationsdienstdatenbank auch ERLs hinzu, fügen jedoch auch eine ELIN-Nummer für jeden Standort hinzu. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

> [!NOTE]
> Mit Skype for Business verbundene analoge Geräte können keine Standortinformationen vom Standortinformationsdienst empfangen oder den Standort an den E9-1-1-Dienstanbieter übertragen.

 Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, stehen Ihnen zwei Optionen zur Verfügung:

- **Herkömmliche PS-ALI-Option** Wenn Sie über lokale Festnetzgateways an jedem Standort verfügen, an dem analoge Telefone bereitgestellt werden, und jedes analoge Telefon über ein DID verfügt, können Sie den Standort des analogen Geräts direkt mit einem Dienstanbieter für private Switch-/Automatische Standortidentifikation (PS-ALI) bereitstellen. In diesem Fall konfigurieren Sie speziell gestaltete Skype for Business-Voice-Richtlinien und weisen sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter, der den Standort verarbeitet, (anstatt den Anruf an einen E9-1-1-Dienstanbieter-SIP-Trunk weiterleite). Wird ein Notruf getätigt, ordnet eine dem PSTN-Trunk zugewiesene Datenbank beim PS-ALI-Anbieter die DID jedes analogen Telefons einem physischen Standort zu und stellt diesen Standort der Rettungsleitstelle zur Verfügung. Diese Datensätze müssen beim PS-ALI-Dienstanbieter immer dann aktualisiert werden, wenn Telefone zu anderen ERLs verlegt werden.

- **E9-1-1-Dienstanbieteroption** Sie können die DIDs für analoge Telefone und die entsprechenden ERLs beim E9-1-1-Dienstanbieter registrieren, sofern dies vom E9-1-1-Dienstanbieter unterstützt wird. Wenn der Anbieter einen Anruf von Skype for Business Server empfängt, der keine PIDF-LO-Daten enthält, kann der Anbieter sehen, ob eine Datenbank übereinstimmung mit der DID-Nummer des Anrufers vorhanden ist. Mithilfe der aus der Datenbank abgerufenen ERL kann der Anbieter den Notruf automatisch an die richtige Rettungsstelle weiterführen, und die Rettungsstelle erhält die DID des analogen Geräts und einen ESQK-Eintrag, mit dem der Verteiler den Standort des Anrufers suchen kann.

Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.

Aus Sicht von Skype for Business Server kann der E9-1-1-Prozess in zwei Phasen unterteilt werden:

- Schritt 1: Abrufen eines Standorts

- Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch ermittelt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Weitere Informationen zu den möglichen Optionen finden Sie unter Definieren der Netzwerkelemente, die zum [Bestimmen des Standorts in Skype for Business Server verwendet werden.](network-location.md)

## <a name="acquiring-a-location"></a>Abrufen eines Standorts

In einer Skype for Business Server E9-1-1-Bereitstellung erwirbt jeder intern verbundene Skype for Business- oder Lync Phone Edition-Client aktiv einen eigenen Standort. Nach der SIP-Registrierung gibt der Client alle Netzwerkverbindungsinformationen, die er über sich selbst kennt, in einer Standortanforderung an den Standortinformationsdienst an, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server wird. Jeder zentrale Standortpool verfügt über einen Standortinformationsdienst, der die Netzwerkinformationen verwendet, um die Datensätze nach einem übereinstimmenden Standort zu abfragen. Wenn eine Übereinstimmung vorkommt, gibt der Standortinformationsdienst einen Standort an den Client zurück. Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der Skype for Business-Client enthält die PIDF-LO-Daten als Teil eines Notrufs. Diese Daten werden vom E9-1-1-Dienstanbieter verwendet, um die entsprechende Rettungsstelle zu ermitteln und den Anruf zusammen mit dem richtigen ESQK an diese Rettungsstelle weiter zu routen, wodurch der Rettungsdienst den Standort des Anrufers abrufen kann.

Das folgende Diagramm zeigt, wie ein Skype for Business-Client einen Standort erwirbt (mit Ausnahme der adressebasierten Standortmethode des Client-MAC eines Drittanbieters):

![So erwirbt der Client ein Standortdiagramm](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Damit ein Client einen Standort abrufen kann, müssen die folgenden Schritte ausgeführt werden:

1. Der Administrator füllt die Standortinformationsdienstdatenbank mit der Netzwerk-Wiremap auf (Tabellen, die verschiedene Arten von Netzwerkadressen entsprechenden Notfallreaktionsstandorten (Emergency Response Locations, ERLs) enstellen.

2. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, überprüft der Administrator die Teile der ERLs mit den allgemeinen Adressen anhand einer MSAG (Master Street Address Guide)-Datenbank, die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein ELIN-Gateway verwenden, stellt der Administrator sicher, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

3. Während der Registrierung oder bei jeder Netzwerkänderung sendet ein intern verbundener Client eine Standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.

4. Der Standortinformationsdienst fragt die veröffentlichten Datensätze nach einem Speicherort ab und gibt, wenn eine Übereinstimmung gefunden wird, die ERL im PIDF-LO-Format an den Client zurück.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines SIP-Trunks

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1. Nähere Informationen zur Verwendung eines ELIN-Gateway zum Herstellen einer Verbindung mit einem Telefonfestnetzbasierten E9-1-1-Dienstanbieter finden Sie unter [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an die Rettungsstelle (Public Safety Answering Point, PSAP) geroutet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Routing von Notrufen von Lync Server zu PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Wenn ein Notruf von einem kompatiblen Skype for Business Server-Client abgeschaltet wird:

1. Eine SIP INVITE, die den Standort, die Rückrufnummer des Anrufers sowie (optional) die Benachrichtigungs-URL und die Konferenzrückrufnummer enthält, wird an Skype for Business Server geroutet.

2. Skype for Business Server entspricht der Notrufnummer  und leitet den Anruf (basierend auf dem in der anwendbaren Standortrichtlinie definierten Wert für die Festnetznutzung) an einen Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.

3. Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für Skype for Business-Notrufbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirmen der Sicherheitsbeauftragten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Standort des Anrufers, sodass das Sicherheitspersonal mithilfe einer Sofortnachricht oder Sprachnachricht schnell auf den Notruf reagieren kann.

5. Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6. Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Weiterleiten von E9-1-1-Anrufen mithilfe eines ELIN-Gateways

Einige Partner im Unified Communications Open Interoperability Program bieten qualifizierte ELIN (Emergency Location Identification Number)-fähige Gateways, die eine Alternative zu einer SIP-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter darstellen können. ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting )-Verbindungen mit E9-1-1-Diensten, die auf dem Telefonfestnetz (Public Switched Telephone Network, PSTN) basieren. Ausführliche Informationen zu Partnern, die ELIN-Gateways und Links zu ihrer Dokumentation bereitstellen, finden Sie unter ["Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=248425) für Microsoft Lync und Telefonieinfrastruktur [für Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)

Wie SIP-Trunk-Verbindungen mit E9-1-1-Dienstanbietern bieten auch ELIN-Gateways die Möglichkeit, einen Notruf an die am besten geeignete Rettungsleitstelle (Public Safety Answering Point, PSAP) des Anrufers weiter zu routen, diese Gateways verwenden jedoch eine ELIN als Standort-ID. Sie definieren ELINs für jeden Notfallstandort (Emergency Response Location, ERL) in Ihrer Organisation (Weitere Informationen finden Sie unter "Verwalten von Standorten für [ELIN-Gateways in Skype for Business Server").](elin-gateways.md)

Wenn Sie ein ELIN-Gateway für Notrufe verwenden, verwenden Sie dieselbe Skype for Business Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunk-Verbindung verwenden würden. Das heißt, die Standortinformationsdienstdatenbank stellt den Standort für den Skype for Business-Client zur Verfügung, und die Standortrichtlinie aktiviert die Funktion und definiert das Routing. Bei einem ELIN-Gateway müssen Sie die ELINs jedoch der Standortinformationsdienstdatenbank hinzufügen und von Ihrem Netzbetreiber in die ALI (Automatic Location Identification)-Datenbank hochladen lassen.

Wenn ein Skype for Business-Client seinen Standort vom Standortinformationsdienst erhält, enthält der Standort die ELIN. Bei einem Notruf ist die ELIN in dem Standort enthalten, der an das ELIN-Gateway gesendet wird. Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer der anrufenden Person durch die ELIN aus. Das ELIN-Gateway leitet den Anruf dann an das PSTN weiter, wobei die ELIN die Rufnummer ist. Der PSTN-Netzbetreiber für den E9-1-1-Dienst recherchiert die ELIN in der ALI-Datenbank, bei der es sich um eine ergänzende Datenbank der MSAG (Master Street Address Guide)-Datenbank handelt. Das PSTN sendet basierend auf der Recherche in der ALI-Datenbank den Anruf dann an eine geeignete Rettungsleitstelle, und die Rettungsleitstelle sendet basierend auf der Recherche in der ALI-Datenbank Einsatzgruppen zum Standort des Anrufers. Die Nummer, von der der Anruf stammt, wird für einen vordefinierten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen. Bei einem Rückruf kontaktiert die Rettungsleitstelle das ELIN-Gateway, von dem die ELIN mit der DID (Direct Inward Dialing)-Nummer des Anrufers ausgetauscht wird.

ELIN-Gateways unterstützen nur Notrufe innerhalb des Netzwerks Ihrer Organisation. Es werden keine Notrufe von außerhalb Ihres Netzwerks unterstützt.

> [!NOTE]
> Einzelheiten zur Verwendung einer SIP-Trunkverbindung für Notrufe finden Sie unter [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Das folgende Diagramm zeigt, wie ein Notruf von Skype for Business Server an die RETTUNGSAP geroutet wird, wenn Sie ein ELIN-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen mit einem ELIN-Gateway**

![Zeigt, wie ein Notruf über den Vermittlungsserver und dann zum Anbieter der Notrufdienste weiter geht. Danach kann optional ein Anrufer an die Sicherheit vor Ort und/oder ein Rückruf an den ursprünglichen Anrufer gesendet werden.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Eine SIP INVITE mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und Konferenzrückrufnummer wird an Skype for Business Server geroutet.

2. Skype for Business Server entspricht der Notrufnummer und  leitet den Anruf (basierend auf dem in der anwendbaren Standortrichtlinie definierten Wert für die Festnetznutzung) an einen Vermittlungsserver und von dort an ein ELIN-Gateway weiter.

3. Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4. Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.

5. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, wird einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für Skype for Business-Notrufbenachrichtigungen gesendet. Diese Nachricht wird immer auf den Bildschirmen der Sicherheitsbeauftragten angezeigt und enthält den Namen, die Telefonnummer, die Uhrzeit und den Standort des Anrufers, sodass das Sicherheitspersonal mithilfe einer Sofortnachricht oder Sprachnachricht schnell auf den Notruf reagieren kann.

6. Wird der Anruf unterbrochen, verwendet die Rettungsleitstelle die ELIN, um den Anrufer direkt zu kontaktieren. Das ELIN-Gateway tauscht die ELIN durch die DID-Nummer des Anrufers aus.


