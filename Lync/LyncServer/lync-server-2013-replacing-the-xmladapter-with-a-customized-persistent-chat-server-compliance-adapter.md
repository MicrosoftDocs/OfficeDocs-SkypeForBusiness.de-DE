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
ms.openlocfilehash: 9235c57a055131049251d17b75f73a4370cc5f2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="a7944-102">Ersetzen des xmladapters durch einen angepassten beständigen Chat Server-Kompatibilitätsadapter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7944-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7944-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a7944-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a7944-104">Sie können einen benutzerdefinierten Adapter schreiben, anstatt den XMLAdapter zu verwenden, der mit dem Server für beständigen Chat installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a7944-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="a7944-105">Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a7944-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="a7944-106">Sie müssen diese Assembly im beständigen Chat Server-Installationsordner für jeden Server im beständigen Chat Serverpool platzieren.</span><span class="sxs-lookup"><span data-stu-id="a7944-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="a7944-107">Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.</span><span class="sxs-lookup"><span data-stu-id="a7944-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="a7944-108">Implementieren der IComplianceAdapter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7944-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="a7944-109">Die Schnittstelle ist in der Assembly Compliance. dll im Namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`definiert.</span><span class="sxs-lookup"><span data-stu-id="a7944-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="a7944-110">Die Schnittstelle definiert zwei Methoden, die Ihr benutzerdefinierter Adapter implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="a7944-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="a7944-111">Der beständige Chat-Kompatibilitätsserver ruft diese Methode auf, wenn der Adapter zuerst geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a7944-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="a7944-112">Die `AdapterConfig` Kompatibilitäts Konfiguration für beständigen Chat enthält, die für den Kompatibilitätsadapter relevant ist.</span><span class="sxs-lookup"><span data-stu-id="a7944-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="a7944-113">Der beständige Chat-Kompatibilitätsserver ruft diese Methode in regelmäßigen Intervallen auf, solange neue zu übersetzende Daten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a7944-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="a7944-114">Dieses Zeitintervall entspricht dem `RunInterval` in der Compliance-Konfiguration für beständigen Chat angegebenen Satz.</span><span class="sxs-lookup"><span data-stu-id="a7944-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="a7944-115">Die `ConversationCollection` enthält die Konversations Informationen, die beim letzten Aufrufen dieser Methode erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="a7944-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

