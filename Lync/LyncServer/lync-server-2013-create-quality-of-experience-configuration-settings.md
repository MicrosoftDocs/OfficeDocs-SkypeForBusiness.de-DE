---
title: 'Lync Server 2013: Erstellen von Konfigurationseinstellungen für die Qualität der Benutzeroberfläche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f651da026dcf73253eaccada14332a7f2f5c1f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Erstellen von Konfigurationseinstellungen für die Qualität von Erfahrungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzelne globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben sie Vorrang vor den globalen Einstellungen. Beispiel: Wenn Sie für den Standort Redmond standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.

QoE-Konfigurationseinstellungen können entweder mit der lync Server-Systemsteuerung oder mit dem Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) erstellt werden. Wenn Sie die lync Server-Systemsteuerung zum Erstellen neuer Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:


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
<td><p>Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Überwachung der QoE-Daten aktivieren</p></td>
<td><p>EnableQoE</p></td>
<td><p>Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden.</p></td>
</tr>
<tr class="odd">
<td><p>Löschvorgang für QoE-Daten aktivieren</p></td>
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft <strong>QoE-Daten für maximal (Tage) aufbewahren</strong> festgelegten Zeitraums gelöscht werden sollen.</p></td>
</tr>
<tr class="even">
<td><p>QoE-Daten für maximal (Tage) aufbewahren</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank gelöscht werden. Bei deaktiviertem Löschvorgang wird dieser Wert ignoriert.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Das Cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen, die in der lync Server-Systemsteuerung nicht zur Verfügung stehen. Weitere Informationen finden Sie im Hilfethema zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen Sie QoE-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.

5.  Klicken Sie unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll und klicken Sie dann auf **OK**.

6.  Tun Sie unter **Neue QoE-Einstellung** Folgendes:
    
      - Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.
    
      - Wählen Sie **Löschvorgang für QoE-Daten aktivieren** aus, um den Löschvorgang einzuschalten.
    
      - Wählen Sie unter **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet New-CsQoEConfiguration erstellen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen

  - Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort „Redmond“ gelten sollen:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung

  - Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:

  - Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

