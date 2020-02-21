---
title: 'Lync Server 2013: Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Entfernen von Geräteaktualisierungsdateien, die keinem Gerät in lync Server 2013 zugeordnet sind

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Jedes Mal, wenn neue Geräte Updates in das System hochgeladen werden, wird eine entsprechende geräteaktualisierungsregel erstellt. Standardmäßig werden diese neuen geräteaktualisierungsregeln dem Status Ausstehend zugewiesen. Dies bedeutet, dass die Regeln heruntergeladen und auf Testgeräten installiert werden können, jedoch nicht auf Produktionsgeräten, sodass Sie die Updates testen können, bevor Sie für die Benutzer verfügbar gemacht werden. Basierend auf den Tests können Sie das Update entweder annehmen und bereitstellen oder ablehnen und löschen. Wenn Sie eine Aktualisierung ablehnen, wird die Geräteaktualisierung nicht von der entsprechenden geräteaktualisierungsregel abgewiesen.

<div>


Geräteaktualisierungsdateien, die keinem Gerät mehr zugeordnet sind, können mithilfe von Windows PowerShell und dem Cmdlet **Clear-CsDeviceUpdateFile** entfernt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.



</div>

<div>


  - Mit dem folgenden Befehl werden beispielsweise alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com entfernt, die keinem Gerät mehr zugeordnet sind:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

