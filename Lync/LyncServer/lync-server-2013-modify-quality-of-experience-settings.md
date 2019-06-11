---
title: 'Lync Server 2013: Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce6041e6512714f10785cf2976727788e105f70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der Standardeinstellung werden QoE-Daten (Quality of Experience, Erlebnisqualität) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **QoE-Daten** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie QoE deaktivieren, werden auch Daten gelöscht, die bei aktivierter QoE-Datenerfassung aufgezeichnet wurden.

<div>


> [!NOTE]  
> Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Überwachungsberichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.



</div>

Das nachfolgende Verfahren beschreibt, wie Sie die Löscheinstellungen für QoE-Daten konfigurieren.

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>So legen Sie die Beibehaltung von QoE-Daten mithilfe der lync Server-Systemsteuerung fest

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Wählen Sie die Option **Löschen für QoE aktivieren** aus, um die Löschung zu aktivieren.

6.  Wählen Sie unter **Maximale Speicherdauer für die QuE-Aufzeichnung (Tage)** die maximale Anzahl von Tagen aus, für die QoE-Daten gespeichert werden sollen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Angeben der QoE-Aufbewahrung mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " erstellen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>So geben Sie die QoE-Aufbewahrung für einen speziellen Standort an

  - Dieser Befehl ermöglicht das Löschen von QoE-Daten für den Standort Redmond. Zudem wird damit für die QoE-Daten eine Aufbewahrungsdauer von 20 Tagen konfiguriert.
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>So geben Sie die QoE-Aufbewahrung für mehrere Standorte an

  - Mit diesem Befehl wird die Beibehaltung von QoE-Daten für alle in einer Organisation verwendeten QoE-Konfigurationseinstellungen konfiguriert.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

