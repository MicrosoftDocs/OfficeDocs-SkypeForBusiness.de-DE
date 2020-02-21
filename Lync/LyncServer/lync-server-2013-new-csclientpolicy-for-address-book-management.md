---
title: 'Lync Server 2013: New-CsClientPolicy für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30ee2dff06f2881906793043f1dc039f57919a67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>New-CsClientPolicy für die Adressbuchverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet New-CsClientPolicy lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten RBAC (Role-based Access Control)-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, (einschließlich aller von Ihnen erstellen benutzerdefinierten RBAC-Rollen):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Das Cmdlet New-CsClientPolicy definiert eine große Anzahl von Einstellungen für die Bereitstellung von Clients für Features, die in lync Server 2013 verfügbar sind. Für den Adressbuchdienst ist der Parameter AddressBookAvailability von Interesse. Dieser Parameter, der sich direkt auf die für Clients verfügbaren Optionen auswirkt, bietet drei mögliche Optionen:

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Dieser Parameter, sofern definiert, gibt an, wie durch Clients auf das Adressbuch zugegriffen wird. Wenn Sie diesen Parameter definieren, müssen Sie eine der Optionen festlegen. Wenn Sie diese Einstellung nicht ändern, bleibt der Standardwert "WebSearchAndFileDownload" in Kraft.

Beispiel:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>Siehe auch


[New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

