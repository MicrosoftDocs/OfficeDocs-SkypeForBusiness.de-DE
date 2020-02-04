---
title: Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="56b46-102">Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="56b46-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56b46-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="56b46-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="56b46-104">Bei diesem Verfahren werden die VoIP-Routen so geändert, dass der lync Server 2013-Vermittlungsserver anstelle des Legacy Office Communications Server 2007 R2-Vermittlungsservers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56b46-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="56b46-105">So ändern Sie die VoIP-Routen zur Verwendung des neuen Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="56b46-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="56b46-106">Systemsteuerung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56b46-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="56b46-107">Wählen Sie im linken Bereich die Option **VoIP-Routing** und dann **Route**aus.</span><span class="sxs-lookup"><span data-stu-id="56b46-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="56b46-108">Klicken Sie auf **neu** , um eine neue VoIP-Route zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56b46-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="56b46-109">Füllen Sie die folgenden Felder aus:</span><span class="sxs-lookup"><span data-stu-id="56b46-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="56b46-110">**Name**: Geben Sie einen aussagekräftigen Namen für die VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="56b46-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="56b46-111">Für dieses Dokument werden wir **W15PSTNRoute**verwenden.</span><span class="sxs-lookup"><span data-stu-id="56b46-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="56b46-112">**Beschreibung**: Geben Sie eine kurze Beschreibung der VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="56b46-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="56b46-113">Überspringen Sie alle verbleibenden Abschnitte, bis Sie **zugeordnete Gateways**erreichen.</span><span class="sxs-lookup"><span data-stu-id="56b46-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="56b46-114">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="56b46-114">Click **Add**.</span></span> <span data-ttu-id="56b46-115">Wählen Sie das neue Standardgateway aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b46-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="56b46-116">Klicken Sie unter **zugeordnete PSTN-Nutzungen**auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="56b46-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="56b46-117">Wählen Sie auf der Seite **PSTN-Verwendungsdaten Satz auswählen** einen Datensatznamen aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b46-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="56b46-118">Klicken Sie auf der Seite **neue VoIP-Route** auf **OK** , um die **VoIP-Route**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56b46-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="56b46-119">Wählen Sie auf der Seite **VoIP-Routing** die Option **Route**aus.</span><span class="sxs-lookup"><span data-stu-id="56b46-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="56b46-120">Verschieben Sie die neu erstellte Route an den Anfang der Liste, und wählen Sie dann **Commit**aus.</span><span class="sxs-lookup"><span data-stu-id="56b46-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

