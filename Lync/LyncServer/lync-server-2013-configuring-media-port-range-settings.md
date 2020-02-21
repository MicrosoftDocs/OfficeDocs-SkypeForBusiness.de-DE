---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für den Medienportbereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f345b97851aac264bb3b7ef05978d80d851099ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Konfigurieren von Einstellungen für den Medienportbereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Die Einstellungen für Medienportbereiche können sich erheblich auf die Clientleistung auswirken und sollten konfiguriert werden. Sie können diese Einstellungen mit lync Server-Verwaltungsshell konfigurieren.

### <a name="media-port-range-settings"></a>Einstellungen für den Medienportbereich

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
<th>Lync Server-Verwaltungsshell-Cmdlet</th>
<th>Cmdlet-Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Gibt an, ob die vom Server gesendeten Portbereiche vom Client für Medien- und Signaldatenverkehr verwendet werden sollen. Wird gemeinsam mit den Unterwerten "MinMediaPort" und "MaxMediaPort" verwendet.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>Parameter clientmediaportrangeenabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Gibt die erste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit "MaxMediaPort" den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (repräsentiert die erste Portnummer, die für Clientmediendaten verwendet wird)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Gibt die höchste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit "MinMediaPort" den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (gibt die Gesamtanzahl von Ports an, die für Clientmediendaten verfügbar sind; der Standardwert lautet 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>So konfigurieren Sie die Einstellungen für den Medienportbereich

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsConferencingConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen für Konferenzen zurück.

3.  Führen Sie das folgende Cmdlet mit den Parametern und Werten aus, die Sie ändern möchten (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Sie können zusätzliche Sätze mit Konfigurationseinstellungen für Konferenzen für bestimmte Standorte erstellen. Verwenden Sie das Cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> mit einer Standortidentität. Beim Erstellen neuer Konfigurationseinstellungen für Konferenzen für einen Standort haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

