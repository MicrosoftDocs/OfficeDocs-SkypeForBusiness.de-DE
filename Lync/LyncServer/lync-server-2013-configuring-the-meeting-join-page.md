---
title: 'Lync Server 2013: Konfigurieren der Seite für den besprechungsbeitritt'
description: 'Lync Server 2013: Konfigurieren der Seite für den besprechungsbeitritt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e7c9dde0fdb6829da7bd11e16261a4bd76b7554
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564301"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-14_

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den besprechungsbeitritt, ob ein lync 2013 Client bereits auf dem Computer des Benutzers installiert ist. Wenn bereits ein Client installiert ist, wird dieser geöffnet und tritt der Besprechung bei. Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von lync Web App geöffnet.

Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten. Diese Konfigurationsoptionen wurden aus der lync Server 2013-Systemsteuerung entfernt, Sie werden jedoch mithilfe des Set-CsWebServiceConfiguration-Cmdlets konfiguriert.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Set-CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>"Showjoinusinglegacyclientlink"</p></td>
<td><p>Bei Festlegung auf "true" wird Benutzern, die einer Besprechung mithilfe einer anderen Clientanwendung als lync beitreten, die Möglichkeit gegeben, an der Besprechung mit Office Communicator 2007 R2 teilzunehmen. Der Standardwert lautet "False".</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Bei Festlegung auf "True" werden automatisch alternative Optionen für die Teilnahme an einer Onlinekonferenz (z. B. Office Communicator 2007 R2) erweitert und für Benutzer angezeigt. Bei Festlegung auf "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen selbst anzeigen.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>So konfigurieren Sie die Seite für den besprechungsbeitritt mithilfe lync Server 2013 Verwaltungsshell

1.  Starten Sie die lync Server 2013 Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die Konfigurationseinstellungen des Webdiensts anzuzeigen:
    
        Get-CsWebServiceConfiguration

3.  Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie unter " [CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) " in der Dokumentation zu lync Server 2013 Management Shell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Gruppe-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

