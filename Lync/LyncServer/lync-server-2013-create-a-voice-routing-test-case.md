---
title: 'Lync Server 2013: Erstellen eines Testfalls für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>So erstellen Sie einen Test Case

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **neu** , um einen neuen Testfall zu erstellen.

5.  Geben Sie im Feld **Name**einen eindeutigen Namen für den Testfall ein.
    
    Der Name muss bei allen Sprach Routing-Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.

6.  Geben Sie in **zu testende Nummer**die gewählte Nummer ein, die Sie zum Testen der Routingkonfiguration verwenden möchten, die Sie für diesen Testfall angeben. Basierend auf den Wähleinstellungen, der Route und der VoIP-Richtlinie wird diese Nummer normalisiert und als Ausgabe angezeigt.

7.  Wählen Sie in der Liste **Wählplan** die Wähleinstellungen aus, die Sie beim Ausführen des Tests verwenden möchten. Standardmäßig ist der globale Wählplan vorgesehen.

8.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die Sie beim Ausführen des Tests verwenden möchten. Standard ist die globale VoIP-Richtlinie.

9.  Geben Sie in **erwartete Übersetzung**die Telefonnummer in das Format ein, das Sie nach der Übersetzung erwarten. Hierbei handelt es sich um den Wert der Telefonnummer, die Sie testen, nachdem Sie von der ersten Normalisierungsregel, die im ausgewählten Wählplan übereinstimmt, übersetzt wurde. Wenn Sie den Testfall ausführen, schlägt der Test fehl, wenn die von Ihnen getestete Zahl nicht zu dem Wert in der **erwarteten Übersetzung**führt.

10. Optional In der Liste **Erwarteter PSTN-Verbrauch** können Sie den PSTN-Verwendungsdaten Satz (Public Switched Telephone Network) auswählen, der auf der Grundlage der angegebenen Wähleinstellungen und VoIP-Richtlinie verwendet werden soll, wenn Sie den Testfall ausführen. Wenn ein anderer PSTN-Verwendungsdaten Satz verwendet wird, schlägt der Test fehl.

11. Optional In der Liste **erwartete Route** können Sie die VoIP-Route auswählen, die Sie bei der Ausführung des Testfalls erwarten, basierend auf den angegebenen Wähleinstellungen und VoIP-Richtlinien. Wenn eine andere VoIP-Route verwendet wird, schlägt der Test fehl.

12. Optional Klicken Sie auf **Ausführen** , um den Testfall auszuführen. Die Ergebnisse werden im rechten Panel der Seite angezeigt.

13. Klicken Sie auf **OK**.

14. Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen Test Case für VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>alle</STRONG> übernehmen ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>
    
    Wenn der Wählplan, der im Test verwendet wird, Telefonnummern normalisiert, die mit einem Pluszeichen beginnen (beispielsweise + 12065551219), kann dieser Plan dazu führen, dass der VoIP-Routing Test fehlschlägt. (Die Wähleinstellungen und die VoIP-Route funktionieren; in der Tat ist Test-CsDialPlan erfolgreich. Der sprach Routing Test schlägt jedoch möglicherweise fehl.) Dies ist etwas, das Sie beim Testen von VoIP-Routen beachten sollten.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

