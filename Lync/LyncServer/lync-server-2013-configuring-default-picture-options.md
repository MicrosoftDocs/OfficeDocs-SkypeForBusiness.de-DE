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

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Konfigurieren von Standardbild Optionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-22_

Standardmäßig werden die Bilder von Benutzern automatisch angezeigt. Wenn Benutzer Ihre Bilder ausblenden möchten, können Sie die Option " **meine Grafik ausblenden** " im lync-Client auswählen. Diese Einstellung wird jedoch von einigen anderen Office-Anwendungen ignoriert.

Wenn die Möglichkeit zum Anzeigen von Bildern auch beim Ausschalten durch den Benutzer ein Problem ist, können Sie die Einstellungen für die lync-Bildanzeige Global oder für eine Website oder einen Dienst ändern, sodass die Bilder der Benutzer standardmäßig nicht angezeigt werden. Verwenden Sie das folgende lync Server-Verwaltungsshell-Cmdlet, damit die Bilder des Benutzers nicht angezeigt werden, es sei denn, Sie wählen explizit die Option " **eigenes Bild anzeigen** " im Client aus:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Weitere Informationen zu diesem Cmdlet finden Sie in der Dokumentation zu " [CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) " in der lync Server-Verwaltungsshell.

</div>

<span> </span>

</div>

</div>

</div>

