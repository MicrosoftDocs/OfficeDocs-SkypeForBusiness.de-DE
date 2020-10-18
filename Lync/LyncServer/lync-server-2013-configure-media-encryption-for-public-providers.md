---
title: 'Lync Server 2013: Konfigurieren der Medienverschlüsselung für öffentliche Anbieter'
description: 'Lync Server 2013: Konfigurieren der Medienverschlüsselung für öffentliche Anbieter.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577621"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="385eb-103">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="385eb-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="385eb-104">_**Letztes Änderungsstand des Themas:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="385eb-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="385eb-105">Wenn Sie einen a/V-Verbund (Audio/Video) mit Windows Live Messenger implementieren, müssen Sie zwei Parameter ändern: die lync Server Verschlüsselungsebene und die EnablePublicCloudAccess-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="385eb-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="385eb-106">Standardmäßig ist die Verschlüsselungsstufe auf "Erforderlich" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="385eb-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="385eb-107">Sie müssen diese Einstellung in "Unterstützt" ändern.</span><span class="sxs-lookup"><span data-stu-id="385eb-107">You must change this setting to Supported.</span></span> <span data-ttu-id="385eb-108">Die Richtlinie "EnablePublicCloudAccess" ist auf "False" festgelegt, sie muss jedoch auf **True** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="385eb-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="385eb-109">Dies können Sie in der lync Server-Verwaltungsshell tun.</span><span class="sxs-lookup"><span data-stu-id="385eb-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="385eb-110">Konfigurieren des Verbunds für Windows Live</span><span class="sxs-lookup"><span data-stu-id="385eb-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="385eb-111">Starten Sie die lync Server-Verwaltungsshell auf dem Front-End-Server: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="385eb-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="385eb-112">Geben Sie an der Eingabeaufforderung die folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="385eb-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="385eb-113">Dieser Schritt ist erforderlich, weil Windows Live Messenger die Audio-/Videoverschlüsselung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="385eb-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="385eb-114">Mithilfe des Befehls wrid die globale Richtlinie auf eine Einstellung zur Unterstützung der Verschlüsselung festgelegt, anstatt die Verschlüsselung der Audio-/Videodaten zu fordern.</span><span class="sxs-lookup"><span data-stu-id="385eb-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="385eb-115">Für Clients, die die Verschlüsselung unterstützen, wird weiterhin Verschlüsselung verwendet, beispielsweise lync 2013.</span><span class="sxs-lookup"><span data-stu-id="385eb-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

