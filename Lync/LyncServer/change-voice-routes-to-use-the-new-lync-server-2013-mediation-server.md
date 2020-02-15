---
title: Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver
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
ms.openlocfilehash: c8edaf6c8d912e9784a0a3df6dfe27a45aa873e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="212c8-102">Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="212c8-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="212c8-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="212c8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="212c8-104">Bei diesem Verfahren werden die VoIP-Routen so geändert, dass die lync Server 2013 Vermittlungsserver anstelle der Legacy Office Communications Server 2007 R2 Vermittlungsserver verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="212c8-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="212c8-105">So ändern Sie die VoIP-Routen für die Verwendung des neuen Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="212c8-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="212c8-106">Lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="212c8-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="212c8-107">Wählen Sie im linken Bereich **VoIP-Routing** und dann **Route** aus.</span><span class="sxs-lookup"><span data-stu-id="212c8-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="212c8-108">Klicken Sie auf **Neu**, um eine neue VoIP-Route zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="212c8-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="212c8-109">Füllen Sie die folgenden Felder aus:</span><span class="sxs-lookup"><span data-stu-id="212c8-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="212c8-p101">**Name**: Geben Sie einen beschreibenden Namen für die VoIP-Route ein. Im Rahmen dieses Dokuments wird **W15PSTNRoute** verwendet.</span><span class="sxs-lookup"><span data-stu-id="212c8-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="212c8-112">**Beschreibung**: Geben Sie eine kurze Beschreibung für die VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="212c8-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="212c8-p102">Überspringen Sie alle verbleibenden Abschnitte, bis Sie zu **Zugeordnete Gateways** gelangen. Klicken Sie auf **Hinzufügen**. Wählen Sie das neue Standardgateway aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="212c8-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="212c8-116">Klicken Sie unter **Zugeordnete PSTN-Verwendungen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="212c8-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="212c8-117">Wählen Sie auf der Seite **PSTN-Verwendungseintrag auswählen** den Namen eines Eintrags aus, klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="212c8-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="212c8-118">Klicken Sie auf der Seite **Neue VoIP-Route** auf **OK**, um die **VoIP-Route** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="212c8-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="212c8-119">Wählen Sie auf der Seite **VoIP-Routing** die Option **Route** aus.</span><span class="sxs-lookup"><span data-stu-id="212c8-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="212c8-120">Verschieben Sie die neu erstellte Route an den Anfang der Liste, und wählen Sie dann **Commit** aus.</span><span class="sxs-lookup"><span data-stu-id="212c8-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

