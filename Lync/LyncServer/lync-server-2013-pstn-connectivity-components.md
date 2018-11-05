---
title: 'Lync Server 2013: Komponenten für die PSTN-Konnektivität'
TOCTitle: Komponenten für die PSTN-Konnektivität
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398504(v=OCS.15)
ms:contentKeyID: 49294312
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten für die PSTN-Konnektivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten. Aus Benutzersicht sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz wie eine ganz normale SIP-Sitzung wirken.

Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway bereitstellen - mit Nebenstellenanlage (was auch als direkte SIP-Verbindung bezeichnet wird) oder ohne Nebenstellenanlage.

## SIP-Trunking

Als Alternative zu PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking mit dem Telefonfestnetz verbinden. Mit SIP-Trunking sind folgende Szenarien möglich:

  - Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.

  - Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.

Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich.

## PSTN-Gateways

Bei PSTN-Gateways handelt es sich um Drittanbietergeräte, die Signale und Mediendaten zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz oder einer Nebenstellenanlage übersetzen. PSTN-Gateways arbeiten mit dem Vermittlungsserver zusammen, um Anrufe aus dem Festnetz oder über eine Nebenstellenanlage an einen Enterprise-VoIP-Client zu übergeben. Der Vermittlungsserver übergibt außerdem Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway, damit dieses sie an das Telefonfestnetz oder die Nebenstellenanlage weiterleitet. Eine Liste der Partner, die mit Microsoft zusammenarbeiten, um für Lync Server funktionsfähige Geräte bereitzustellen, finden Sie auf der Microsoft-Website der Unified Communications-Partner unter <http://go.microsoft.com/fwlink/?linkid=202836>.

## Nebenstellenanlagen

Wenn Sie über eine vorhandene VoIP-Infrastruktur mit einer Nebenstellenanlage verfügen, können Sie diese mit Lync Server-Enterprise-VoIP verwenden.

Die folgenden Szenarien mit Integration von Enterprise-VoIP und einer Nebenstellenanlage werden unterstützt:

  - IP-Nebenstellenanlage mit Unterstützung der Medienumgehung und einem Vermittlungsserver.

  - IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.

  - TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.


> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur für die Produkte und Versionen unterstützt, die auf der Webseite für das Unified Communications Open Interoperability Program \endash Lync Server unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268730">http://go.microsoft.com/fwlink/?linkid=268730</A> aufgelistet werden.



Ausführliche Informationen zu Partnern, die Enterprise VoIP-Lösungen anbieten, finden Sie auf der Microsoft Unified Communications-Partnerseite unter <http://go.microsoft.com/fwlink/?linkid=202836>.

Ausführliche Informationen zu Partnern, die Enterprise VoIP-Hardwarelösungen (einschließlich PSTN-Gateways) anbieten, finden Sie auf der Microsoft Unified Communications-Partnerseite unter <http://go.microsoft.com/fwlink/?linkid=202836>.

