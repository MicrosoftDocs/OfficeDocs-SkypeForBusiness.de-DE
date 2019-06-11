---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für den Medienportbereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Konfigurieren von Einstellungen für den Medienportbereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Einstellungen für den Medienportbereich können die Clientleistung erheblich beeinträchtigen und sollten konfiguriert werden. Sie können diese Einstellungen mithilfe der lync Server-Verwaltungsshell konfigurieren.

### <a name="media-port-range-settings"></a>Einstellungen für den Medien Port Bereich

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Einstellung</th>
<th>Beschreibung</th>
<th>Cmdlet "lync Server-Verwaltungsshell"</th>
<th>Cmdlet-Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Gibt an, ob der vom Server gesendete Portbereich vom Client für Medien und Signalisierungen verwendet werden soll. Wird in Verbindung mit den unter Werten MinMediaPort und MaxMediaPort verwendet.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Gibt die für Medien zu verwendende anfangs Portnummer an. Kombiniert mit MaxMediaPort, um den Portbereich anzugeben. Der empfohlene Mindestbereich ist 40-Anschlüsse.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (stellt die Anfangs Portnummer dar, die für Client Medien verwendet werden soll)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Gibt die höchste Portnummer an, die für Medien verwendet werden soll. Kombiniert mit MinMediaPort, um den Portbereich anzugeben. Der empfohlene Mindestbereich ist 40-Anschlüsse.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (zeigt die Gesamtanzahl der für Client Medien verfügbaren Ports an; Standard ist 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>So konfigurieren Sie die Einstellungen für den Medien Port Bereich

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsConferencingConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen für Konferenzen zurück.

3.  Führen Sie das folgende Cmdlet mit den Parametern und Werten aus, die Sie ändern möchten (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Sie können zusätzliche Gruppen von Konferenz Konfigurationseinstellungen für bestimmte Websites erstellen. Verwenden Sie das Cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> mit einer Websiteidentität. Wenn Sie neue Konferenz Konfigurationseinstellungen für Websites erstellen, haben die Websiteeinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

