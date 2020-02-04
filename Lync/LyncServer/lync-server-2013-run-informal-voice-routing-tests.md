---
title: 'Lync Server 2013: Ausführen informeller VoIP-Routing Tests'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Ausführen informeller VoIP-Routing Tests in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Sie können das Dialogfeld **Informationen zum Erstellen von sprach Routing Testfällen** verwenden, um informelle Tests auszuführen, bevor Sie einen tatsächlichen Testfall erstellen. Wenn Sie mit dem Ergebnis eines Tests zufrieden sind, haben Sie die Möglichkeit, es als formalen Testfall zu speichern.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>So führen Sie einen informellen VoIP-Routing Test aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf VoIP- **Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **VoIP-Weiterleitungstest Fall Informationen erstellen**.

5.  Geben Sie im Feld **gewählte Nummer** die Telefonnummer ein, die Sie für diesen Test verwenden möchten. Diese Nummer wird normalisiert und im Feld " **normalisierte Zahl** " des **Ergebnis** Bereichs angezeigt.

6.  Wählen Sie in der Liste **Wählplan** die Wähleinstellungen aus, die Sie zum Testen der gewählten Nummer verwenden möchten. Standardmäßig ist der globale Wählplan vorgesehen.
    
    Wenn Sie den Test ausführen, wird die erste Normalisierungsregel in diesem Wählplan, die der gewählten Nummer entspricht, im Feld **Normalisierungsregel** des **Ergebnis** Bereichs angezeigt.

7.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die Sie zum Testen der gewählten Nummer verwenden möchten. Standard ist die globale VoIP-Richtlinie.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungs Eintrag in dieser VoIP-Richtlinie im ersten Feld für die **PSTN-Nutzung** des **Ergebnis** Bereichs angezeigt. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdaten Satz zugeordnet ist, im Feld **erste Route** angezeigt.

8.  Optional Aktivieren Sie das Kontrollkästchen **vom Benutzer auffüllen** , wenn Sie die gewählte Nummer anhand der VoIP-Richtlinie testen möchten, die einem bestimmten Benutzer zugewiesen ist.
    
    1.  Klicken Sie auf **Durchsuchen** , um das Dialogfeld **Enterprise-VoIP-Benutzer auswählen** anzuzeigen.
    
    2.  Klicken Sie auf **Suchen** , um die Liste der Benutzer anzuzeigen, die für Enterprise-VoIP aktiviert sind.
    
    3.  Doppelklicken Sie auf den Benutzernamen, dessen zugewiesene VoIP-Richtlinie Sie für diesen Test verwenden möchten. Das Feld " **Richtlinie** " ist jetzt mit der VoIP-Richtlinie gefüllt, die dem ausgewählten Benutzer zugewiesen ist.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende Usage-Eintrag (Public Switched Telephone Network, PSTN) in dieser VoIP-Richtlinie im ersten Feld für die **PSTN-Nutzung** des **Ergebnis** Bereichs angezeigt. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdaten Satz zugeordnet ist, im Feld **erste Route** angezeigt.

9.  Klicken Sie auf **Ausführen** , um den Testfall auszuführen. Die Ergebnisse werden im rechten Fenster des Dialogfelds angezeigt.

10. Optional Klicken Sie auf **Speichern** unter, wenn Sie diese Testkonfiguration als formalen Testfall speichern möchten.
    
    1.  Geben Sie im Feld **Name** des Dialogfelds **VoIP-Routing Test Case-Informationen speichern** einen eindeutigen Namen für den Testfall ein.
        
        Der Name muss bei allen Sprach Routing-Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.
    
    2.  Beachten Sie, dass die verbleibenden Felder im Dialogfeld **sprach Routing-Testfall-Informationen speichern** schreibgeschützt sind und aus der informellen Testkonfiguration *und* den Ergebnissen ausgefüllt werden. Überprüfen Sie, ob es sich um die Konfiguration handelt, die Sie für den Testfall speichern möchten.
        
        <div>
        

        > [!NOTE]  
        > Die Werte aus den Testergebnissen werden verwendet, um die Felder im Dialogfeld <STRONG>VoIP-Routing Test Case-Informationen speichern</STRONG> wie folgt zu füllen: 
        > <UL>
        > <LI>
        > <P>Die <STRONG>erwartete Übersetzung</STRONG> wird mit dem Wert im Feld <STRONG>normalisierte Zahl</STRONG> vorab ausgefüllt.</P>
        > <LI>
        > <P>Die <STRONG>erwartete Route</STRONG> wird mit dem Wert im <STRONG>ersten Routen</STRONG> Feld ausgefüllt.</P>
        > <LI>
        > <P><STRONG>Voraussichtlicher PSTN-Verwendungsdaten Satz</STRONG> wird mit dem Wert im <STRONG>ersten PSTN-Nutzungs</STRONG> Feld vorab ausgefüllt.</P></LI></UL>Wenn Übereinstimmungen für einen dieser Werte während des Testlaufs nicht gefunden wurden, ist das entsprechende Feld im Dialogfeld <STRONG>Informationen zum Speichern von sprach Routing Testfällen</STRONG> leer.

        
        </div>
    
    3.  Klicken Sie auf **OK** , um den Testfall zu speichern, oder klicken Sie auf **Abbrechen** , um zurückzukehren, um zum Dialogfeld **sprach Routing Test Case-Informationen anzeigen** zu wechseln, um den Test weiter zu entwickeln, bevor Sie ihn speichern.

11. Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen Test Case für VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um den Testfall zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Ausführen von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
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

