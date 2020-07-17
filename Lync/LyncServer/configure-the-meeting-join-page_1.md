---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63354b9e0b0cf44ed44f53c91061578e01fecb5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-14_

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den besprechungsbeitritt, ob ein lync 2013 Client bereits auf dem Computer des Benutzers installiert ist. Ist bereits ein Client installiert, wird dieser Client geöffnet und für den Besprechungsbeitritt verwendet. Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von Microsoft lync Web App geöffnet.

Sie können das Verhalten der Seite für den besprechungsbeitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten. Diese Konfigurationsoptionen wurden aus der lync Server 2013-Systemsteuerung entfernt, Sie werden jedoch mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration-Parameter</th>
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

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsWebServiceConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.

3.  Führen Sie den folgenden Befehl aus, wobei die Parameter abhängig von Ihren Einstellungen auf true oder false festgelegt sind (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur lync Server 2013 Verwaltungsshell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

