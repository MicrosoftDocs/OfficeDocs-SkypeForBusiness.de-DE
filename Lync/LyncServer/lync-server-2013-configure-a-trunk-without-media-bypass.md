---
title: 'Lync Server 2013: Konfigurieren eines Trunks ohne medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen trunk mit aktivierter medienumgehung konfigurieren möchten, lesen Sie [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globaler Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>So konfigurieren Sie einen Trunk ohne Medienumgehung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

4.  Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    
      - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    
      - Klicken Sie auf **Neu** und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        
          - **Website trunk:** Wählen Sie die Website für diese trunk-Konfiguration unter **Wählen Sie eine Website** aus, und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        
          - **Pool trunk:** Wählen Sie den Namen des Trunks aus, auf den diese trunk **** -Konfiguration angewendet werden soll, und klicken Sie auf **OK**. Dieser Stamm kann der Stamm Stamm oder zusätzliche Trunks sein, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird dieser Trunk nicht unter **Dienst auswählen** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.<BR>Das Feld <STRONG>Name</STRONG> ist bereits mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts ausgefüllt und kann nicht geändert werden.

    
    </div>

5.  Wählen Sie unter **Verschlüsselungsunterstützungsgrad** eine der folgenden Optionen aus:
    
      - **Erforderlich:** Die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) muss verwendet werden, um den Datenverkehr zwischen dem Vermittlungs Server und dem Gateway oder der PBX (Private Branch Exchange) zu schützen.
    
      - **Optional:** Die SRTP-Verschlüsselung wird verwendet, wenn Sie vom Dienstanbieter oder Gerätehersteller unterstützt wird.
    
      - **Nicht unterstützt:** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und wird daher nicht verwendet.

6.  Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

7.  Aktivieren Sie das Kontrollkästchen **zentralisierte Medienverarbeitung** , wenn ein bekannter medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway (Public Switched Telephone Network), in dem die Medien Terminierung dieselbe IP-Adresse wie die Signalisierungs Terminierung hat). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

8.  Wenn der trunk-Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungs Server unterstützt, aktivieren Sie das Kontrollkästchen **senden verweisen auf das Gateway** .

9.  (Optional) Zur Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu und konfigurieren Sie diese. Die PSTN-Nutzungen, die dieser trunk-Konfiguration zugeordnet sind, werden für alle eingehenden Anrufe über den trunk übernommen, der nicht von einem lync-Endpunkt stammt. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:
    
      - Wenn Sie einen oder mehrere Datensätze aus einer Liste aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungsdaten Sätze auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Markieren Sie einen Datensatz und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.
            
            <div>
            

            > [!NOTE]  
            > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

            
            </div>
        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            
              - Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            
              - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Klicken Sie anschließend auf **OK**.
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:
        
        1.  Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            
              - Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            
              - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Es ist wichtig, die PSTN-Verwendungsdaten Sätze entsprechend dem Mediation Server-Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist. Wenn es sich bei dem Vermittlungs Server-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die trunk-Konfiguration keinem PSTN-Verwendungsdaten Satz zugeordnet ist, der zu einem PSTN-Ziel oder anderen Downstream-Systemen weitergeleitet wird, die über lync verbunden sind. Server.

    
    </div>

10. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung einer optimalen Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Lync Server durchläuft die Liste von oben nach unten.

    
    </div>

11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

12. Aktivieren Sie das Weiterleitungs **Anrufprotokoll** , um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsservers zu ermöglichen.

13. **Enable Forward P-Asserted-Identity-Daten** sollten ausgewählt werden, damit Pai-Anruf Absenderinformationen zwischen dem Vermittlungs Server und der Gatewayseite (und umgekehrt) weitergeleitet werden, wenn vorhanden.

14. **Failovertimer für Ausgangsrouting aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Das erneute Routing zu einem anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungs Server empfangen wird. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln gelten für anrufende Nummern für ausgehende Anrufe
    
      - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Optional) Ordnen Sie **Übersetzungsregeln für die gewählte Nummer** für den Trunk zu und konfigurieren Sie diese. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf.
    
      - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.
    
    <div>
    

    > [!WARNING]  
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.

    
    </div>

17. Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server durchsucht die Übersetzungsregel Liste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehreren Übersetzungsregeln übereinstimmen kann, müssen Sie sicherstellen, dass die stärker einschränkenden Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.

    
    </div>

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

