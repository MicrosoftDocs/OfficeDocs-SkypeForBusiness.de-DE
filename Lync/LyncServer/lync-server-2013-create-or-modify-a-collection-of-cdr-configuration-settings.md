---
title: 'Lync Server 2013: Erstellen oder Ändern einer Sammlung von KDS-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582df13f3bcd7c1d25e8bf15ce1534992ba6aeeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514792"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) können Sie die Verwendung von Peer-zu-Peer-Sofortnachrichtensitzungen, VoIP-Telefon anrufen (Voice over Internet Protocol) und Konferenzanrufe nachverfolgen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Bei der Installation von Microsoft lync Server 2013 wird eine einzelne, globale Sammlung von KDS-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise standortspezifische Einstellungen für den Standort "Redmond" erstellen, werden diese Einstellungen (anstelle der globalen Einstellungen) zum Verwalten von KDS in Redmond verwendet.

Sie können KDS-Konfigurationseinstellungen entweder mit lync Server-Systemsteuerung oder mit dem [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet erstellen. Sie können lync Server-Systemsteuerung oder das Cmdlet " [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) " verwenden, um vorhandene Einstellungen zu ändern. Wenn Sie lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI-Einstellung</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identität</p></td>
<td><p>Eindeutiger Bezeichner für die zu erstellenden KDS-Konfigurationseinstellungen. Diese Einstellungen können nur auf Standortebene erstellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Aktivieren der Überwachung von CDRs</p></td>
<td><p>"Enablecdr"</p></td>
<td><p>Gibt an, ob KDS aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren der Bereinigung von CDRs</p></td>
<td><p>"Enablepurging"</p></td>
<td><p>Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.</p></td>
</tr>
<tr class="even">
<td><p>CDRs für maximale Dauer (Tage) beibehalten</p></td>
<td><p>"Keepcalldetailfordays"</p></td>
<td><p>Gibt an, wie viele Tage KDS-Einträge in der KDS-Datenbank aufbewahrt werden. Alle Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. (Beachten Sie, dass das Löschen nur erfolgen kann, wenn die Bereinigung aktiviert wurde.)</p></td>
</tr>
<tr class="odd">
<td><p>Fehlerberichtsdaten für maximale Dauer (Tage) aufbewahren</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Gibt die Anzahl der Tage an, an denen KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen hochgeladen wurden.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die Cmdlets New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in lync Server-Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie in den Hilfethemen zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und in den <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Sets-CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen Sie KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Klicken Sie auf der Registerkarte **Anruf Detail Aufzeichnung** auf **neu**.

3.  Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, an dem die neuen Konfigurationseinstellungen erstellt werden sollen. Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Websites bereits eine Sammlung von KDS-Konfigurationseinstellungen zugewiesen wurde. Jede Website ist auf eine einzelne solche Sammlung limitiert. In diesem Fall können Sie die Einstellungen entweder löschen und dann neu erstellen oder die vorhandenen Einstellungen einfach ändern.

4.  Nehmen Sie im Dialogfeld neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Doppelklicken Sie auf die Auflistung der zu ändernden Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie nur eine einzelne Auflistung gleichzeitig ändern können. Um dieselben Änderungen an mehreren Auflistungen vorzunehmen, verwenden Sie stattdessen die lync Server-Verwaltungsshell.

3.  Nehmen Sie im Dialogfeld Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können KDS-Konfigurationseinstellungen auch mit Windows PowerShell und dem Cmdlet **New-CsCdrConfiguration** erstellen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen

  - Mit diesem Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen erstellt, die auf den Standort "Redmond" angewendet werden:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Sammlung von KDS-Konfigurationseinstellungen, die die Aufzeichnung von Anrufdetails deaktivieren

  - Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für das Anruf Detail zu erstellen, die standardmäßig die Aufzeichnung von Anruf Detail Aufzeichnungen zulassen, verwenden Sie einen Befehl wie den folgenden:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an

  - Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter einschließen. Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Anruf Detail Datensätze für 30 Tage und Fehlerberichte für 90 Tage aufbewahrt werden:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Weitere Informationen finden Sie im Hilfethema zum [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

