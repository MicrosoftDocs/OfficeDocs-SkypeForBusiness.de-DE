---
title: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts eines Konferenz Geräts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bd3cfa6099d45cbad2d15ed164652756f50f5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Erstellen oder Ändern eines Kontaktobjekts für ein Konferenzgerät in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-02_

Erstellen Sie zum Erstellen eines Konferenzraum Objekts zunächst ein Active Directory Benutzerkonto zum Darstellen des Geräts. Verwenden Sie dann das Cmdlet **enable-csmeetingroom "** , um zu ermöglichen, dass dieses Konto als Konferenzgerät fungiert. Wenn Sie die Eigenschaften eines vorhandenen Konferenz Geräts ändern müssen, verwenden Sie das Cmdlet " **Sets-csmeetingroom"** ".

Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Erstellen eines Konferenz Geräts

  - Nachdem Sie das Active Directory-Benutzerkonto erstellt haben, das das neue Konferenzgerät darstellt, aktivieren Sie es mithilfe des Cmdlets **enable-csmeetingroom "** . Achten Sie darauf, eine) die Identität des Konferenz Geräts, b) den registrierungsstellenpool, in dem das Raum Konto verwaltet wird, und c) die SIP-Adresse, die diesem Konto zugewiesen werden soll, einzubeziehen. Beispiel:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Ändern eines Konferenz Geräts

  - Verwenden Sie das Cmdlet " **csmeetingroom"** ", um die Eigenschaftswerte eines vorhandenen Konferenz Geräts zu ändern. Mit dem folgenden Befehl wird beispielsweise die Telefonnummer (LineUri) aktualisiert, die einem Konferenzgerät zugeordnet ist:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-csmeetingroom "](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und im Cmdlet [csmeetingroom"](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

