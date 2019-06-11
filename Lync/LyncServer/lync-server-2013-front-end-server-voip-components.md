---
title: 'Lync Server 2013: VoIP-Komponenten des Front-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3558d230b1fb767f0e7844be3894b579149c3f6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Front-End-Server-VoIP-Komponenten für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die VoIP-Komponenten, die sich auf Front-End-Servern befinden, sind wie folgt:

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

Die eingehende Routing Komponente verarbeitet eingehende Anrufe weitgehend gemäß den Einstellungen, die von Benutzern auf Ihren Enterprise-VoIP-Clients angegeben werden. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern dies vom Benutzer konfiguriert ist. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufweiterleitung aktiviert ist, können Benutzer angeben, ob nicht angenommene Anrufe an eine andere Nummer oder an einen Exchange um-Server weitergeleitet werden sollen, der für die Anrufannahme konfiguriert wurde. Die eingehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.

</div>

<div>

## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Sie wendet (gemäß Definition in der VoIP-Richtlinie für den Benutzer) Anrufautorisierungsregeln auf Anrufer an und ermittelt das optimale PSTN-Gateway für das Routing der einzelnen Anrufe. Die ausgehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange um-Routingkomponente verarbeitet das Routing zwischen lync Server und Servern, auf denen Exchange Unified Messaging (um) ausgeführt wird, um lync Server mit Unified Messaging-Features zu integrieren.

Die Exchange um-Routingkomponente behandelt auch das Umleiten von Voicemail über das PSTN, wenn Exchange um-Server nicht verfügbar sind. Wenn Sie über Enterprise-VoIP-Benutzer an Zweigstellen verfügen, die nicht über eine stabile WAN-Verbindung zu einem zentralen Standort verfügen, bietet die Survivable Branch-Appliance, die Sie auf der Zweigstelle bereitstellen, die Voicemail-Überlebensfähigkeit von Zweig Benutzern während eines WAN-Ausfalls. Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch-Appliance die folgenden Aktionen aus:

  - Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

  - Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

  - Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist.

Zum Aktivieren des Umleitens von Voicemail empfehlen wir, dass Ihr Exchange-Administrator die automatische Exchange UM-Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.

Details zu diesen Features finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [Planen der Stabilität von Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md).

</div>

<div>

## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Diese Komponente sorgt für das Routing von Anrufen beim primären Registrierungsstellenpool des Anrufempfängers. Wenn dieser Pool nicht verfügbar ist, leitet die Komponente den Anruf an den Backup-Registrierungsstellenpool des Anrufempfängers weiter. Wenn keiner der beiden Pools über das IP-Netzwerk erreicht werden kann, leitet die Komponente für das clusterübergreifende Routing den Anruf über das Telefonfestnetz an die Rufnummer des Benutzers um.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Andere Komponenten, die sich auf dem Front-End-Server oder Director befinden und die grundlegende Unterstützung für VoIP bieten, aber nicht selbst VoIP-Komponenten sind, umfassen Folgendes:

  - **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Informationen verteilt die Eingangsroutingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers. Benutzer Dienste ist eine Hauptkomponente auf allen Front-End-Servern und-Directors.

  - **Benutzerreplikationsdienst** Extrahiert Benutzer Telefonnummern aus Active Directory-Domänendiensten und schreibt Sie in Tabellen in der RTC-Datenbank, wo Sie für Benutzer Dienste und den Adressbuch Server verfügbar sind. Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.

  - **Adressbuchserver.** Enthält Informationen zur globalen Adressliste aus Active Directory-Domänendiensten für lync Server-Clients. Sie ruft auch Benutzer-und Kontaktinformationen aus der RTC-Datenbank ab, schreibt die Informationen in die Adressbuchdateien und speichert die Dateien dann in einem freigegebenen Ordner, in dem Sie von lync-Clients heruntergeladen werden. Der Adressbuch Server schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuch-Webabfrage Dienst verwendet wird, um auf Benutzer Suchabfragen von Microsoft lync 2010 Mobile zu reagieren. Optional werden Unternehmensbenutzer-Telefonnummern, die in die RTC-Datenbank geschrieben wurden, zum Zweck der Bereitstellung von Benutzerkontakten in lync normalisiert. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Der Adressbuch-Webabfrage Dienst wird standardmäßig mit den Webdiensten auf den einzelnen Front-End-Servern installiert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

