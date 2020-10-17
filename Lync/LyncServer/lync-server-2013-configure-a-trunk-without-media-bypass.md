---
title: 'Lync Server 2013: Konfigurieren eines Trunks ohne medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fce45563538b41773f76a8733b1c226454e6f76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523122"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen trunk mit aktivierter medienumgehung konfigurieren möchten, finden Sie weitere Informationen unter [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>So konfigurieren Sie einen Trunk ohne Medienumgehung

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

4.  Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    
      - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    
      - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        
          - **Website trunk:** Wählen Sie den Standort für diese trunkkonfiguration unter **Standort auswählen** aus, und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        
          - **Pool trunk:** Wählen Sie in **Dienst auswählen** den Namen des Trunks aus, für den diese trunkkonfiguration gilt, und klicken Sie auf **OK**. Bei diesem trunk kann es sich um den Stamm trunk oder um zusätzliche Trunks handeln, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.
    
    <div>
    

    > [!NOTE]  
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.<BR>Das Feld <STRONG>Name</STRONG> wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden.

    
    </div>

5.  Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    
      - **Erforderlich:** Die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) muss verwendet werden, um den Datenverkehr zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) zu schützen.
    
      - **Optional:** Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dies unterstützt.
    
      - **Nicht unterstützt:** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und wird daher nicht verwendet.

6.  Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

7.  Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

8.  Wenn der trunk Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden von referieren auf das Gateway aktivieren** .

9.  (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden auf alle über den Trunk eingehenden Anrufe angewendet, der nicht aus einem Lync-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:
    
      - Klicken Sie auf **auswählen**, um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungseinträge auszuwählen. Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.
    
      - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
            
            <div>
            

            > [!NOTE]  
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

            
            </div>
        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Klicken Sie auf **OK**.
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:
        
        1.  Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Es ist wichtig, PSTN-Verwendungsdaten Sätze gemäß dem Vermittlungsserver Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist. Wenn es sich bei dem Vermittlungsserver Peer um ein PSTN-Gateway oder einen SBC (Session Border Controller) handelt, wird dringend empfohlen, dass die trunkkonfiguration keinem PSTN-Verwendungsdaten Satz zugeordnet ist, der an ein PSTN-Ziel oder andere nachgeschaltete Systeme weitergeleitet wird, die über lync Server verbunden sind.

    
    </div>

10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Lync Server die Liste von oben nach unten durchlaufen.

    
    </div>

11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

12. **Enable Forward Call History** sollte ausgewählt sein, um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsserver zu ermöglichen.

13. **Enable Forward P-Asserted-Identity Data** sollte ausgewählt sein, damit Pai-Anruf Absenderinformationen zwischen der Vermittlungsserver Seite und der Gatewayseite (und umgekehrt) weitergeleitet werden können, sofern vorhanden.

14. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Das erneute Routing an einen anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die wählende Nummer angewendet.
    
      - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.
    
      - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    
    <div>
    

    > [!WARNING]  
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

    
    </div>

17. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server durchläuft die Liste der Übersetzungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.

    
    </div>

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

