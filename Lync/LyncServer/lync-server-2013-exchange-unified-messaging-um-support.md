---
title: 'Lync Server 2013: Unterstützung für Exchange Unified Messaging (UM)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Unterstützung für Exchange Unified Messaging (UM) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (um) zum Kombinieren von Voicemail und e-Mail-Messaging in einer einzelnen Messaginginfrastruktur. In Exchange 2013 besteht Exchange um aus dem Exchange um-Dienst, der auf dem Postfachserver installiert ist und ausgeführt wird, und dem um-Anruf Router, der auf dem Client Zugriffsserver installiert ist und ausgeführt wird. Bei lync Server 2013 Enterprise-VoIP-Bereitstellungen kombiniert Exchange um Sprachnachrichten und e-Mail-Nachrichten in einem einzigen Speicher, auf den von einem Telefon (also Outlook Voice Access) oder einem Computer aus zugegriffen werden kann. Exchange um-und lync Server 2013 arbeiten zusammen, um Benutzern von Enterprise-VoIP die Anrufannahme, Outlook Voice Access und automatische Telefonzentralendienste bereitzustellen.

Neben der Unterstützung für die Integration in lokale Bereitstellungen von Exchange um unterstützt lync Server 2013 die Integration in gehostete Exchange um. Auf diese Weise können Sie Ihren Benutzern Sprachnachrichten senden, wenn Sie einige oder alle von Ihnen zu einem gehosteten Exchange-Dienstanbieter wie Microsoft Exchange Online migrieren.

Lync Server 2013 unterstützt die folgenden Versionen:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Microsoft Exchange Server 2007 mit Service Pack 1 (SP1) (erforderlich) oder neuestes Service Pack (empfohlen)

Sie können Exchange um nicht mit lync Server 2013 oder einer lync Server 2013-Datenbank collocate. Sie können Exchange um-und lync Server 2013 in getrennten Gesamtstrukturen installieren.

<div>


> [!NOTE]  
> Exchange um ist möglicherweise für Enterprise-VoIP-Bereitstellungen, für die eine Telefonanlage bereitgestellt wurde, nicht erforderlich, da die Telefonanlage weiterhin Voicemail und verwandte Dienste für alle Benutzer bereitstellen kann. Wenn Sie die Telefonanlage schließlich zurückziehen (wenn Sie beispielsweise SIP-Trunking für PSTN-Konnektivität (Public Switched Telephone Network) bereitstellen), müssen Sie Exchange um für die Bereitstellung von Voicemail für Benutzer neu konfigurieren, die zuvor das Telefonanlagen-Voicemailsystem verwendet haben.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Komponenten und Topologien für lokales Unified Messaging in Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Unterstützung für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

