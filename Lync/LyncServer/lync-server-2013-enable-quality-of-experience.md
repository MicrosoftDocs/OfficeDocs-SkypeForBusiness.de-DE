---
title: 'Lync Server 2013: Aktivieren der Qualität der Benutzerfreundlichkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 558e7cfef48a472b4fd9ab7f538197313a8f112a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Aktivieren der erfahrungsqualität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben. Ausführliche Informationen finden Sie unter [Planen der Überwachung in lync Server 2013](lync-server-2013-planning-for-monitoring.md) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um QoE in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.

<div>


> [!NOTE]  
> Zur Aktivierung von QoE müssen Sie zunächst die Überwachung und eine Monitoring-Back-End-Datenbank konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>So aktivieren Sie QoE mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion** und anschließend auf **QoE aktivieren**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Aktivieren von QoE mithilfe von Windows PowerShell-Cmdlets

Sie können QoE mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " aktivieren. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>So aktivieren Sie QoE für einen einzelnen Standort

  - Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf „True“ ($True) fest.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>So deaktivieren Sie QoE für einen einzelnen Standort

  - Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf „False“ ($False) fest. Die Überwachung wird dadurch nicht deinstalliert. Das Erfassen und Speichern von QoE-Daten wird unterbrochen.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>So aktivieren Sie QoE mit einem einzelnen Befehl an mehreren Standorten

  - Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

Ausführliche Informationen finden Sie unter [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der Überwachung in Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

