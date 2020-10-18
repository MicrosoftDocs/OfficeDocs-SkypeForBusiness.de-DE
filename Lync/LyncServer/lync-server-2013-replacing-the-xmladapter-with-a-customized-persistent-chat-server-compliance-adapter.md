---
title: 'Lync Server 2013: Ersetzen des xmladapters durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter'
description: 'Lync Server 2013: Ersetzen Sie den XMLAdapter durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter.'
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
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576141"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="e0767-103">Ersetzen des xmladapters durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0767-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0767-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e0767-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e0767-105">Sie können einen benutzerdefinierten Adapter anstelle des mit dem Server für beständigen Chat installierten xmladapters schreiben.</span><span class="sxs-lookup"><span data-stu-id="e0767-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="e0767-106">Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="e0767-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="e0767-107">Sie müssen diese Assembly im Serverinstallationsordner für beständigen Chat aller Server im Pool für beständigen Chat platzieren.</span><span class="sxs-lookup"><span data-stu-id="e0767-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="e0767-108">Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.</span><span class="sxs-lookup"><span data-stu-id="e0767-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="e0767-109">Implementieren der IComplianceAdapter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0767-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="e0767-110">Die Schnittstelle ist in der Compliance.dll-Assembly im Namespace definiert `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="e0767-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="e0767-111">Die Schnittstelle definiert zwei Methoden, die Ihr benutzerdefinierter Adapter implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="e0767-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="e0767-112">Der Kompatibilitätsserver für beständigen Chat ruft diese Methode auf, wenn der Adapter zuerst geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e0767-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="e0767-113">Der `AdapterConfig` enthält die Kompatibilitäts Konfiguration für beständigen Chat, die für den Kompatibilitätsadapter relevant ist.</span><span class="sxs-lookup"><span data-stu-id="e0767-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="e0767-114">Der Kompatibilitätsserver für beständigen Chat ruft diese Methode in periodischen Intervallen auf, solange neue Daten zu übersetzen sind.</span><span class="sxs-lookup"><span data-stu-id="e0767-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="e0767-115">Dieses Zeitintervall entspricht dem `RunInterval` in der Kompatibilitäts Konfiguration für beständigen Chat festgelegten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="e0767-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="e0767-116">Das `ConversationCollection` enthält die Unterhaltungsinformationen, die beim letzten Aufruf dieser Methode gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="e0767-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

