---
title: 'Lync Server 2013: Exchange Unified Messaging (um)-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd46b19ea52b56b70cc5bd4c459f2260a97306d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Exchange Unified Messaging (um)-Unterstützung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (um) für die Kombination von Sprachnachrichten und e-Mail-Messaging in einer einzelnen Messaging Infrastruktur. In Exchange 2013 besteht Exchange um aus dem Exchange um Dienst, der auf dem Postfachserver installiert und ausgeführt wird, und dem um-Anruf Router, der installiert ist und auf dem Client Zugriffsserver ausgeführt wird. Für lync Server 2013 Enterprise-VoIP-Bereitstellungen kombiniert Exchange um Sprachnachrichten und e-Mail-Nachrichten in einem einzelnen Speicher, auf den von einem Telefon (Outlook Voice Access) oder einem Computer aus zugegriffen werden kann. Exchange um und lync Server 2013 arbeiten zusammen, um Mailboxansage, Outlook Voice Access und automatische Telefonzentralen für Benutzer von Enterprise-VoIP bereitzustellen.

Zusätzlich zur Unterstützung der Integration in lokale Bereitstellungen von Exchange um unterstützt lync Server 2013 die Integration in gehostete Exchange um. Dies ermöglicht Ihnen die Bereitstellung von Voicemessaging für Ihre Benutzer, wenn Sie einige oder alle Benutzer zu einem gehosteten Exchange-Dienstanbieter wie beispielsweise Microsoft Exchange Online migrieren.

Lync Server 2013 unterstützt die folgenden Versionen:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Microsoft Exchange Server 2007 mit Service Pack 1 (SP1) (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

Sie können Exchange um nicht mit lync Server 2013 oder einer lync Server 2013 Datenbank collocate. Sie können Exchange um und lync Server 2013 in getrennten Gesamtstrukturen installieren.

<div>


> [!NOTE]  
> Für Enterprise-VoIP-Bereitstellungen, für die eine Nebenstellenanlage bereitgestellt wurde, ist Exchange um möglicherweise nicht erforderlich, da die Nebenstellenanlage weiterhin Voicemail und verwandte Dienste für alle Benutzer bereitstellen kann. Wenn Sie die Nebenstellenanlage schließlich zurückziehen (beispielsweise, wenn Sie SIP-Trunking für PSTN-Konnektivität (Public Switched Telephone Network) bereitstellen), müssen Sie Exchange um neu konfigurieren, um Benutzern, die zuvor das Voicemailsystem der Nebenstellenanlage verwendet haben, Voicemail bereitzustellen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Komponenten und Topologien für lokale Unified Messaging in lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Unterstützung für gehostete Exchange um Integration in lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

