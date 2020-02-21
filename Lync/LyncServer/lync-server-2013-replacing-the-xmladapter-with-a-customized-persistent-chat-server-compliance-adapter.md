---
title: 'Lync Server 2013: Ersetzen des xmladapters durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Ersetzen des xmladapters durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Sie können einen benutzerdefinierten Adapter anstelle des mit dem Server für beständigen Chat installierten xmladapters schreiben. Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert. Sie müssen diese Assembly im Serverinstallationsordner für beständigen Chat aller Server im Pool für beständigen Chat platzieren. Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementieren der IComplianceAdapter-Schnittstelle

Die Schnittstelle ist in der Assembly Compliance. dll im Namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`definiert. Die Schnittstelle definiert zwei Methoden, die Ihr benutzerdefinierter Adapter implementieren muss.

    void SetConfig(AdapterConfig config)

Der Kompatibilitätsserver für beständigen Chat ruft diese Methode auf, wenn der Adapter zuerst geladen wird. Der `AdapterConfig` enthält die Kompatibilitäts Konfiguration für beständigen Chat, die für den Kompatibilitätsadapter relevant ist.

    void Translate(ConversationCollection conversations)

Der Kompatibilitätsserver für beständigen Chat ruft diese Methode in periodischen Intervallen auf, solange neue Daten zu übersetzen sind. Dieses Zeitintervall entspricht dem `RunInterval` in der Kompatibilitäts Konfiguration für beständigen Chat festgelegten Zeitraum.

Das `ConversationCollection` enthält die Unterhaltungsinformationen, die beim letzten Aufruf dieser Methode gesammelt wurden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

