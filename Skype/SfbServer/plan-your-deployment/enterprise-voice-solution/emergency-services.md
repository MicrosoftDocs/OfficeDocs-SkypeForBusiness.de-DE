---
title: Planen für Notdienste in Skype Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Informationen zu erweiterten E9-1-1 (E9-1-1) Dienste in Skype für Business Server Enterprise-VoIP, einschließlich Speicherort Erwerb und Anrufrouting.
ms.openlocfilehash: 7a4c03da5a7e138e68495c3bacd473f9ea073178
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-emergency-services-in-skype-for-business-server-2015"></a>Planen für Notdienste in Skype Business Server 2015
 
Informationen zu erweiterten E9-1-1 (E9-1-1) Dienste in Skype für Business Server Enterprise-VoIP, einschließlich Speicherort Erwerb und Anrufrouting.
  
Skype für Business Server unterstützt erweiterte E9-1-1 (E9-1-1) Dienste innerhalb der USA oder als Teil eines Enterprise-VoIP-Bereitstellung. E9-1-1 ist eine Notfällen-Funktion, die ordnet eine 9-1-1-anrufen mit einem Notfall Antwort Speicherort (ERL), der allgemeinen besteht (d. h., Straße)-Adressen und andere genauere Standortinformationen wie Numbers für Anrufe von Office-Gebäuden Floor und andere mandantenfähigen Funktionen. Mithilfe den bereitgestellten ERL kann einen öffentlichen Sicherheit beantworten Point (PSAP) sofort Notdienste an den Anrufer in Leiden mit geringerem versehentlich Umleiten des Responders an einem Speicherort falsche oder unklare versenden.
  
> [!NOTE]
> Skype für Business Server unterstützt jetzt die Konfiguration von mehreren Notfall Zahlen für einen Client an. Weitere Informationen finden Sie unter [Planen für mehrere Notfall Zahlen in Skype für Business Server 2015](multiple-emergency-numbers.md). 
  
> [!NOTE]
> Skype für Business Server verfügt über drei erweiterten Enterprise-VoIP-Funktionen: anrufsteuerung, notrufdienste (E9-1-1), und die medienumgehung. Eine Übersicht über die Planung von Informationen, die alle drei dieser Features gemeinsam ist, finden Sie unter [Einstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server 2015 Netzwerk](network-settings-for-advanced-features.md). 
  
Skype für Business Server unterstützt Enhanced E9-1-1 (E9-1-1) aufrufen in Skype für Business-Clients und Lync Phone Edition-Geräte. Wenn Sie Skype für Business Server für E9-1-1, Notfall Anrufe von Skype für Unternehmen konfigurieren, oder Lync Phone Edition enthalten Emergency Response Speicherort (ERL) Informationen aus der Datenbank. ERLs bestehen aus allgemeinen (d. h., Straße)-Adressen und andere Informationen, die hilft Ihnen, um eine genauere Position in Bürogebäude und andere mandantenfähigen Betriebsanlagen zu ermitteln. Wenn ein Benutzer einen Notruf herstellt, leitet Skype für Business Server den Anruf Audio, zusammen mit den Speicherort und den Rückruf Informationen über einen Vermittlungsserver an einen E9-1-1-Dienstanbieter. Der E9-1-1-Dienstanbieter verwendet die Adresse des Anrufers, um den Anruf zu öffentlichen Sicherheit beantworten Point (PSAP) weiterleiten, die dem Standort des Anrufers dient, und sendet entlang einer Emergency Service Abfrage Schlüssel (ESQK), die der PSAP zum Nachschlagen des Anrufers ERL verwendet. 
  
Skype für Business Server unterstützt zwei Methoden für die Weiterleitung von Notrufen an einen E9-1-1-Dienstanbieter:
  
- Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter
    
- Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter
    
Wenn Sie einem SIP-Trunk-E9-1-1-Dienstanbieter verwenden, ERLs der Standortinformationen Service-Datenbank hinzufügen und überprüfen Sie die Speicherorte für ein Master-Shape Straße Adresse Guide (Street), die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein E9-1-1-Dienstanbieter einen Anruf empfängt, der keinen Standortinformationen oder hat einen Speicherort, der nicht gegen die Street bestätigt wurde, leitet der E9-1-1-Dienstanbieter den Anruf an eine nationale/regionale Emergency Call Antwort Center (ECRC), das ist mit geschulte Mitarbeiter Alternativtext Standort des Anrufers zu erhalten, sofern möglich, und manuelles Weiterleitung des Anrufs an den entsprechenden PSAP besetzt. (Einige SIP-Trunk-E9-1-1-Dienstanbieter bieten auch, dass Kunden mit einem PSTN direct inward Dialing () Anzahl an die ECRC, die eine alternative Möglichkeit für routing E9-1-1 bietet aufruft, wenn der SIP-Trunk aus irgendeinem Grund nicht.)
  
Im Gegensatz zu Time Division multiplexing (TDM) und IP-basierte private Branch Exchange, (Nebenstellenanlage PBX) Telefone über die Speicherorte, einen Skype feste for Business-Endpunkt sehr mobil werden kann. Bei der Bereitstellung von E9-1-1-Feature kann Skype für Business Server sichergestellt werden, unabhängig davon, wo sich ein Anrufer befindet, Notruf an den PSAP geroutet werden kann, die dem Standort des Anrufers fungiert. Beispielsweise Hauptsitz des Benutzers befindet sich in Redmond, Washington, aber der Benutzer platziert einen Notruf über einen Computer in einer Zweigstelle in Wichita, Kansas, den SIP-Trunk oder PSTN-basierten E9-1-1-Dienstanbieter leitet den Anruf an den PSAP in Wichita , nicht an den PSAP in Redmond.
  
Wenn Sie ein ELIN-Gateway verwenden, ERLs auch hinzufügen, um die Standortinformationen Service-Datenbank, aber Sie enthalten außerdem eine ELIN Nummer für jeden Standort. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI-Datenbank (Automatic Location Identification, automatische Standortidentifizierung) hochlädt. 
  
> [!NOTE]
> Skype für analoge Geräte Business verbundene nicht empfangen Standortinformationen aus dem Dienst Standortinformationen oder Speicherort zum E9-1-1-Dienstanbieter zu übertragen. 
  
 Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und E9-1-1 über analoge Telefone unterstützen müssen, stehen Ihnen zwei Optionen zur Verfügung:
  
- **Herkömmliche PS-ALI-option** Wenn Sie dabei analoge Telefone bereitgestellt werden und jedes analoge Telefon hat eine DID lokalen PSTN-Gateways an jedem Standort haben, können Sie das analoge Gerät Speicherort direkt mit einem privaten Switch/automatische Location Identification (PS-ALI) Dienstanbieter bereitstellen. In diesem Fall speziell gestalteten Skype für Business VoIP-Richtlinien konfigurieren und weisen Sie diese das analoge Gerät Kontaktobjekte, damit E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway den PSTN-Dienstanbieter weitergeleitet, die die Website (stattdessen services Weiterleiten des Anrufs an einen E9-1-1-Dienstanbieter SIP-Trunk). Wenn ein Notruf eingefügt wird, wird eine Datenbank an ein PS-ALI-Anbieter, der den PSTN-Trunk zugeordnet ist ordnet die DID jedes analoge Telefonnummer einen physischen Standort und diesen Speicherort an dem PSAP bietet. Jedes Mal, wenn Telefone in verschiedenen ERLs verschoben werden, müssen diese Einträge mit dem Dienstanbieter PS-ALI aktualisiert werden.
    
- **E9-1-1, Service Provider-option** Sie können das analoge Telefonleitung DIDs und ihre entsprechenden ERLs mit dem E9-1-1-Dienstanbieter registrieren, wenn dies vom E9-1-1-Dienstanbieter unterstützt wird. Wenn der Anbieter einen Anruf von Skype für Business Server, die PIDF-LO-Daten enthalten, nicht empfängt, kann der Anbieter sehen, wenn eine Datenbank Übereinstimmung auf die Rufnummer des Anrufers DID vorliegt. Mithilfe den ERL automatisch aus der Datenbank, die vom Anbieter kann abgerufen erhält die Route des Notrufs an die richtige rettungsleitstelle weiter, und die Rettungsleitstelle die DID das analoge Gerät und ein ESQK-Eintrag, der den Verteiler, der dem Standort des Anrufers nachgeschlagen ermöglicht.
    
Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.
  
Aus einer Skype für Business Server Perspektive kann der E9-1-1-Prozess in zwei Schritte aufgeteilt werden:
  
- Schritt 1: Abrufen eines Standorts
    
- Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter
    
In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.
  
Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch erkannt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Ausführliche Informationen zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente zum Ermitteln des Standorts in Skype für Business Server 2015 verwendet](network-location.md). 
  
## <a name="acquiring-a-location"></a>Abrufen eines Standorts

In einer Skype für Business Server E9-1-1-Bereitstellung erhält jede intern verbundener Skype für Business oder Lync Phone Edition-Client aktiv eigenem Speicherort. Nach der SIP-Registrierung stellt der Client alle Netzwerk-Konnektivitätsinformationen, die sie über sich selbst in eine standortanforderung mit dem Dienst Standortinformationen bekannt, einen Webdienst ist, die auf eine replizierte Datenbank von SQL Server ist bereit. Jeder Pool zentralen Standort verfügt über eine Standortinformationen-Dienst, der Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort abzufragen. Wenn eine Übereinstimmung vorhanden ist, gibt der standortinformationsdienst eine Position an den Client zurück. Wenn keine Übereinstimmung vorliegt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Standortrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.
  
Die Skype für Business-Client umfasst die PIDF-LO-Daten als Teil des ein Notruf und diese Daten werden vom E9-1-1-Dienstanbieter verwendet, um den entsprechenden PSAP bestimmen und Weiterleitung des Anrufs an diese PSAP zusammen mit der richtigen ESQK den PSAP Verteiler, wodurch Standort des Anrufers zu erhalten.
  
Das folgende Diagramm zeigt, wie eine Skype für Business-Client einen Standort (mit Ausnahme der Drittanbieter-Client-MAC-Adresse-basierte Location-Methode) abruft:
  
![Beschreibung des Abrufs eines Standorts durch einen Client (Diagramm)](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)
  
Damit ein Client den Standort erwirbt, sind folgende Schritte erforderlich:
  
1. Der Administrator füllt die Standortinformationen Service-Datenbank mit der netzwerkwiremap (Tabellen, die verschiedene Typen von Netzwerkadressen den entsprechenden Emergency Response Locations (ERLs) zuordnen).
    
2. Wenn Sie einen SIP-Trunk E9-1-1-Dienstanbieter nutzen, überprüft der Administrator die Adressteile der Notfallstandorte gegen eine MSAG-Datenbank (Master Street Address Guide), die durch den E9-1-1-Dienstanbieter bereitgestellt wird. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) nutzen, stellt der Administrator sicher, dass der PSTN-Anbieter die ELINs in die ALI-Datenbank hochlädt (Automatic Location Identification).
    
3. Während der Registrierung oder wenn eine netzwerkänderung stattfindet sendet ein intern verbundener-Client eine standortanforderung, die den Client enthält die ermittelten Netzwerkadressen auf den standortinformationsdienst.
    
4. Die Standortinformationen Service fragt seine veröffentlichten Datensätze für einen Standort und, wenn eine Übereinstimmung gefunden wird, gibt den ERL im PIDF-LO-Format an den Client zurück.
    
## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit für die Bereitstellung von E9-1-1. Ausführliche Informationen zur Verwendung eines ELIN-Gateways zur Verbindung von eines öffentlichen Telefonfestnetz (PSTN)-basierte E9-1-1-Dienstanbieter, finden Sie unter [Routing E9-1-1 Calls mithilfe eines ELIN-Gateways](http://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).
  
Das folgende Diagramm zeigt, wie ein Notruf von weitergeleitet wird Skype für Business Server zum öffentlichen Sicherheit beantworten Point (PSAP) Wenn Sie eine SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.
  
**Weiterleiten von E9-1-1-Anrufen über einen SIP-trunk**

![Notrufweiterleitung vom Lync Server an PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)
  
Wenn ein Notruf über einen kompatiblen Skype für Business Server-Client befindet:
  
1. Eine SIP INVITE-Anforderung mit dem Standort, der Rückrufnummer des Anrufers sowie der (optional) Benachrichtigungs-URL und konferenzrückrufnummer wird an Skype für Business Server weitergeleitet.
    
2. Skype für Business Server gleicht die Notrufnummer und leitet den Anruf (basierend auf dem **PSTN-Verwendung** -Wert, der in der betreffenden Standortrichtlinie definiert ist) an einen Vermittlungsserver und von dort über einen SIP-Trunk zum E9-1-1-Dienstanbieter.
    
3. Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.
    
4. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, werden eine oder mehrere der Sicherheits-Managern Ihrer Organisation eine spezielle Skype Business Notfall Benachrichtigung Sofortnachricht gesendet. Diese Meldung wird immer eingeblendet wird, klicken Sie auf die Sicherheits-Managern Bildschirme und des Anrufers, Telefonnummer, Zeit und Standort Aktivieren des Sicherheitspersonals an, schnell auf den Notruf tätigt Antworten mit einer Sofortnachricht oder VoIP enthält.
    
5. Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.
    
6. Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.
    
## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway

Einige Partner in der Unified Communications Open Interoperability Program bieten qualifizierte Emergency Location Identification Anzahl (ELIN)-fähige Gateways, die als Alternative zu einem SIP-trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter verwendet werden können. ELIN-Gateways unterstützen ISDN- oder zentralisierte automatische Nachricht Accounting (CAMA) eine Verbindung mit öffentlichen Telefonfestnetz (PSTN)-basierte E9-1-1-Dienste. Ausführliche Informationen zu Partnern, die die ELIN-Gateways und Links zu ihrer Dokumentation bereitstellen, finden Sie unter [Infrastruktur für Microsoft Lync qualifizierte](https://go.microsoft.com/fwlink/p/?LinkId=248425) und [Telefonie-Infrastruktur für Skype für Unternehmen](https://technet.microsoft.com/en-us/office/dn947483). 
  
Wie SIP-Trunk-Verbindungen an E9-1-1-Dienstanbieter ELIN-Gateways bieten auch die Möglichkeit, Weiterleiten eines Notrufs an des Anrufers am besten geeignete öffentlichen Sicherheit beantworten Point (PSAP), aber diese Gateways ein ELIN als Speicherortbezeichner verwenden. Sie definieren ELINs für jede Emergency Response Speicherort (ERL) in Ihrer Organisation (Weitere Informationen hierzu finden Sie unter [Verwalten von Standorten für ELIN-Gateways in Skype für Business Server 2015](elin-gateways.md)). 
  
Wenn Sie ein ELIN-Gateway für Notrufe verwenden, verwenden Sie die gleichen Skype für Business Server E9-1-1-Infrastruktur, die Sie für einen SIP-Trunk-Verbindung verwenden würden. D. h., die Standortinformationen Service-Datenbank enthält den Speicherort der Skype für Business-Client, und die Standortrichtlinie aktiviert das Feature und das routing definiert. Mit einem ELIN-Gateway müssen Sie jedoch die Standortinformationen Service-Datenbank die ELINs hinzufügen und diese auf die automatische Speicherort (Identification)-Datenbank hochladen Ihres PSTN-Betreibers haben.
  
Wenn eine Skype für Business Client den Speicherort aus dem Dienst Standortinformationen erhält, enthält der Speicherort der ELIN. Bei einem Notruf ist das ELIN mit dem Speicherort, an das ELIN-Gateway gesendet enthalten. Das ELIN-Gateway identifiziert das Gespräch wie ein Notruf und des Anrufers Zahl mit der ELIN vertauscht. Das ELIN-Gateway leitet den Anruf an das Telefonfestnetz mit der ELIN dann als der Rufnummer. Die PSTN E9-1-1-Dienstanbieter sucht das ELIN in die ALI-Datenbank, die eine Mobile Begleit-Datenbank in der Datenbank Master Street Address Guide (Street) ist. Das Telefonfestnetz sendet dann den Anruf an die am besten geeignete PSAP basierend auf der Suche ALI und der PSAP Notdienste an dem Standort des Anrufers basierend auf der Suche ALI sendet. Nummer des Anrufers wird auf das ELIN-Gateway für einen vordefinierten Zeitraum für Rückrufe zwischengespeichert. Während ein Rückruf erreicht der PSAP ELIN-Gateway, das für den Anrufer direkt nach innen Nummer (DIALING) an die ELIN vertauscht.
  
ELIN-Gateways unterstützen Notrufe nur innerhalb des Netzwerks Ihrer Organisation. Notrufe von außerhalb dieses Netzwerks werden nicht unterstützt.
  
> [!NOTE]
> Weitere Informationen zur Verwendung einer SIP-trunkverbindung für Notrufe finden Sie unter [Routing E9-1-1 Calls by Using a SIP Trunk](http://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx). 
  
Das folgende Diagramm zeigt, wie ein Notruf von weitergeleitet wird Skype für Business Server an den PSAP bei Verwendung ein ELIN-Gateways.
  
**Weiterleiten von E9-1-1-anrufen mit einem ELIN-gateway**

![Zeigt, wie ein Anruf bei Notdiensten über den Vermittlungsserver läuft und dann zum Anbieter für die Notrufunterstützung gelangt. Danach kann optional eine Sofortnachricht an den Sicherheitsdienst vor Ort gesendet und/oder ein Rückruf zum ursprünglichen Anrufer durchgeführt werden.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)
  
1. Eine SIP INVITE-Anforderung mit dem Standort, der Rückrufnummer des Anrufers sowie der (optional) Benachrichtigungs-URL und konferenzrückrufnummer wird an Skype für Business Server weitergeleitet.
    
2. Skype für Business Server gleicht die Notrufnummer ab und leitet den Anruf (basierend auf dem **PSTN-Verwendung** -Wert, der in der jeweiligen ortungsrichtlinie definierten), an einen Vermittlungsserver und von dort an ein ELIN-Gateway.
    
3. Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.
    
4. Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.  
    
5. Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, werden eine oder mehrere der Sicherheits-Managern Ihrer Organisation eine spezielle Skype Business Notfall Benachrichtigung Sofortnachricht gesendet. Diese Meldung wird immer eingeblendet wird, klicken Sie auf die Sicherheits-Managern Bildschirme und des Anrufers, Telefonnummer, Zeit und Standort Aktivieren des Sicherheitspersonals an, schnell auf den Notruf tätigt Antworten mit einer Sofortnachricht oder VoIP enthält.
    
6. Wenn der Anruf vorzeitig unterbrochen wird, kontaktiert der PSAP den Anrufer mithilfe der ELIN direkt. Das ELIN-Gateway tauscht die ELIN mit der DID des Anrufers.
    

