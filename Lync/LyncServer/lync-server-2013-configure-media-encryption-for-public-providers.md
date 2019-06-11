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
ms.openlocfilehash: 1496bda01456593066efd212241e3d930f1e2cc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-12_

Wenn Sie eine Audio/Video-Föderation (A/V) mit Windows Live Messenger implementieren, müssen Sie zwei Parameter ändern: die lync Server-Verschlüsselungsstufe und die EnablePublicCloudAccess-Richtlinie. Standardmäßig ist die Verschlüsselungsstufe auf Required eingestellt. Sie müssen diese Einstellung in unterstützt ändern. Wenn die EnablePublicCloudAccess-Richtlinie auf "false" festgelegt ist, muss diese auf " **true**" festgelegt werden. Sie können dies in der lync Server-Verwaltungsshell tun.

<div>

## <a name="configure-federation-for-windows-live"></a>Konfigurieren von Federation für Windows Live

1.  Starten Sie die lync Server-Verwaltungsshell auf dem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie an der Eingabeaufforderung die folgenden Befehle ein:
    
       ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Dieser Schritt ist erforderlich, da Windows Live Messenger die Verschlüsselung von Audio/Video nicht unterstützt. Mit dem Befehl wird Ihre globale Richtlinie auf eine Verschlüsselungseinstellung für die Unterstützung festgelegt, anstatt die Audio/Video-Daten zu verschlüsseln. Clients, die die Verschlüsselung unterstützen, verwenden weiterhin die Verschlüsselung, wie lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

