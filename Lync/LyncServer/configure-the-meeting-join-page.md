---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01c2be988c94bd0bc90ed6b48702d426b42e505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-14_

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", ob ein lync 2013-Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client geöffnet und der Besprechung beitreten. Wenn ein Client nicht installiert ist, wird standardmäßig die 2013-Version von lync Web App geöffnet.

Sie können das Verhalten der Besprechungsteilnahme Seite ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit Office Communicator 2007 R2 oder lync 2010 Attendant gestatten möchten. Diese Konfigurationsoptionen wurden aus der Systemsteuerung von lync Server 2013 entfernt, aber Sie werden mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>CsWebServiceConfiguration-Parameter für Besprechungsteilnehmer Seite

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

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsWebServiceConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen des Webdiensts zurück.

3.  Führen Sie den folgenden Befehl aus, wobei die Parameter je nach ihrer Einstellung auf "true" oder "false" festgelegt sind (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur lync Server 2013-Verwaltungsshell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

