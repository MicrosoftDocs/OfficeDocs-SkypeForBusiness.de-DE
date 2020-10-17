---
title: 'Lync Server 2013: Importieren von Testfällen für das VoIP-Routing'
description: 'Lync Server 2013: Importieren von Testfällen für das VoIP-Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ce1b144de03406b7b78d6957371ed2bc303e95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547831"
---
# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importieren von Testfällen für das VoIP-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren beispielsweise die Nummer, die gewählt werden soll, und die Wähleinstellungen und die VoIP-Richtlinie, die verwendet werden sollen, und lync Server 2013 können dann anhand dieser Bedingungen sicherstellen, dass die angegebene Nummer erfolgreich an das PSTN-Netzwerk weitergeleitet werden kann.

Testfälle, die mithilfe von lync Server-Systemsteuerung erstellt werden können, werden normalerweise nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde. Sie können jedoch in Form von XML-Dateien (mit der Erweiterung VTEST) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie den gleichen Test auf verschiedenen Computern, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden, ausführen.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>So importieren Sie einen Testfall für das VoIP-Routing

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie im Menü **Aktionen** auf **Testfälle importieren**.

5.  Suchen Sie nach der Testfalldatei (.VTEST), die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.

6.  Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine VTEST-Datei importieren, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um den Testfall zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Exportieren von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

