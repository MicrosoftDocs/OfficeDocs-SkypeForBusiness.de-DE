---
title: 'Lync Server 2013: Aktivieren der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2b31e399ba43f9e6b02ea66466da74e39d63a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a>Aktivieren der Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.

Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation zu den folgenden Cmdlets:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Gruppe-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>So aktivieren Sie die Anrufsteuerung mithilfe der Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkConfiguration" aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>So aktivieren Sie die Anrufsteuerung mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Global**.

4.  Klicken Sie in der Liste auf **Global**, und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen**.

5.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen.

    
    </div>

6.  Klicken Sie auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

