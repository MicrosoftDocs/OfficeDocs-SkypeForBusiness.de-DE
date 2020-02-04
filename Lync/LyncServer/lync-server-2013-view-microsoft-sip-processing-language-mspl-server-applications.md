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
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-09-26_

Eine Microsoft SIP Processing Language (MSPL)-Serveranwendung ist eine skriptbasierte Anwendung, die eine Skriptsprache anstelle der Microsoft lync 2010-API verwendet. MSPL bietet eine genauere Steuerung des Filter-und Proxy Verhaltens sowie eine Möglichkeit zum Verteilen bestimmter Nachrichten an transaktionsbasierte SIP-Anwendungen. MSPL wird speziell zum Filtern und Weiterleiten von SIP-Nachrichten verwendet. MSPL-Anwendungen werden im gleichen Prozess wie das userservices-Modul ausgeführt, während ein Programm, das auf der lync 2010-API basiert, in einem separaten Prozess ausgeführt wird.

Sie können die Seite **Serveranwendung** in der Gruppe **Topologie** der lync Server-Systemsteuerung verwenden, um eine Liste der MSPL-Server Anwendungen anzuzeigen, die auf Front-End-Servern in ihrer lync Server 2013-Umgebung ausgeführt werden. In der Liste werden die für die einzelnen Pools verfügbaren Skripts sowie deren Aktivierung oder kritische Anzeige angezeigt. Die Skripts werden in der Reihenfolge ausgeführt, in der Sie aufgelistet sind.

Zu diesen Skripts gehören die folgenden:

  - ClientVersionFilter bietet dem Administrator die Möglichkeit, die Version der Clients anzugeben, die von einem Pool unterstützt werden. Der Clientversionsfilter überprüft die Client Version und kann entweder verhindern, dass der Client sich anmeldet oder den Benutzer mit einer Meldung zeigt, die angibt, dass er einen Client verwendet, der nicht unterstützt wird. Der Clientversionsfilter kann auch so konfiguriert werden, dass dem Benutzer eine Meldung angezeigt wird, die die URL der neuesten herunterladbaren Version des Clients enthält.

  - TranslationService übersetzt eine Zahl, die ein Benutzer entsprechend den vom Administrator definierten Normalisierungsregeln zu einer E. 164-Nummer wählt. Ausführliche Informationen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation erzwingt die Föderations Überprüfung auf Mandantenebene für Mandantenübergreifende und eingehende Nachrichten von externen Bereitstellungen.

  - UserServices ist die SIP-Registrierungsstelle, Anwesenheits-und Konferenz Komponente eines Front-End-Servers. Es bietet eng integrierte Chat-, Anwesenheits-und Konferenzfeatures, die auf dem SIP-Proxy aufgebaut sind.

  - InterClusterRouting ist für das Weiterleiten von Anrufen an den primären Registrierungspool des anrufenden verantwortlich. Ausführliche Informationen finden Sie unter [Front-End-Server-VoIP-Komponenten für lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (intelligenter Chat Filter) blockiert Nachrichten, die klickable-URLs enthalten, oder die versuchen, Dateiübertragungen zu initiieren. IIMFilter überprüft auch die Client Version im Namen des Servers. IIMFilter wirkt sich auf Dateiübertragungen aus, die entweder mit lync Server oder Communicator initiiert werden. Standardmäßig sind klickable-Links deaktiviert, indem Sie vor dem ersten Zeichen des Links einen Unterstrich hinzufügen. Ein Administrator kann dieses Verhalten so ändern, dass der Link blockiert wird, wobei Nachrichten, die Klick Bare URLs enthalten oder die versuchen, eine Dateiübertragung zu initiieren, vom Server blockiert werden, um die beabsichtigten Ziele zu erreichen. IIMFilter ist auf allen Servern mit lync Server mit Ausnahme von Proxy Servern und Archivierungsservern installiert.

  - UserPinService wird verwendet, um persönliche Identifikationsnummern (Pins) des Benutzers für Einwahlkonferenzen zu überprüfen.

  - DefaultRouting ist die Standardrouting Anwendung für Server, auf denen lync Server ausgeführt wird. Sie ist standardmäßig aktiviert. Die Routing Anwendung ist auf allen Standard Edition-und Enterprise Edition-Servern installiert.

  - ExumRouting leitet Anrufe an Exchange Server Unified Messaging (um) weiter. ExumRouting bestimmt den entsprechenden Exchange um-Server zum Weiterleiten des Anrufs an die Stelle, an der eine neue Voicemail-Nachricht hinterlegt werden soll. ExumRouting behandelt auch einige andere Exchange um-Integrationsaspekte, einschließlich Routing an automatische Telefonzentrale und Teilnehmerzugriff.

  - OutboundRouting bestimmt das Gateway, das einen Anruf an eine Telefonnummer weiterleitet, entsprechend der gewählten Nummer und der Wähl Berechtigung des Benutzers. OutboundRouting behandelt auch das Umleiten von anrufen, wenn ein Gateway keinen Anruf verarbeiten kann.

  - QoEAgent erhält QoE-Daten Berichte (Quality of Experience) von Endpunkten über SIP-Dienstanforderungen und sendet die Daten mithilfe von HTTP Post an die Zielwarteschlange auf dem Überwachungs Server oder an Drittanbieter. Ausführliche Informationen finden Sie unter [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation erzwingt die Föderations Überprüfung auf Mandantenebene für Nachrichten, die an eine Ziel externe Bereitstellung gesendet werden.

  - AcpRouting-Proxys laden Anforderungen, die für den Audiokonferenz-Anbieter bestimmt sind, an das Audiokonferenz-Anbieter Gateway ein.

Zu den Skripts, die auf Edgeserver ausgeführt werden, gehören die folgenden:

  - IIMFilter

  - OptionsHandler reagiert auf eingehende Options Anforderungen mit **200 OK** , wenn die Anforderung für den aktuellen Server bestimmt ist. Diese wird für die Topologie-Validierung verwendet.

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

