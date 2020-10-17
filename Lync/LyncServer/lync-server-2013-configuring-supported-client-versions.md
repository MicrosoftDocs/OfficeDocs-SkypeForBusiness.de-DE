---
title: 'Lync Server 2013: Konfigurieren unterstützter Clientversionen'
description: 'Lync Server 2013: Konfigurieren unterstützter Clientversionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74396314cae864fae134531b71375c750be8d3da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556881"
---
# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Konfigurieren unterstützter Clientversionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-14_

In lync Server 2013 können Sie clientversionsrichtlinien einrichten, um die Versionen von Clients anzugeben, die in Ihrer Umgebung unterstützt werden. Darüber hinaus können Sie mithilfe der globalen Clientversionskonfiguration eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist und die deshalb nicht explizit unterstützt oder eingeschränkt werden.

Sie können auch mithilfe von Clientversionsrichtlinien Clientupdates verwalten. Wenn Sie eine Clientversionsrichtlinie festlegen und die Optionen **Zulassen und Upgrade** und **Blockieren und Upgrade** verwenden, erhalten Clients aktualisierte Software vom Windows Server Update Service (falls Sie diesen Dienst nutzen) oder von Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Einstellungen für die Clientversionsrichtlinie

Die standardmäßige clientversionsrichtlinie erfordert, dass alle Clients lync ausführen. Wenn Clients in Ihrer Umgebung frühere Versionen von Communicator ausgeführt werden, müssen Sie möglicherweise die Client Versionsregeln neu konfigurieren, um zu verhindern, dass Clients und Geräte beim Herstellen einer Verbindung mit lync Server 2013 unerwartet blockiert oder aktualisiert werden. Sie können die Standardregel ändern oder in der Liste Client Versionsrichtlinie eine höhere Regel hinzufügen, um die Standardregel außer Kraft zu setzen. Darüber hinaus sollten Sie die Client Versionsrichtlinie so konfigurieren, dass die neuesten Updates erforderlich sind, da kumulative Updates (CUS) veröffentlicht werden. Ausführliche Informationen finden Sie unter [angeben der Clientanwendungen,](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) die für die Anmeldung bei lync Server 2013 in der Betriebsdokumentation verwendet werden können.

</div>

</div>

<span> </span>

</div>

</div>

</div>

