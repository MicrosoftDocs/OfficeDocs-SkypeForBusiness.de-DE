---
title: 'Lync Server 2013: Importieren von geräteaktualisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ddeb9d37d36d6ab18467e04e4a7c46b9b8576fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526722"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a>Importieren von geräteaktualisierungsregeln in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Geräteaktualisierungsregeln können nur mit Windows PowerShell und dem Cmdlet **Import-CsDeviceUpdate** importiert werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>So importieren Sie geräteaktualisierungsregeln auf einen einzelnen Webserver

  - Der folgende Befehl importiert geräteaktualisierungsregeln auf den Webserver ATL-CS-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>So importieren Sie geräteaktualisierungsregeln auf alle Webserver

  - In diesem Beispiel werden geräteaktualisierungsregeln auf alle in Ihrer Organisation bereitgestellten Webserver importiert. Damit dieser Befehl funktioniert, müssen die Ordner \\ \\ ATL-FS-001.litwareinc.com- \\ Updates freigegeben und für alle Webserver verfügbar sein.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Ausführliche Informationen finden Sie im Hilfethema zum [Import-CsDeviceUpdate-](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anzeigen von Informationen zu geräteaktualisierungsregeln in lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Genehmigen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

