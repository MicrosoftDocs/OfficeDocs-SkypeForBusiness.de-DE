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
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Übersicht über E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Microsoft lync Server 2013 unterstützt erweiterte 9-1-1 (E9-1-1)-Aufrufe von lync-Clients und lync Phone Edition-Geräten. Wenn Sie lync Server für E9-1-1 konfigurieren, beinhalten Notrufe, die von lync 2013 oder lync Phone Edition abgesetzt werden, die Informationen zum Emergency Response Location (ERL) aus der Datenbank des Standort Informationsdiensts. ERLs bestehen aus bürgerlichen (also Straßen-) Adressen und anderen Informationen, die dazu beitragen, eine genauere Position in Bürogebäuden und anderen Multitenant-Anlagen zu erkennen. Wenn ein Benutzer einen Notfall Anruf tätigt, leitet lync Server den Audioanruf zusammen mit dem Standort und den Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Service-Anbieter weiter. Der E9-1-1-Service-Anbieter verwendet die bürgerliche Adresse des Anrufers, um den Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterzuleiten, der dem Aufenthaltsort des Anrufers dient, und sendet einen Notfall-Service-Abfrage Schlüssel (ESQK), den der PSAP verwendet, um den Erl des Anrufers nachschlagen zu können.

Lync Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:

  - Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter

  - Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter

Wenn Sie einen SIP Trunk E9-1-1 Dienstanbieter verwenden, fügen Sie ERLs der Datenbank des Standort Informationsdiensts hinzu, und überprüfen Sie dann die Speicherorte mit einem Master Street Address Guide (MSAG), der vom E9-1-1-Dienstanbieter verwaltet wird. Wenn ein Dienstanbieter E9-1-1 einen Anruf empfängt, der keine Standortinformationen hat oder einen Speicherort aufweist, der nicht mit dem MSAG überprüft wurde, der E9-1-1-Service-Anbieter leitet den Anruf an ein nationales/regionales Notruf Center (ECRC) weiter, das mit speziell geschulten Mitarbeitern besetzt ist, die den Standort des Anrufers, wenn möglich, verbal abrufen und den Anruf manuell an die entsprechende PSAP weiterleiten. (Einige SIP Trunk E9-1-1-Service-Anbieter bieten Kunden auch eine direkte PSTN-Wählnummer (DID) an den ECRC, die ein alternatives Mittel zur Weiterleitung von 9-1-1-anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund fehlschlägt.)

Im Gegensatz zu Time Division Multiplexing (TDM) und IP-basierter PBX-Telefone (Private Branch Exchange), die über feste Speicherorte verfügen, kann ein lync-Endpunkt sehr mobil sein. Wenn Sie das E9-1-1-Feature bereitstellen, hilft lync Server dabei, sicherzustellen, dass der Notruf, unabhängig davon, wo sich ein Anrufer befindet, an die PSAP weitergeleitet werden kann, die dem Aufenthaltsort des Anrufers dient. Beispiel: Wenn sich das Hauptbüro eines Benutzers in Redmond, Washington, befindet und der Benutzer einen Notruf von einem Computer in einer Zweigstelle in Wichita, Kansas, absetzt, leitet der SIP-Trunk- oder PSTN-basierte E9-1-1-Dienstanbieter den Anruf an die Rettungsleitstelle in Wichita und nicht an die Rettungsleitstelle in Redmond weiter.

Wenn Sie ein Elin-Gateway verwenden, fügen Sie auch ERLs der Datenbank des Standort Informationsdiensts hinzu, Sie schließen aber auch eine Elin-Nummer für jede Position ein. Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer. Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI-Datenbank (Automatic Location Identification, automatische Standortidentifizierung) hochlädt.

<div>


> [!NOTE]  
> Mit lync verbundene analoge Geräte können keine Standortinformationen vom standortinformationsdienst empfangen oder den Standort an den E9-1-1-Service-Anbieter übertragen. Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und E9-1-1 über analoge Telefone unterstützen müssen, stehen Ihnen zwei Optionen zur Verfügung: 
> <UL>
> <LI>
> <P><STRONG>Traditionelle PS-Ali-Option</STRONG>&nbsp;&nbsp;&nbsp;Wenn Sie an jedem Standort, an dem analoge Telefone bereitgestellt werden, über lokale PSTN-Gateways verfügen und auf jedem analogen Telefon ein did vorhanden ist, können Sie den Standort des analogen Geräts direkt mit einem privaten Switch/Automatic Location Identification (PS-Ali)-Dienstanbieter bereitstellen. In diesem Fall konfigurieren Sie speziell gestaltete lync-VoIP-Richtlinien und weisen Sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter weiterleiten, der die Website abruft (anstatt das Routing des Anruf an einen E9-1-1-Service-Anbieter SIP-Trunk). Wenn ein Notruf erfolgt, ordnet eine Datenbank bei einem PS-Ali-Anbieter, der dem PSTN-trunk zugeordnet ist, die did-Daten jedes analogen Telefons einem physikalischen Standort zu und stellt diesen Standort dem PSAP zur Verfügung. Diese Einträge müssen mit dem PS-Ali-Dienstanbieter jedes Mal aktualisiert werden, wenn Telefone in andere ERLs verschoben werden.</P>
> <LI>
> <P><STRONG>E9-1-1 Service Provider-Option</STRONG>&nbsp;&nbsp;&nbsp;Sie können die analoge Telefon DIDs und deren zugehörige ERLs mit dem E9-1-1-Dienstanbieter registrieren, wenn dieser vom Dienstanbieter E9-1-1 unterstützt wird. Wenn der Anbieter einen Anruf von lync Server erhält, der keine PIDF-Lo-Daten enthält, kann der Anbieter sehen, ob eine Daten Bank Übereinstimmung für die DID-Nummer des anrufenden Teilnehmers vorliegt. Durch Verwendung des Erl, das aus seiner Datenbank abgerufen wurde, kann der Anbieter den Notruf automatisch an die richtige PSAP weiterleiten, und der PSAP empfängt die did des analogen Geräts und einen ESQK-Eintrag, der es dem Dispatcher ermöglicht, den Standort des Anrufers nachzuschlagen.</P></LI></UL>Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.</div>

Aus Sicht des lync-Servers kann der E9-1-1-Prozess in zwei Phasen aufgeteilt werden:

  - Schritt 1: Abrufen eines Standorts

  - Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter

In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.

Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch erkannt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen. Details zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in lync Server 2013 verwendet](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Abrufen eines Standorts in Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

