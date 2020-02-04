---
title: 'Lync Server 2013: Importieren von Testfällen für das VoIP-Routing'
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
ms.openlocfilehash: 013860ea52773f4109c56bd71d37a9f4b8938225
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importieren von Testfällen für das VoIP-Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren solche Dinge wie die Nummer, die gewählt werden soll, und die Richtlinie für Wähleinstellungen und VoIP, die verwendet werden soll, und lync Server 2013 kann dann überprüfen, ob die angegebene Nummer aufgrund dieser Bedingungen Erfolg haben kann. sfully an das PSTN-Netzwerk weitergeleitet werden.

Testfälle, die mithilfe der lync Server-Systemsteuerung erstellt werden können, werden in der Regel nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde. Diese Testfälle können jedoch als XML-Dateien (mit der Erweiterung. vtest) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie dieselben Tests auf verschiedenen Computern ausführen, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>So importieren Sie einen Test Case für VoIP-Routing

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie im Menü **Aktionen** auf **Testfälle importieren**.

5.  Suchen Sie die Testfalldatei (vtest), die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.

6.  Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine vtest-Datei importieren, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um den Testfall zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

