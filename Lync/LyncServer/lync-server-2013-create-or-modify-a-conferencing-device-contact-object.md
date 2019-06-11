---
title: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts für Konferenzgeräte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b468b2338d115e7b646c28fd4d0b310b6e132d79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Erstellen oder Ändern eines Kontaktobjekts für Konferenzgeräte in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-02_

Zum Erstellen eines Konferenzraum Objekts erstellen Sie zunächst ein Active Directory-Benutzerkonto, um das Gerät darzustellen. Verwenden Sie dann das Cmdlet **enable-CsMeetingRoom** , damit dieses Konto als Konferenzgerät funktioniert. Wenn Sie die Eigenschaften eines vorhandenen Konferenz Geräts ändern müssen, verwenden Sie das Cmdlet " **Satz-CsMeetingRoom** ".

Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Erstellen eines Konferenz Geräts

  - Nachdem Sie das Active Directory-Benutzerkonto erstellt haben, das das neue Konferenzgerät darstellt, aktivieren Sie es mithilfe des Cmdlets **enable-CsMeetingRoom** . Stellen Sie sicher, dass Sie a) die Konferenzgeräte Identität, b) den Registrar-Pool, in dem das Raumkonto verwaltet wird, und c) die SIP-Adresse einbeziehen, die diesem Konto zugewiesen werden soll. Beispiel:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Ändern eines Konferenz Geräts

  - Verwenden Sie das Cmdlet " **CsMeetingRoom** ", um die Eigenschaftswerte eines vorhandenen Konferenz Geräts zu ändern. Mit dem folgenden Befehl wird beispielsweise die Telefonnummer (LineUri) aktualisiert, die einem Konferenzgerät zugeordnet ist:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und dem Cmdlet " [Satz-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

