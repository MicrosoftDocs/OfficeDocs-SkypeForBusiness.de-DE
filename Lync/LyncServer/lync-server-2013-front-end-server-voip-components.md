---
title: 'Lync Server 2013: Front-End-Server VoIP-Komponenten'
description: 'Lync Server 2013: VoIP-Komponenten Front-End-Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9390d06cf6277ef79ec2ec785bad4b497bc04a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567091"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Front-End-Server von VoIP-Komponenten für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Die VoIP-Komponenten auf Front-End-Servern befinden sich wie folgt:

  - Übersetzungsdienst

  - Eingangsroutingkomponente

  - Ausgangsroutingkomponente

  - Routingkomponente für Exchange UM

  - Komponente für das clusterübergreifende Routing

  - [Vermittlungsserver Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.

</div>

<div>

## <a name="inbound-routing-component"></a>Eingangsroutingkomponente

Die eingehende Routingkomponente verarbeitet eingehende Anrufe im Wesentlichen gemäß den Einstellungen, die von Benutzern auf den Enterprise-VoIP-Clients festgelegt sind. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern vom Benutzer konfiguriert. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufweiterleitung aktiviert ist, können Benutzer angeben, ob nicht beantwortete Anrufe an eine andere Nummer oder an einen Exchange um Server weitergeleitet werden sollen, der für die Mailboxansage konfiguriert wurde. Die eingehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und Front-End-Servern installiert.

</div>

<div>

## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Sie wendet (gemäß Definition in der VoIP-Richtlinie für den Benutzer) Anrufautorisierungsregeln auf Anrufer an und ermittelt das optimale PSTN-Gateway für das Routing der einzelnen Anrufe. Die ausgehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange um Routingkomponente verarbeitet das Routing zwischen lync Server und Servern mit Exchange Unified Messaging (um), um lync Server mit Unified Messaging-Funktionen zu integrieren.

Die Exchange um Routingkomponente behandelt auch das erneute Routing von Voicemail über das PSTN, wenn Exchange um Server nicht verfügbar sind. Wenn Sie über Enterprise-VoIP-Benutzer an Zweigstellenstandorten verfügen, die nicht über eine ausfallsichere WAN-Verbindung mit einem zentralen Standort verfügen, bietet die Survivable Branch Appliance, die Sie am Zweigstellenstandort bereitstellen, für Zweig Benutzer während eines WAN-Ausfalls eine Survivable-Fähigkeit für Voicemail. Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch Appliance folgende Aufgaben aus:

  - Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

  - Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

  - Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist

Zum Aktivieren der Voicemail-Umleitung empfehlen wir, dass Ihr Exchange-Administrator Exchange um automatische Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.

Ausführliche Informationen zu diesen Features finden Sie unter [Planning for Exchange Unified Messaging Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md).

</div>

<div>

## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Diese Komponente sorgt für das Routing von Anrufen beim primären Registrierungspool des Anrufempfängers. Wenn dieser Pool nicht verfügbar ist, leitet die Komponente den Anruf an den Sicherungsregistrierungspool des Anrufempfängers weiter. Wenn keiner der beiden Pools über das IP-Netzwerk erreicht werden kann, leitet die Komponente für das clusterübergreifende Routing den Anruf über das Telefonfestnetz an die Rufnummer des Benutzers um.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Andere Komponenten im Front-End-Server oder Director, die grundlegende Unterstützung für VoIP bieten, aber selbst keine VoIP-Komponenten sind, umfassen Folgendes:

  - **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Informationen verteilt die Eingangsroutingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers. User Services ist eine Hauptkomponente auf allen Front-End-Servern und Directors.

  - **Benutzerreplikationsdienst.** Extrahiert Benutzer Telefonnummern aus Active Directory-Domänendienste und schreibt Sie in Tabellen in der RTC-Datenbank, wo Sie für Benutzer Dienste und Adressbuch Server verfügbar sind. Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.

  - **Adressbuchserver.** Enthält Informationen zur globalen Adressliste von Active Directory-Domänendienste an lync Server Clients. Außerdem ruft er Benutzer-und Kontaktinformationen aus der RTC-Datenbank ab, schreibt die Informationen in die Adressbuchdateien und speichert die Dateien dann in einem freigegebenen Ordner, in dem Sie von lync-Clients heruntergeladen werden. Der Adressbuch Server schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuch-Webabfragedienst verwendet wird, um auf Benutzer Suchabfragen von Microsoft lync 2010 Mobile zu reagieren. Optional werden die Telefonnummern von Unternehmensbenutzern, die in die RTC-Datenbank geschrieben wurden, zum Zweck der Bereitstellung von Benutzerkontakten in lync normalisiert. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Das Adressbuch-Webabfragedienst wird standardmäßig mit den Webdiensten auf jedem Front-End-Server installiert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

