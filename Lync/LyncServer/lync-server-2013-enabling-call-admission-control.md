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
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Aktivieren der Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nachdem Sie das CAC-Netzwerk konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen. Hierzu können Sie die lync Server-Systemsteuerung verwenden.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>So aktivieren Sie CAC über die lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.
    
    <div>
    

    > [!NOTE]  
    > Für jede Microsoft lync Server 2013-Bereitstellung kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist. Sie können die globale Konfiguration nicht umbenennen.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **Anruf Zulassungs Steuerung aktivieren** , und klicken Sie dann auf **Commit**.

Wenn Sie auf **Commit**klicken, führen Sie einen Test der Konfiguration aus. Das Dialogfeld **globale Einstellungen bearbeiten** wird geschlossen, und Sie kehren zur **globalen** Seite zurück. Sie erhalten eine Warnung, wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen festgestellt werden, die verhindern, dass Sie ordnungsgemäß funktionieren (Wenn beispielsweise alle Regionen über eine interregions Route nicht mit allen anderen Regionen verbunden sind).

Wenn Sie Änderungen an Ihrer Netzwerkkonfiguration vornehmen, können Sie die Überprüfungs Prüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit**klicken. Sie müssen CAC nicht zuerst deaktivieren: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Sie können dies jederzeit tun, ohne Konfigurationsänderungen vorzunehmen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über die Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Satz-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

