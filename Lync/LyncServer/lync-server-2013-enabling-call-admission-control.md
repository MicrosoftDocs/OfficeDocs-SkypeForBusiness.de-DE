---
title: 'Lync Server 2013: Aktivieren der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1482ce09ff4501deb4c3acbb5df77d014b314ffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Aktivieren der Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Anrufsteuerungsnetzwerks müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen. Dazu können Sie lync Server-Systemsteuerung verwenden.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>So aktivieren Sie die Anrufsteuerung in lync Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**.
    
    <div>
    

    > [!NOTE]  
    > Für jede Microsoft lync Server 2013-Bereitstellung kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist. Die globale Konfiguration kann nicht umbenannt werden.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**, und klicken Sie auf **Commit**.

Beim Klicken auf **Commit** wird die Konfiguration getestet. Das Dialogfeld **Globale Einstellungen bearbeiten** wird geschlossen, und die Seite **Global** wird erneut angezeigt. Wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen ermittelt werden, die eine ordnungsgemäße Funktionsweise verhindern, wird eine Warnung angezeigt (wenn die einzelnen Regionen beispielsweise nicht über eine regionenübergreifende Route miteinander verbunden sind).

Nach dem Ändern Ihrer Netzwerkkonfiguration können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit** klicken. Es ist nicht erforderlich, die Anrufsteuerung zunächst zu deaktivieren: Lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Dieser Vorgang kann zu einem beliebigen Zeitpunkt ausgeführt werden, ohne Konfigurationsänderungen vorzunehmen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über die Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Planung der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Gruppe-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

