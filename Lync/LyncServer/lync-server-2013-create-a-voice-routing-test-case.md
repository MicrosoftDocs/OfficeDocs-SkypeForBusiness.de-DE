---
title: 'Lync Server 2013: Erstellen eines Testfalls für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da110d7e3bfb7188384163cb572591d0bf7f8ff3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501772"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Erstellen eines Testfalls für das VoIP-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>So erstellen Sie einen Testfall

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Neu**, um einen neuen Testfall zu erstellen.

5.  Geben Sie unter **Name** einen eindeutigen Namen für den Testfall ein.
    
    Der Name muss bei allen VoIP-Routing Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich ( \\ ), Punkt (.) oder Unterstrich () auch beliebige alphanumerische Zeichen enthalten \_ .

6.  Geben Sie unter **Zu testende gewählte Rufnummer** die gewählte Rufnummer ein, die Sie zum Testen der für diesen Testfall angegebenen Routingkonfiguration verwenden möchten. Basierend auf dem Satz mit Wähleinstellungen, der Route und der VoIP-Richtlinie wird diese Nummer normalisiert und als Ausgabe angezeigt.

7.  Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen aus, der bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.

8.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.

9.  Geben Sie unter **Erwartete Übersetzung** die Telefonnummer in dem Format ein, in dem sie nach der Übersetzung vorliegen soll. Hierbei handelt es sich um den Wert der getesteten Telefonnummer, nachdem diese durch die erste den Kriterien entsprechende Normalisierungsregel in den ausgewählten Wähleinstellungen übersetzt wurde. Wenn die getestete Nummer bei Ausführung des Testfalls nicht den Wert in **Erwartete Übersetzung** ergibt, ist der Test nicht erfolgreich.

10. (Optional) In der Liste **Erwartete PSTN-Verwendung** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie den PSTN-Verwendungsdatensatz (Public Switched Telephone Network, Telefonfestnetz) auswählen, der beim Ausführen des Testfalls verwendet werden soll. Wird ein anderer PSTN-Verwendungsdatensatz verwendet, ist der Test nicht erfolgreich.

11. (Optional) In der Liste **Erwartete Route** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie die VoIP-Route auswählen, die beim Ausführen des Testfalls verwendet werden soll. Wird eine andere VoIP-Route verwendet, ist der Test nicht erfolgreich.

12. (Optional) Klicken Sie auf **Ausführen**, um den Testfall auszuführen. Die Ergebnisse werden im rechten Seitenbereich angezeigt.

13. Klicken Sie auf **OK**.

14. Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie einen Testplan für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>
    
    Wenn der im Test verwendete Wählplan die Telefonnummern normalisiert, die mit einem Pluszeichen beginnen (beispielsweise + 12065551219), kann dieser Plan dazu führen, dass der VoIP-Routing Test fehlschlägt. (Die Wähleinstellungen und die VoIP-Route funktionieren; tatsächlich werden Test-CsDialPlan erfolgreich sein. Der VoIP-Routing Test schlägt jedoch möglicherweise fehl.) Dies sollten Sie beim Testen von VoIP-Routen beachten.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Exportieren von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importieren von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

