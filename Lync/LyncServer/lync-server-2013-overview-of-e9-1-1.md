---
title: 'Lync Server 2013: Übersicht über E9-1-1'
TOCTitle: Übersicht über E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412936(v=OCS.15)
ms:contentKeyID: 49295284
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über E9-1-1 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Microsoft Lync Server 2013 unterstützt Anruffunktionen für erweiterte Notfalldienste (E9-1-1) über Lync-Clients und Lync Phone Edition-Geräte. Wenn Sie Lync Server E9-1-1 konfigurieren, enthalten Notrufe von Lync 2013 oder Lync Phone Edition Informationen zum Standort für Notrufmaßnahmen (Emergency Response Location, ERL) aus der Standortinformationsdienst-Datenbank. ERLs bestehen aus allgemeinen Adressen (d. h. Hausadressen) und anderen Informationen, die eine präzisere Standortermittlung in Bürogebäuden und anderen Einrichtungen mit mehreren Parteien ermöglichen. Wenn ein Benutzer einen Notruf tätigt, werden die Audiodaten des Anrufs und Informationen zum Standort sowie Rückrufinformationen von Lync Server über einen Vermittlungsserver an einen E9-1-1-Dienstanbieter weitergeleitet. Der E9-1-1-Dienstanbieter verwendet die allgemeine Adresse des Anrufers, um den Anruf an die für den Standort des Anrufers zuständige Rettungsleitstelle weiterzuleiten. Es wird ebenfalls ein Notfalldienst-Abfrageschlüssel (ESQK) mitgesendet, mit dem die Rettungsleitstelle den ERL des Anrufers ausfindig machen kann.

Lync Server unterstützt zwei Methoden für die Weiterleitung von Notrufen an einen E9-1-1-Dienstanbieter:

  - Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

  - Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, fügen Sie der Standortinformationsdienst-Datenbank ERLs hinzu und überprüfen die Standorte anhand einer vom E9-1-1-Dienstanbieter verwalteten MSAG (Master Street Address Guide)-Datenbank. Wenn ein E9-1-1-Dienstanbieter einen Anruf erhält, der keine Standortinformationen enthält, oder der einen Standort enthält, der nicht mit der MSAG-Datenbank abgeglichen wurde, leitet der E9-1-1-Dienstanbieter den Anruf an ein nationales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) weiter. Das ECRC verfügt über speziell geschulte Mitarbeiter, die in einem Gespräch nach Möglichkeit den Standort des Anrufers ermitteln und den Anruf an eine geeignete Rettungsleitstelle weiterleiten. (Einige SIP-Trunk-E9-1-1-Dienstanbieter stellen ihren Kunden auch eine PSTN-DID (Direct Inward Dialing)-Nummer des ECRC zur Verfügung. Somit steht eine Alternative für die Weiterleitung von Notrufen bereit, falls der SIP-Trunk aus irgendeinem Grund fehlschlägt.)

Im Gegensatz zu TDM (Time Division Multiplexing)-Telefonen und Telefonen in einer IP-basierten Nebenstellenanlage (Private Branch Exchange, PBX), die über feste Standorte verfügen, kann ein Lync-Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, wird von Lync Server sichergestellt, dass der Notruf unabhängig vom Standort des Anrufers an die Rettungsleitstelle weitergeleitet wird, die für den Standort des Clients zuständig ist. Beispiel: Wenn sich das Hauptbüro eines Benutzers in Redmond, Washington, befindet, der Benutzer jedoch einen Notruf von einem Computer in einer Zweigstelle in Wichita, Kansas, absetzt, leitet der SIP-Trunk- oder PSTN-basierte E9-1-1-Dienstanbieter den Anruf an die Rettungsleitstelle in Wichita und nicht an die Rettungsleitstelle in Redmond weiter.

Wenn Sie ein ELIN-Gateway verwenden, fügen Sie der Standortinformationsdienst-Datenbank ebenfalls ERLs hinzu, jedoch integrieren Sie eine ELIN-Nummer für jeden Standort. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.


> [!NOTE]
> Analoge Geräte, die mit Lync verbunden sind, können keine Standortinformationen vom Standortinformationsdienst empfangen oder Standorte an den E9-1-1-Dienstanbieter übertragen. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, stehen Ihnen zwei Optionen zur Verfügung: 
> <UL>
> <LI>
> <P><STRONG>Herkömmlicher PS-ALI-Anbieter</STRONG>&nbsp;&nbsp;&nbsp;Wenn Sie an jedem Standort, an dem sich analoge Telefone befinden, über lokale PSTN-Gateways verfügen und jedes analoge Telefon über eine DID verfügt, können Sie den Standort des analogen Geräts direkt über einen PS-ALI (Private Switch/Automatic Location Identification)-Dienstanbieter bereitstellen. In diesem Fall konfigurieren Sie speziell hierfür erstellte Lync-VoIP-Richtlinien und weisen diese den Kontaktobjekten der analogen Geräte zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den für den Standort verantwortlichen PSTN-Betreiber weitergeleitet werden (anstatt den Anruf an den SIP-Trunk eines E9-1-1-Dienstanbieters weiterzuleiten). Wird ein Notruf getätigt, ordnet eine dem PSTN-Trunk zugewiesene Datenbank beim PS-ALI-Anbieter die DID jedes analogen Telefons einem physischen Standort zu und stellt diesen Standort der Rettungsleitstelle zur Verfügung. Diese Datensätze müssen beim PS-ALI-Dienstanbieter immer dann aktualisiert werden, wenn Telefone zu anderen ERLs verlegt werden.</P>
> <LI>
> <P><STRONG>E9-1-1-Dienstanbieter</STRONG>&nbsp;&nbsp;&nbsp;Sie können die DIDs der analogen Telefone und die zugehörigen ERLs beim E9-1-1-Dienstanbieter registrieren, wenn dies vom E9-1-1-Dienstanbieter unterstützt wird. Erhält der Anbieter einen Anruf von Lync Server, der keine PIDF-LO-Daten enthält, kann der Anbieter anhand der DID-Nummer des Anrufers erkennen, ob eine Übereinstimmung in einer Datenbank vorhanden ist. Anhand des aus der Datenbank abgerufenen ERL kann der Anbieter den Notruf automatisch an die entsprechende Rettungsleitstelle weiterleiten. Die Rettungsleitstelle erhält die DID des analogen Geräts und einen ESQK-Datensatz, mit dem der Verantwortliche den Standort des Anrufers ausfindig machen kann.</P></LI></UL>Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.



Aus Lync Server-Perspektive kann der E9-1-1-Prozess in zwei Schritte aufgeteilt werden:

  - Schritt 1: Abrufen eines Standorts

  - Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch ermittelt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Ausführliche Informationen zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente zum Ermitteln des Standorts in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

## In diesem Abschnitt

  - [Abrufen eines Standorts in Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

