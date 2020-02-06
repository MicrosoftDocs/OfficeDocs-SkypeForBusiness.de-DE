---
title: Planen von Notfalldiensten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Erfahren Sie mehr über erweiterte 9-1-1 (E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterfassung und Anrufweiterleitung.
ms.openlocfilehash: f09729bc6fdbd2fa64dee5b30af88494cd618915
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802985"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planen von Notfalldiensten in Skype for Business Server

Erfahren Sie mehr über erweiterte 9-1-1 (E9-1-1)-Dienste in Skype for Business Server Enterprise-VoIP, einschließlich Standorterfassung und Anrufweiterleitung.

Skype for Business Server unterstützt erweiterte 9-1-1 (E9-1-1)-Dienste in den Vereinigten Staaten als Teil einer Enterprise-VoIP-Bereitstellung. E9-1-1 ist ein Notfall-Dispatch-Feature, das einen 9-1-1-Anruf mit einem Emergency Response Location (ERL) verknüpft, der aus bürgerlichen (also Straßen-) Adressen und anderen spezifischeren Standortinformationen wie Floor-Nummern für Anrufe von Bürogebäuden besteht. und andere Multitenant-Anlagen. Durch Verwendung des bereitgestellten Erl kann ein öffentlicher Sicherheits Beantwortungs Punkt (PSAP) sofort Antworten an den Anrufer in Seenot senden, wobei das Risiko verringert wird, dass der Responder versehentlich an eine falsche oder mehrdeutige Position geleitet wird.

> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Weitere Informationen finden Sie unter [Planen mehrerer Notrufnummern in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung, Notfalldienste (E9-1-1) und medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Features üblich sind, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](network-settings-for-advanced-features.md).

Skype for Business Server unterstützt erweiterte 9-1-1 (E9-1-1)-Anrufe von Skype for Business-Clients und lync Phone Edition-Geräten. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, beinhalten Notrufe, die von Skype for Business oder lync Phone Edition getätigt werden, die Informationen zum Emergency Response Location (ERL) aus der Datenbank des Standort Informationsdiensts. ERLs bestehen aus bürgerlichen (also Straßen-) Adressen und anderen Informationen, die dazu beitragen, eine genauere Position in Bürogebäuden und anderen Multitenant-Anlagen zu erkennen. Wenn ein Benutzer einen Notruf tätigt, leitet der Skype for Business-Server den Audioanruf zusammen mit dem Standort und den Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Service-Anbieter weiter. Der E9-1-1-Service-Anbieter verwendet die bürgerliche Adresse des Anrufers, um den Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterzuleiten, der dem Aufenthaltsort des Anrufers dient, und sendet einen Notfall-Service-Abfrage Schlüssel (ESQK), den der PSAP verwendet, um den Erl des Anrufers nachschlagen zu können.

Skype for Business Server unterstützt zwei Methoden zum Routing von Notrufen an einen E9-1-1-Service-Anbieter:

- Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

- Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP Trunk E9-1-1 Dienstanbieter verwenden, fügen Sie ERLs der Datenbank des Standort Informationsdiensts hinzu, und überprüfen Sie dann die Speicherorte mit einem Master Street Address Guide (MSAG), der vom E9-1-1-Dienstanbieter verwaltet wird. Wenn ein Dienstanbieter E9-1-1 einen Anruf empfängt, der keine Standortinformationen hat oder einen Speicherort aufweist, der nicht mit dem MSAG überprüft wurde, der E9-1-1-Service-Anbieter leitet den Anruf an ein nationales/regionales Notruf Center (ECRC) weiter, das mit speziell geschulten Mitarbeitern besetzt ist, die den Standort des Anrufers, wenn möglich, verbal abrufen und den Anruf manuell an die entsprechende PSAP weiterleiten. (Einige SIP Trunk E9-1-1-Service-Anbieter bieten Kunden auch eine direkte PSTN-Wählnummer (DID) an den ECRC, die ein alternatives Mittel zur Weiterleitung von 9-1-1-anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund fehlschlägt.)

Im Gegensatz zu Time Division Multiplexing (TDM) und IP-basierter PBX-Telefone (Private Branch Exchange), die über feste Standorte verfügen, kann ein Skype for Business-Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, hilft Skype for Business Server dabei, sicherzustellen, dass der Notruf unabhängig von der Position des Anrufers an die PSAP weitergeleitet werden kann, die dem Aufenthaltsort des Anrufers dient. Wenn sich beispielsweise die Hauptniederlassung eines Benutzers in Redmond, Washington befindet, der Benutzer aber einen Notruf von einem Computer in einer Zweigniederlassung in Wichita, Kansas durchführt, leitet der SIP Trunk oder der PSTN-basierte E9-1-1-Dienstanbieter den Anruf an das PSAP in Wichita weiter. , nicht auf die PSAP in Redmond.

Wenn Sie ein Elin-Gateway verwenden, fügen Sie auch ERLs der Datenbank des Standort Informationsdiensts hinzu, Sie schließen aber auch eine Elin-Nummer für jede Position ein. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI-Datenbank (Automatic Location Identification, automatische Standortidentifizierung) hochlädt.

> [!NOTE]
> Skype for Business-angeschlossene analoge Geräte können keine Standortinformationen vom standortinformationsdienst empfangen oder den Standort an den E9-1-1-Service-Anbieter übertragen.

 Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und E9-1-1 über analoge Telefone unterstützen müssen, stehen Ihnen zwei Optionen zur Verfügung:

- **Traditionelle PS-Ali-Option** Wenn Sie an jedem Standort, an dem analoge Telefone bereitgestellt werden, über lokale PSTN-Gateways verfügen und jedes analoge Telefon eine did hat, können Sie den Standort des analogen Geräts direkt mit einem privaten Switch/Automatic Location Identification (PS-Ali)-Dienstanbieter bereitstellen. In diesem Fall konfigurieren Sie speziell gestaltete Skype for Business-VoIP-Richtlinien und weisen Sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter weiterleiten, der die Website (stattdessen der Weiterleitung des Anrufs an einen E9-1-1-Service-Anbieter-SIP-Trunk). Wenn ein Notruf erfolgt, ordnet eine Datenbank bei einem PS-Ali-Anbieter, der dem PSTN-trunk zugeordnet ist, die did-Daten jedes analogen Telefons einem physikalischen Standort zu und stellt diesen Standort dem PSAP zur Verfügung. Diese Einträge müssen mit dem PS-Ali-Dienstanbieter jedes Mal aktualisiert werden, wenn Telefone in andere ERLs verschoben werden.

- **E9-1-1 Service Provider-Option** Sie können die analoge Telefon DIDs und deren zugehörige ERLs mit dem E9-1-1-Dienstanbieter registrieren, wenn dieser vom Dienstanbieter E9-1-1 unterstützt wird. Wenn der Anbieter einen Anruf von Skype for Business Server erhält, der keine PIDF-Lo-Daten enthält, kann der Anbieter sehen, ob auf der DID-Nummer des anrufenden eine Daten Bank Entsprechung vorhanden ist. Durch Verwendung des Erl, das aus seiner Datenbank abgerufen wurde, kann der Anbieter den Notruf automatisch an die richtige PSAP weiterleiten, und der PSAP empfängt die did des analogen Geräts und einen ESQK-Eintrag, der es dem Dispatcher ermöglicht, den Standort des Anrufers nachzuschlagen.

Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.

Aus der Perspektive eines Skype for Business-Servers kann der E9-1-1-Prozess in zwei Phasen aufgeteilt werden:

- Schritt 1: Abrufen eines Standorts

- Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch erkannt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Details zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in Skype for Business Server verwendet](network-location.md)werden.

## <a name="acquiring-a-location"></a>Abrufen eines Standorts

In einer Skype for Business Server E9-1-1-Bereitstellung erwirbt jeder intern angeschlossene Skype for Business-oder lync Phone Edition-Client aktiv seinen eigenen Standort. Nach der SIP-Registrierung liefert der Client alle Netzwerk Verbindungsinformationen, die er über sich selbst weiß, in einer standortanforderung an den standortinformationsdienst, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server-Datenbank gesichert wird. Jeder zentrale Website Pool verfügt über einen standortinformationsdienst, der die Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort abzufragen. Wenn eine Übereinstimmung vorliegt, gibt der standortinformationsdienst einen Speicherort an den Client zurück. Wenn keine Übereinstimmung vorliegt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Standortrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der Skype for Business-Client umfasst die PIDF-Lo-Daten als Teil eines Notrufs, und diese Daten werden vom E9-1-1-Dienstanbieter verwendet, um den entsprechenden PSAP zu ermitteln und den Anruf an diesen PSAP zusammen mit dem korrekten ESQK weiterzuleiten, wodurch der PSAP-Verteiler Abrufen des Standorts des Anrufers.

Das folgende Diagramm zeigt, wie ein Skype for Business-Client einen Standort erwirbt (mit Ausnahme der Adress basierten Standort Methode eines Drittanbieters für Client Mac):

![So erwirbt der Client ein Standort Diagramm](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Damit ein Client den Standort erwirbt, sind folgende Schritte erforderlich:

1. Der Administrator füllt die Datenbank des Standort Informationsdiensts mit dem Netzwerk Wiremap (Tabellen, in denen verschiedene Arten von Netzwerkadressen den entsprechenden Notfall Speicherorten zugeordnet werden (ERLs)).

2. Wenn Sie einen SIP-Trunk E9-1-1-Dienstanbieter nutzen, überprüft der Administrator die Adressteile der Notfallstandorte gegen eine MSAG-Datenbank (Master Street Address Guide), die durch den E9-1-1-Dienstanbieter bereitgestellt wird. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) nutzen, stellt der Administrator sicher, dass der PSTN-Anbieter die ELINs in die ALI-Datenbank hochlädt (Automatic Location Identification).

3. Bei der Registrierung oder bei jeder Netzwerkänderung sendet ein intern verbundener Client eine Standortanfrage, die die gefundenen Netzwerkadressen des Clients enthält, an den standortinformationsdienst.

4. Der standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab, und gibt, wenn eine Übereinstimmung gefunden wird, das Erl an den Client im PIDF-Lo-Format zurück.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit für die Bereitstellung von E9-1-1. Wie Sie über ein ELIN-Gateway eine Verbindung mit einem PSTN-basierten E9-1-1-Dienstanbieter herstellen, erfahren Sie unter [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Das folgende Diagramm zeigt, wie ein Notfall Anruf von Skype for Business Server an den Public Safety Answering Point (PSAP) weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Service-Anbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Notfall Anruf Routing von lync Server zu PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Wenn ein Notruf über einen kompatiblen Skype for Business Server-Client erfolgt:

1. Eine SIP-Einladung, die den Standort, die Rückrufnummer des Anrufers und die (optionale) Benachrichtigungs-URL und die Konferenz-Rückrufnummer enthält, wird an den Skype for Business-Server weitergeleitet.

2. Skype for Business Server vergleicht die Notrufnummer und leitet den Anruf (basierend auf dem **PSTN-Nutzungs** Wert, der in der jeweiligen Standortrichtlinie definiert ist) an einen Vermittlungsserver und von dort aus über einen SIP-Stamm an den E9-1-1-Service-Anbieter weiter.

3. Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4. Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für eine Skype for Business-Notfallbenachrichtigung gesendet. Diese Meldung wird immer auf dem Bildschirm des Security Officers eingeblendet und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass das Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

5. Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6. Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway

Einige Partner des Unified Communications Open Interoperability-Programms bieten qualifizierte Notfall Standort-Identifikationsnummern (Elin)-fähige Gateways, die als Alternative zu einer SIP Trunk-Verbindung zu einem qualifizierten E9-1-1-Service-Anbieter dienen können. Elin-Gateways unterstützen die ISDN-oder zentralisierte Cama-Konnektivität (Automatic Message Accounting) zu Public Switched Telephone Network (PSTN)-basierenden E9-1-1-Diensten. Details zu Partnern, die Elin-Gateways und Links zu deren Dokumentation bereitstellen, finden Sie unter [Infrastruktur für Microsoft lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) und [Telefonie-Infrastruktur für Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Wie SIP-Trunk-Verbindungen mit E9-1-1-Service-Anbietern bieten Elin-Gateways auch die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheits Beantwortungs Punkt (PSAP) des Anrufers zu leiten, doch diese Gateways verwenden eine Elin als Standort-ID. Sie definieren Elins für jeden Emergency Response Location (ERL) in Ihrer Organisation (Details finden Sie unter [Verwalten von Speicherorten für Elin-Gateways in Skype for Business Server](elin-gateways.md)).

Wenn Sie ein Elin-Gateway für Notrufe verwenden, verwenden Sie dieselbe Skype for Business Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunk-Verbindung verwenden würden. Das heißt, die Datenbank des Standort Informationsdiensts stellt den Standort für den Skype for Business-Client bereit, und die Standortrichtlinie aktiviert das Feature und definiert den Arbeitsplan. Mit einem Elin-Gateway müssen Sie jedoch die Elins zur standortinformationsdienst-Datenbank hinzufügen und ihren PSTN-Netzbetreiber in die Datenbank "Automatic Location Identification (Ali)" hochladen.

Wenn ein Skype for Business-Client seinen Standort über den standortinformationsdienst erhält, enthält der Standort das Elin. Während eines Notrufs ist der Elin-Standort im Lieferumfang des Elin-Gateways enthalten. Das Elin-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer des Anrufers mit dem Elin aus. Das Elin-Gateway leitet dann den Anruf an das PSTN mit dem Elin als Rufnummer weiter. Der PSTN E9-1-1-Anbieter sucht nach dem Elin in der Ali-Datenbank, die eine Begleit Datenbank zur Master Street Address Guide (MSAG)-Datenbank ist. Das PSTN sendet dann den Anruf an die am besten geeignete PSAP basierend auf dem Ali-Lookup, und der PSAP sendet erste Responder an den Standort des Anrufers, basierend auf dem Ali-Lookup. Die Rufnummer wird für einen vordefinierten Zeitraum für Rückrufe auf dem Elin-Gateway zwischengespeichert. Während eines Rückrufs erreicht der PSAP das Elin-Gateway, das die Elin-Nummer für die direkte Durchwahlnummer des Anrufers ersetzt.

ELIN-Gateways unterstützen Notrufe nur innerhalb des Netzwerks Ihrer Organisation. Notrufe von außerhalb dieses Netzwerks werden nicht unterstützt.

> [!NOTE]
> Nähere Informationen zur Verwendung einer SIP-Trunkverbindung für Notrufe finden Sie unter [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Das folgende Diagramm zeigt, wie ein Notfall Anruf von Skype for Business Server an die PSAP weitergeleitet wird, wenn Sie ein Elin-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway**

![Zeigt, wie ein Anruf an Notfalldienste über den Vermittlungs Server und dann an den Notrufdienst Anbieter weitergeleitet wird. Danach kann optional eine Sofortnachricht an Onsite Security und/oder ein Rückruf an den ursprünglichen Anrufer gesendet werden.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Eine SIP-Einladung, die den Standort, die Rückrufnummer des Anrufers und die (optionale) Benachrichtigungs-URL und die Konferenz-Rückrufnummer enthält, wird an den Skype for Business-Server weitergeleitet.

2. Skype for Business Server vergleicht die Notrufnummer und leitet dann den Anruf (basierend auf dem in der jeweiligen Standortrichtlinie definierten **PSTN-Nutzungs** Wert) an einen Vermittlungsserver und von dort aus zu einem Elin-Gateway weiter.

3. Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4. Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP. 

5. Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht für eine Skype for Business-Notfallbenachrichtigung gesendet. Diese Meldung wird immer auf dem Bildschirm des Security Officers eingeblendet und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass das Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

6. Wenn der Anruf vorzeitig unterbrochen wird, kontaktiert der PSAP den Anrufer mithilfe der ELIN direkt. Das ELIN-Gateway tauscht die ELIN mit der DID des Anrufers.


