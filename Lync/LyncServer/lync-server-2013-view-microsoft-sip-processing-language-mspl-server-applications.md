---
title: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582c48cfbd276778b1d22c3bec17a5c0106d8a30
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-09-26_

Eine MSPL-Serveranwendung (Microsoft SIP Processing Language) ist eine nur-Skript-Anwendung, die anstelle des Microsoft lync 2010 API eine Skriptsprache verwendet. MSPL ermöglicht eine genauere Steuerung des Filter- und Proxyverhaltens und bietet eine Funktion zum Weiterleiten bestimmter Nachrichten an transaktionsbasierte SIP-Anwendungen. MSPL wird insbesondere zum Filtern und Weiterleiten von SIP-Nachrichten verwendet. MSPL-Anwendungen werden im gleichen Prozess wie das User Services-Modul ausgeführt, während ein auf dem lync 2010 API basierendes Programm in einem separaten Prozess ausgeführt wird.

Sie können die Seite **Serveranwendung** in der **topologiegruppe** lync Server-Systemsteuerung verwenden, um eine Liste der MSPL-Serveranwendungen anzuzeigen, die auf Front-End-Servern in ihrer lync Server 2013 Umgebung ausgeführt werden. Die Liste zeigt die für jeden Pool verfügbaren Skripts und gibt an, ob diese aktiviert oder kritisch sind. Die Skripts werden in der Reihenfolge ihrer Auflistung ausgeführt.

Die folgenden Skripts sind verfügbar:

  - ClientVersionFilter ermöglicht Administratoren, die von einem Pool unterstützte Version der Clients anzugeben. Mit dem Clientversionsfilter kann die Clientversion überprüft und dann entweder die Anmeldung des Clients verhindert oder dem Benutzer eine Meldung angezeigt werden, dass eine nicht unterstützte Clientversion verwendet wird. Der Clientversionsfilter kann auch so konfiguriert werden, dass dem Benutzer eine Meldung mit der URL der aktuellen herunterladbaren Version des Clients angezeigt wird.

  - TranslationService wandelt eine von einem Benutzer gewählte Nummer entsprechend den vom Administrator festgelegten Normalisierungsregeln in eine E.164-Nummer um. Ausführliche Informationen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten zwischen Mandanten und aus externen Bereitstellungen eingehende Nachrichten.

  - Bei UserServices handelt es sich um die SIP-Registrierungs-, Anwesenheits- und Konferenzkomponente eines Front-End-Servers. Dieses Skript stellt integrierte Sofortnachrichten-, Anwesenheits- und Konferenzfunktionen auf Basis des SIP-Proxys bereit.

  - InterClusterRouting sorgt für das Routing von Anrufen beim primären Registrierungspool des Anrufempfängers. Ausführliche Informationen finden Sie unter [Front-End-Server VoIP-Komponenten für lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (Intelligent im Filter) blockiert Nachrichten, die klickable URLs enthalten oder die versuchen, Dateiübertragungen zu initiieren. IIMFilter überprüft auch die Client Version im Namen des Servers. IIMFilter betrifft Dateiübertragungen, die entweder mit lync Server oder Communicator initiiert werden. Standardmäßig sind die Klick fähigen Links deaktiviert, indem Sie vor dem ersten Zeichen des Links ein Unterstrichzeichen hinzufügen. Ein Administrator kann dieses Verhalten so ändern, dass der Link blockiert wird, sodass Nachrichten, die Klick Bare URLs enthalten oder die versuchen, eine Dateiübertragung zu initiieren, vom Server blockiert werden, um die beabsichtigten Ziele zu erreichen. IIMFilter ist auf allen Servern installiert, auf denen lync Server mit Ausnahme von Proxy Servern und Archivierungsservern betrieben wird.

  - UserPinService wird verwendet, um die persönlichen Identifikationsnummern (PINs) für Einwahlkonferenzen zu überprüfen.

  - DefaultRouting ist die standardmäßige Routing Anwendung für Server, auf denen lync Server verwendet wird. Diese Anwendung ist standardmäßig aktiviert. Die Routinganwendung wird auf allen Standard Edition- und Enterprise Edition-Servern installiert.

  - Mit ExumRouting werden Anrufe von Exchange Server Unified Messaging (UM) weitergeleitet. ExumRouting ermittelt bei Eingang einer neuen Voicemailnachricht den geeigneten Exchange UM-Server zum Weiterleiten des Anrufs. Mit ExumRouting werden zudem einige weitere Integrationsaspekte von Exchange UM behandelt, u. a. die Weiterleitung an eine automatische Telefonzentrale und der Teilnehmerzugriff.

  - OutboundRouting ermittelt das Gateway, das einen Anruf gemäß der gewählten Nummer und der Wählberechtigungen des Benutzers an eine Telefonnummer weiterleitet. OutboundRouting leitet Anrufe auch um, wenn ein Gateway einen Anruf nicht verarbeiten kann.

  - QoEAgent empfängt über SIP SERVICE-Anforderungen QoE-Datenberichte (Quality of Experience) von Endpunkten und sendet die Daten unter Verwendung von HTTP POST an die Zielwarteschlange auf dem Monitoring Server oder an Empfänger eines Drittanbieters. Ausführliche Informationen finden Sie unter [Deploying Monitoring in lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten an eine gezielte externe Bereitstellung.

  - AcpRouting leitet die für den Audiokonferenzanbieter bestimmten INVITE-Anforderungen an das Gateway des Audiokonferenzanbieters weiter.

Auf Edgeservern werden die folgenden Skripts ausgeführt:

  - IIMFilter

  - OptionsHandler beantwortet eingehende OPTIONS-Anforderungen mit **200 OK**, wenn die Anforderung für den aktuellen Server bestimmt ist. Dies wird für die Topologievalidierung verwendet.

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

