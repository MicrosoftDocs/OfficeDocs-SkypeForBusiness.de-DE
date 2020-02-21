---
title: 'Lync Server 2013: Ändern einer VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04f3a46d283139e745f1430f835222f25d4d912
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a>Ändern einer VoIP-Route in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In diesem Thema wird erläutert, wie Sie eine VoIP-Route bearbeiten. Informationen zum Erstellen einer neuen Route finden Sie unter [Create a Voice Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## <a name="to-modify-a-voice-route"></a>So ändern Sie eine VoIP-Route

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Route**.

4.  Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
      - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
      - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.

6.  (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.

7.  Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
      - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
        
          - **Anfangsziffern für Zahlen, die Sie zulassen möchten:** Geben Sie die Präfixwerte ein, die diese Route erfüllen muss (einschließlich des führenden + bei Bedarf). Geben Sie beispielsweise **+425** ein, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
        
          - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, für die diese Route *nicht geeignet* sein soll. Um beispielsweise Zahlen beginnend mit + 425237 aus der Route auszuschließen, geben Sie im Feld **Ausnahmen** den Wert **+ 425237** ein, und klicken Sie dann auf **OK**.
    
      - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Informationen zum Schreiben von regulären Ausdrücken finden Sie unter ".NET Framework reguläre Ausdrücke" unter [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).

8.  Wählen Sie **Anrufer-ID unterdrücken** aus, wenn Sie nicht möchten, dass die ID des Telefons, das den ausgehenden Anruf vornimmt, dem Anrufempfänger angezeigt wird. Wenn Sie diese Option aktivieren, müssen Sie eine **Alternative Anrufer-ID** angeben, die dem Anrufempfänger auf dem Display angezeigt wird.

9.  Klicken Sie auf **Hinzufügen**, und wählen Sie dann einen trunk aus der Liste aus, um ein oder mehrere PSTN-Trunks (Public Switched Telephone Network) mit der VoIP-Route zuzuordnen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihre Bereitstellung Microsoft Office Communications Server 2007 R2 Vermittlungsserver enthält, stehen Sie auch in der Liste zur Verfügung.

    
    </div>

10. Zum Zuordnen einer oder mehrerer PSTN-Verwendungen zur VoIP-Route klicken Sie auf **auswählen** , und wählen Sie einen Eintrag aus der Liste der PSTN-Verwendungsdaten Sätze aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden.
    
    <div>
    

    > [!NOTE]  
    > Informationen zum Anzeigen der Eigenschaften aller verfügbaren PSTN-Verwendungsdaten Sätze finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</A>.<BR>Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungs Einträgen in lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungs Einträgen in lync Server 2013</A>.

    
    </div>

11. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!NOTE]  
    > Im Gegensatz zu einer VoIP-Richtlinie, in der die Reihenfolge, in der die PSTN-Verwendungsdaten Sätze aufgeführt sind, wichtig ist, ist die Reihenfolge der PSTN-Verwendungsdaten Sätze in einer VoIP-Route unbedeutend. Es wird jedoch empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server durchläuft die Liste von oben nach unten.)

    
    </div>

12. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine VoIP-Route speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.

    
    </div>

13. Klicken Sie auf **OK**.

14. Klicken Sie auf der Seite **Route** auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine VoIP-Route erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

