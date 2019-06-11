---
title: 'Lync Server 2013: Konfigurieren der Seite für den Besprechungsbeitritt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-14_

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", ob ein lync 2013-Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird der Client geöffnet und der Besprechung beitreten. Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von lync Web App geöffnet.

Sie können das Verhalten der Besprechungsteilnahme Seite ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten. Diese Konfigurationsoptionen wurden aus der Systemsteuerung von lync Server 2013 entfernt, aber Sie werden mithilfe des Cmdlets "festlegen-CsWebServiceConfiguration" konfiguriert.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Seitensatz "Besprechungsteilnahme" – CsWebServiceConfiguration-Parameter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Satz-CsWebServiceConfiguration-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Wenn die Einstellung auf "true" festgelegt ist, wird Benutzern, die mit einer anderen Clientanwendung als lync an einer Besprechung teilnehmen, die Möglichkeit gegeben, mit Office Communicator 2007 R2 an der Besprechung teilzunehmen. Der Standardwert lautet "False".</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Wenn Sie auf true festgelegt ist, werden alternative Optionen für die Teilnahme an einer Onlinekonferenz (wie Office Communicator 2007 R2) automatisch erweitert und Benutzern angezeigt. Wenn auf "false" (der Standardwert) festgelegt ist, sind diese Optionen verfügbar, der Benutzer muss jedoch die Liste der Optionen für sich selbst anzeigen.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>So konfigurieren Sie die Seite "Besprechungsteilnahme" mithilfe der lync Server 2013-Verwaltungsshell

1.  Starten Sie die lync Server 2013-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die Konfigurationseinstellungen des Webdiensts anzuzeigen:
    
        Get-CsWebServiceConfiguration

3.  Führen Sie den folgenden Befehl aus, wobei die Parameter je nach ihrer Einstellung auf "true" oder "false" festgelegt sind (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie unter " [CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) " in der Dokumentation zur lync Server 2013-Verwaltungsshell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Satz-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

