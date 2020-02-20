---
title: 'Lync Server 2013: Ausführen von Tests für informelles VoIP-Routing'
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
ms.openlocfilehash: 851d292e4c1f891eefa9abb4126ac74e7f3469cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Ausführen von informellen VoIP-Routing Tests in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-07_

Sie können mit dem Dialogfeld **Testfallinformationen für das VoIP-Routing erstellen** interne Tests ausführen, bevor Sie einen tatsächlichen Testfall erstellen. Wenn Sie mit dem Ergebnis eines Tests zufrieden sind, können Sie den Test als formalen Testfall speichern.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>So führen Sie einen informellen Test für das VoIP-Routing aus

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Testfallinformationen für das VoIP-Routing erstellen**.

5.  Geben Sie im Feld **Gewählte Nummer** die Telefonnummer ein, die Sie für diesen Test verwenden möchten. Diese Nummer wird normalisiert und im Feld **Normalisierte Nummer** des Ergebnisbereichs**** angezeigt.

6.  Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen, der zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.
    
    Wenn Sie den Test ausführen, wird die erste Normalisierungsregel in diesen Wähleinstellungen, die mit der gewählten Nummer übereinstimmt, im Feld **Normalisierungsregel** des Ergebnisbereichs**** angezeigt.

7.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt****. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.

8.  (Optional) Aktivieren Sie das Kontrollkästchen **Aus Benutzer auffüllen**, wenn Sie die gewählte Nummer für eine VoIP-Richtlinie testen möchten, die einem bestimmten Benutzer zugewiesen ist.
    
    1.  Klicken Sie auf **Durchsuchen**, um das Dialogfeld **Enterprise-VoIP-Benutzer auswählen** anzuzeigen.
    
    2.  Klicken Sie auf **Suchen**, um die Liste der Benutzer anzuzeigen, die für Enterprise-VoIP aktiviert sind.
    
    3.  Doppelklicken Sie auf den Benutzernamen, dessen zugewiesene VoIP-Richtlinie Sie für diesen Test verwenden möchten. Das Feld **Richtlinie** wird jetzt mit der VoIP-Richtlinie gefüllt, die dem ausgewählten Benutzer zugewiesen ist.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt****. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.

9.  Klicken Sie auf **Ausführen**, um den Testfall auszuführen. Die Ergebnisse werden im rechten Bereich des Dialogfelds angezeigt.

10. (Optional) Klicken Sie auf **Speichern unter**, wenn Sie diese Testkonfiguration als formalen Testfall speichern möchten.
    
    1.  Geben Sie im Feld **Name** des Dialogfelds **Testfallinformationen für das VoIP-Routing speichern** einen eindeutigen Namen für den Testfall ein.
        
        Der Name muss bei allen VoIP-Routing Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.
    
    2.  Beachten Sie, dass die verbleibenden Felder im Dialogfeld **Testfallinformationen für das VoIP-Routing speichern** schreibgeschützt sind und mit den Daten *und* Ergebnissen aus der informellen Testkonfiguration vorausgefüllt werden. Stellen Sie sicher, dass dies die Konfiguration ist, die Sie für den Testfall speichern möchten.
        
        <div>
        

        > [!NOTE]  
        > Die Werte aus den Testergebnissen werden folgendermaßen zum Vorausfüllen der Felder im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> verwendet: 
        > <UL>
        > <LI>
        > <P><STRONG>Erwartete Übersetzung</STRONG> wird mit dem Wert im Feld <STRONG>Normalisierte Nummer</STRONG> vorausgefüllt.</P>
        > <LI>
        > <P><STRONG>Erwartete Route</STRONG> wird mit dem Wert im Feld <STRONG>Erste Route</STRONG> vorausgefüllt.</P>
        > <LI>
        > <P><STRONG>Erwarteter PSTN-Verwendungsdatensatz</STRONG> wird mit dem Wert im Feld <STRONG>Erste PSTN-Verwendung</STRONG> vorausgefüllt.</P></LI></UL>Wenn für einen dieser Werte beim Test keine Übereinstimmungen gefunden werden, bleibt das entsprechende Feld im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> leer.</div>
    
    3.  Klicken Sie auf **OK**, um den Testfall zu speichern, oder klicken Sie auf **Abbrechen**, um zum Dialogfeld **Testfallinformationen für das VoIP-Routing anzeigen** zurückzukehren und weitere Änderungen vorzunehmen, bevor Sie den Test speichern.

11. Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie einen Testfall für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um den Testfall zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines Testfalls für das VoIP-Routing in lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Ausführen von Testfällen für das VoIP-Routing in lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
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

