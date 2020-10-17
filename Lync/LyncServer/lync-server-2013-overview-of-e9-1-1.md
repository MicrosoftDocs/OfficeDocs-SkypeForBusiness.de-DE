---
title: 'Lync Server 2013: Übersicht über E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1c97914abf8e5db393cd932c0a453885e86a5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530622"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Übersicht über E9-1-1 in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Microsoft lync Server 2013 unterstützt den erweiterten 9-1-1 (E9-1-1)-Aufruf von lync-Clients und lync Phone Edition-Geräten. Wenn Sie lync Server für E9-1-1 konfigurieren, werden Notrufe aus lync 2013-oder lync-Phone Edition Informationen aus dem Notfall Reaktions Standort (ERL) aus der Standortinformationsdienst-Datenbank hinzugefügt. ERLs bestehen aus bürgerlichen (also Straße)-Adressen und anderen Informationen, die helfen, eine genauere Position in Bürogebäuden und anderen Multitenant-Einrichtungen zu identifizieren. Wenn ein Benutzer einen Notruf tätigt, leitet lync Server das Audiosignal zusammen mit dem Standort und den Rückrufinformationen über ein Vermittlungsserver an einen E9-1-1-Dienstanbieter weiter. Der E9-1 -1-Dienstanbieter verwendet die bürgerliche Adresse des Anrufers, um den Anruf an den Rettungsleitstelle (Public Safety Answering Points) weiterzuleiten, der dem Standort des Anrufers dient, und sendet einen Notfalldienst-Abfrage Schlüssel (ESQK), den der Rettungsleitstelle zum Nachschlagen des Erl des Anrufers verwendet.

Lync Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:

  - Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

  - Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP-Trunk-E9-1 -1-Dienstanbieter verwenden, fügen Sie ERLs zur Standortinformationsdienst Datenbank hinzu und überprüfen dann die Speicherorte anhand einer Master Street Address Guide (MSAG), die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn ein E9-1 -1-Dienstanbieter einen Anruf erhält, der keine Standortinformationen hat oder keinen Speicherort hat, der nicht mit dem MSAG validiert wurde, der E9-1 -1-Dienstanbieter leitet den Anruf an ein nationales/regionales Emergency Call Response Center (ECRC) weiter, das mit speziell geschulten Mitarbeitern besetzt ist, die den Standort des Anrufers nach Möglichkeit verbal abrufen und den Anruf manuell an die entsprechenden Rettungsleitstelle weiterleiten. (Einige SIP-Trunk-E9-1 -1-Dienstanbieter stellen auch Kunden eine Telefonnummer für das PSTN-Durchwahl Verfahren für die ECRC bereit, die eine alternative Möglichkeit zum Weiterleiten von 9-1-1-anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund ausfällt.)

Im Gegensatz zu TDM (Time Division Multiplexing) und IP-basierten PBX-Telefonen (Private Branch Exchange) mit festen Standorten kann ein lync-Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, hilft lync Server sicherzustellen, dass sich unabhängig davon, wo sich ein Anrufer befindet, der Notruf an die Rettungsleitstelle weitergeleitet werden kann, die dem Standort des Anrufers dient. Beispiel: Wenn sich das Hauptbüro eines Benutzers in Redmond, Washington, befindet, der Benutzer jedoch einen Notruf von einem Computer in einer Zweigstelle in Wichita, Kansas, absetzt, leitet der SIP-Trunk- oder PSTN-basierte E9-1-1-Dienstanbieter den Anruf an die Rettungsleitstelle in Wichita und nicht an die Rettungsleitstelle in Redmond weiter.

Wenn Sie ein Elin-Gateway verwenden, fügen Sie auch ERLs zur Standortinformationsdienst Datenbank hinzu, aber Sie enthalten auch eine Elin-Nummer für jeden Standort. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

<div>


> [!NOTE]  
> Mit lync verbundene analoge Geräte können keine Standortinformationen von der Standortinformationsdienst oder vom Sendestandort an den E9-1 -1-Dienstanbieter empfangen. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, stehen Ihnen zwei Optionen zur Verfügung: 
> <UL>
> <LI>
> <P><STRONG>Traditionelle PS-Ali-Option</STRONG> &nbsp; &nbsp; &nbsp; Wenn Sie über lokale PSTN-Gateways an jedem Standort verfügen, auf dem analoge Telefone bereitgestellt werden und auf jedem analogen Telefon eine DID-Nummer vorhanden ist, können Sie den Standort des analogen Geräts direkt mit einem privaten Switch/Automatic Location Identification (PS-Ali)-Dienstanbieter bereitstellen. In diesem Fall konfigurieren Sie speziell hierfür erstellte Lync-VoIP-Richtlinien und weisen diese den Kontaktobjekten der analogen Geräte zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den für den Standort verantwortlichen PSTN-Betreiber weitergeleitet werden (anstatt den Anruf an den SIP-Trunk eines E9-1-1-Dienstanbieters weiterzuleiten). Wird ein Notruf getätigt, ordnet eine dem PSTN-Trunk zugewiesene Datenbank beim PS-ALI-Anbieter die DID jedes analogen Telefons einem physischen Standort zu und stellt diesen Standort der Rettungsleitstelle zur Verfügung. Diese Datensätze müssen beim PS-ALI-Dienstanbieter immer dann aktualisiert werden, wenn Telefone zu anderen ERLs verlegt werden.</P>
> <LI>
> <P><STRONG>Dienstanbieter Option</STRONG> &nbsp; &nbsp; &nbsp; für E9-1-1 Wenn dies vom E9-1 -1-Dienstanbieter unterstützt wird, können Sie das analoge Telefon DIDs und die entsprechenden ERLs mit dem E9-1 -1-Dienstanbieter registrieren. Wenn der Anbieter einen Anruf von lync Server erhält, der keine PIDF-Lo-Daten enthält, kann der Anbieter sehen, ob eine Daten Bank Übereinstimmung für die DID-Nummer des Anrufers vorliegt. Durch die Verwendung des von der Datenbank abgerufenen Erl kann der Anbieter den Notruf automatisch an die richtige Rettungsleitstelle weiterleiten, und der Rettungsleitstelle erhält das analoge Gerät und einen ESQK-Eintrag, mit dem der Dispatcher den Standort des Anrufers nachschlagen kann.</P></LI></UL>Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.</div>

Aus lync Server Perspektive kann der E9-1-1-Prozess in zwei Phasen aufgeteilt werden:

  - Schritt 1: Abrufen eines Standorts

  - Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch ermittelt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Ausführliche Informationen zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erwerben eines Standorts in lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Weiterleiten von E9-1 -1-Anrufen mithilfe eines SIP-Trunks in lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Weiterleiten von E9-1 -1-Anrufen mithilfe eines Elin-Gateways in lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

