---
title: 'Lync Server 2013: Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Entfernen von Geräteaktualisierungsdateien, die nicht mit einem Gerät in lync Server 2013 verknüpft sind

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Jedes Mal, wenn neue Geräte Updates in das System hochgeladen werden, wird eine entsprechende geräteaktualisierungsregel erstellt. Standardmäßig werden diese neuen geräteaktualisierungsregeln dem Status "Ausstehend" zugewiesen. Das bedeutet, dass die Regeln auf Testgeräten heruntergeladen und installiert werden können, aber nicht auf Produktionsgeräten, sodass Sie die Updates testen können, bevor Sie Sie für Benutzer verfügbar machen. Basierend auf den Tests können Sie das Update entweder annehmen und bereitstellen oder ablehnen und löschen. Wenn Sie ein Update ablehnen, wird das Geräteupdate von seiner geräteaktualisierungsregel nicht zugeordnet.

<div>


Geräteaktualisierungsdateien, die keinem Gerät mehr zugeordnet sind, können mithilfe von Windows PowerShell und dem Cmdlet " **Clear-CsDeviceUpdateFile** " entfernt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>


  - Mit dem folgenden Befehl werden beispielsweise alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com entfernt, die keinem Gerät mehr zugeordnet sind:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

