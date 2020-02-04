---
title: 'Lync Server 2013: Erstellen oder Ändern einer Sammlung von CDR-Konfigurationseinstellungen'
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
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von CDR-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzige globale Sammlung von CDR-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen. Wenn diese Einstellungen auf Standortebene verwendet werden, haben sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Einstellungen auf Standortebene für den Standort „Redmond“ erstellen, werden diese Einstellung (anstelle der globalen Einstellungen) für die KDS-Verwaltung in Redmond verwendet.

Sie können CdR-Konfigurationseinstellungen entweder mithilfe der lync Server-Systemsteuerung oder mit dem Cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) erstellen. Sie können die lync Server-Systemsteuerung oder das Cmdlet " [Satz-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) " verwenden, um vorhandene Einstellungen zu ändern. Wenn Sie die lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzeroberflächeneinstellung</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identität</p></td>
<td><p>Eindeutiger Bezeichner für die KDS-Konfigurationseinstellungen, die erstellt werden. Diese Einstellungen können nur auf der Standortebene erstellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Überwachung von KDS-Aufzeichnungen aktivieren</p></td>
<td><p>EnableCDR</p></td>
<td><p>Gibt an, ob KDS aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Bereinigung von KDS-Aufzeichnungen aktivieren</p></td>
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.</p></td>
</tr>
<tr class="even">
<td><p>Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Datensätze in der KDS-Datenbank gespeichert werden. Datensätze, die älter sind als angegeben, werden automatisch gelöscht. (Beachten Sie, dass der Löschvorgang nur stattfindet, wenn die Bereinigung aktiviert wurde.)</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter sind als angegeben, werden automatisch gelöscht. Fehlerberichte zu Kommunikationsdatensätzen sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die Cmdlets New-CsCdrConfiguration und CsCdrConfiguration umfassen zusätzliche Optionen, die in der lync Server-Systemsteuerung nicht zur Verfügung stehen. Weitere Informationen finden Sie in den Hilfethemen zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und den <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Satz-CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen Sie CDR-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Klicken Sie in der lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Klicken Sie auf der Registerkarte **Anruf Detail Aufzeichnung** auf **neu**.

3.  Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, in dem die neuen Konfigurationseinstellungen erstellt werden sollen. Falls das Dialogfeld leer ist, bedeutet dies, dass allen Ihren Standorten bereits eine Auflistung von KDS-Konfigurationseinstellungen zugewiesen wurde. Für jeden Standort ist nur eine einzige derartige Auflistung zulässig. In diesem Fall können Sie entweder die Einstellungen löschen und anschließend neu erstellen oder aber einfach die vorhandenen Einstellungen ändern.

4.  Wählen Sie im Dialogfeld **Neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS)** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>So ändern Sie vorhandene CdR-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Klicken Sie in der lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Doppelklicken Sie auf die zu ändernde Auflistung von Einstellungen oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten** und klicken Sie anschließend auf **Details einblenden**. Beachten Sie, dass Sie jeweils immer nur eine Auflistung ändern können. Wenn Sie die gleichen Änderungen an mehreren Auflistungen vornehmen möchten, verwenden Sie stattdessen die lync Server-Verwaltungsshell.

3.  Wählen Sie im Dialogfeld **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von CDR-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können CdR-Konfigurationseinstellungen erstellen, die auch mithilfe von Windows PowerShell und dem Cmdlet **New-CsCdrConfiguration** erstellt werden können. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen

  - Mit dem folgenden Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen für den Standort „Redmond“ erstellt:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Auflistung von KDS-Konfigurationseinstellungen, mit denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wird

  - Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von KDS-Konfigurationseinstellungen erstellen möchten, die standardmäßig das Deaktivieren der Aufzeichnung von Kommunikationsdatensätzen erlauben, verwenden Sie den folgenden Befehl:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an

  - Durch die Angabe mehrerer Parameter können Sie mehrere Eigenschaftswerte ändern. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Kommunikationsdatensätze 30 Tage und Fehlerberichte 90 Tage lang aufbewahrt werden:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

