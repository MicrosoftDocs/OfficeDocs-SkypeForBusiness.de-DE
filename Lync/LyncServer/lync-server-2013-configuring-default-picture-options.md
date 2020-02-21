---
title: 'Lync Server 2013: Konfigurieren von Standardbild Optionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3b5007a1d850e1a271c507290c48a2c8d345c7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="9a0ca-102">Konfigurieren von Standardbild Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a0ca-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a0ca-103">_**Letztes Änderungsstand des Themas:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="9a0ca-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="9a0ca-104">Standardmäßig werden die Bilder von Benutzern automatisch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a0ca-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="9a0ca-105">Wenn Benutzer Ihre Bilder ausblenden möchten, können Sie die Option " **meine Grafik ausblenden** " im lync-Client auswählen.</span><span class="sxs-lookup"><span data-stu-id="9a0ca-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="9a0ca-106">Diese Einstellung wird jedoch von einigen anderen Office-Anwendungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9a0ca-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="9a0ca-107">Wenn die Möglichkeit zum Anzeigen von Bildern auch beim Ausschalten durch den Benutzer ein Problem ist, können Sie die Einstellungen für die lync-Bildanzeige Global oder für eine Website oder einen Dienst ändern, sodass die Bilder der Benutzer standardmäßig nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a0ca-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="9a0ca-108">Verwenden Sie das folgende lync Server-Verwaltungsshell-Cmdlet, damit die Bilder des Benutzers nicht angezeigt werden, es sei denn, Sie wählen explizit die Option " **eigenes Bild anzeigen** " im Client aus:</span><span class="sxs-lookup"><span data-stu-id="9a0ca-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="9a0ca-109">Weitere Informationen zu diesem Cmdlet finden Sie in der Dokumentation zu " [CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) " in der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="9a0ca-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

