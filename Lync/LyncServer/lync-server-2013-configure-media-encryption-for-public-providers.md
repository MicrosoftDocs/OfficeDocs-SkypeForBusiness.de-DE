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
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-12_

Wenn Sie einen a/V-Verbund (Audio/Video) mit Windows Live Messenger implementieren, müssen Sie zwei Parameter ändern: die lync Server Verschlüsselungsebene und die EnablePublicCloudAccess-Richtlinie. Standardmäßig ist die Verschlüsselungsstufe auf "Erforderlich" festgelegt. Sie müssen diese Einstellung in "Unterstützt" ändern. Die Richtlinie "EnablePublicCloudAccess" ist auf "False" festgelegt, sie muss jedoch auf **True** festgelegt werden. Dies können Sie in der lync Server-Verwaltungsshell tun.

<div>

## <a name="configure-federation-for-windows-live"></a>Konfigurieren des Verbunds für Windows Live

1.  Starten Sie die lync Server-Verwaltungsshell auf dem Front-End-Server: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie an der Eingabeaufforderung die folgenden Befehle ein:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Dieser Schritt ist erforderlich, weil Windows Live Messenger die Audio-/Videoverschlüsselung nicht unterstützt. Mithilfe des Befehls wrid die globale Richtlinie auf eine Einstellung zur Unterstützung der Verschlüsselung festgelegt, anstatt die Verschlüsselung der Audio-/Videodaten zu fordern. Für Clients, die die Verschlüsselung unterstützen, wird weiterhin Verschlüsselung verwendet, beispielsweise lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

