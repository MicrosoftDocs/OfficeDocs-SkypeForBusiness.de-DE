---
title: 'Lync Server 2013: Vorbereiten der Umgebung für VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a3fb2563e287f24d49c23a468b4a44528707b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="7c155-102">Vorbereiten der Lync Server 2013-Umgebung für VDI</span><span class="sxs-lookup"><span data-stu-id="7c155-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c155-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7c155-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7c155-104">Um die Umgebung für das lync-VDI-Plug-in vorzubereiten, muss der Administrator die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="7c155-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="7c155-105">Stellen Sie in lync Server 2013 sicher, dass EnableMediaRedirection für alle VDI-Benutzer auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7c155-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="7c155-106">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) und dem Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) ".</span><span class="sxs-lookup"><span data-stu-id="7c155-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="7c155-107">Installieren Sie auf dem Rechenzentrums Computer den lync 2013-Client auf allen virtuellen Computern.</span><span class="sxs-lookup"><span data-stu-id="7c155-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="7c155-108">Installieren Sie auf den lokalen Computern das lync VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="7c155-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

