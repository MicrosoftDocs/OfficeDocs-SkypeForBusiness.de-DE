---
title: 'Lync Server 2013: Konfigurieren der Medienverschlüsselung für öffentliche Anbieter'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="b9345-102">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9345-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9345-103">_**Letztes Änderungsdatum des Themas:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="b9345-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="b9345-104">Wenn Sie eine Audio/Video-Föderation (A/V) mit Windows Live Messenger implementieren, müssen Sie zwei Parameter ändern: die lync Server-Verschlüsselungsstufe und die EnablePublicCloudAccess-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b9345-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="b9345-105">Standardmäßig ist die Verschlüsselungsstufe auf Required eingestellt.</span><span class="sxs-lookup"><span data-stu-id="b9345-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="b9345-106">Sie müssen diese Einstellung in unterstützt ändern.</span><span class="sxs-lookup"><span data-stu-id="b9345-106">You must change this setting to Supported.</span></span> <span data-ttu-id="b9345-107">Wenn die EnablePublicCloudAccess-Richtlinie auf "false" festgelegt ist, muss diese auf " **true**" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b9345-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="b9345-108">Sie können dies in der lync Server-Verwaltungsshell tun.</span><span class="sxs-lookup"><span data-stu-id="b9345-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="b9345-109">Konfigurieren von Federation für Windows Live</span><span class="sxs-lookup"><span data-stu-id="b9345-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="b9345-110">Starten Sie die lync Server-Verwaltungsshell auf dem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b9345-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b9345-111">Geben Sie an der Eingabeaufforderung die folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="b9345-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b9345-112">Dieser Schritt ist erforderlich, da Windows Live Messenger die Verschlüsselung von Audio/Video nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9345-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="b9345-113">Mit dem Befehl wird Ihre globale Richtlinie auf eine Verschlüsselungseinstellung für die Unterstützung festgelegt, anstatt die Audio/Video-Daten zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b9345-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="b9345-114">Clients, die die Verschlüsselung unterstützen, verwenden weiterhin die Verschlüsselung, wie lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b9345-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

