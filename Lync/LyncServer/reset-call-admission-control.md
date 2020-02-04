---
title: Zurücksetzen der Anrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6956b1a871a4a0a5c7e758d2890a58989f5ac8a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="e243c-102">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="e243c-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e243c-103">_**Letztes Änderungsdatum des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="e243c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="e243c-104">Wenn ein lync Server 2010-Front-End-Pool Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen lync Server 2013-Pool verschieben, bevor Sie den lync Server 2010-Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="e243c-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="e243c-105">So setzen Sie CAC zurück</span><span class="sxs-lookup"><span data-stu-id="e243c-105">To reset CAC</span></span>

1.  <span data-ttu-id="e243c-106">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="e243c-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="e243c-107">Klicken Sie mit der rechten Maustaste auf den Websiteknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e243c-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e243c-108">Vergewissern Sie sich, dass unter Einstellungen für die **Anrufsteuerung**die Option **Anrufsteuerung aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e243c-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="e243c-109">Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufannahme Steuerung (CAC)** den lync Server 2013-Pool aus, der CAC hosten soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e243c-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="e243c-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e243c-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

