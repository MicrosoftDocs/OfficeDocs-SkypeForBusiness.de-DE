---
title: 'Lync Server 2013: Aktivieren von Quality of Experience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 539408bfaa32565ef76312e1b0d96767edecc169
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Aktivieren der erfahrungsqualität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben. Ausführliche Informationen finden Sie unter [Planning for Monitoring in lync Server 2013](lync-server-2013-planning-for-monitoring.md) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um QoE für Ihre gesamte Organisation oder jeden Standort in Ihrer Organisation zu aktivieren.

<div>


> [!NOTE]  
> Zum Aktivieren von QoE müssen Sie zunächst die Überwachung und eine Überwachungs-Back-End-Datenbank konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>So aktivieren Sie QoE mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion**, und klicken Sie dann auf **QoE aktivieren**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Aktivieren von QoE mithilfe von Windows PowerShell-Cmdlets

Sie können QoE mithilfe von Windows PowerShell und dem CmdletSet **-CsQoEConfiguration** aktivieren. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>So aktivieren Sie QoE für einen einzelnen Standort

  - Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf true ($true) fest.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>So deaktivieren Sie QoE für einen einzelnen Standort

  - Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf false ($false) fest. Die Überwachung wird dadurch nicht deinstalliert. Es hält die Sammlung und Speicherung von QoE-Daten an.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>So aktivieren Sie QoE an mehreren Standorten mithilfe eines einzelnen Befehls

  - Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

Ausführliche Informationen finden Sie unter [Sets-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der Überwachung in lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

