---
title: 'Lync Server 2013: Konfigurieren eines Trunks ohne Medienumgehung'
TOCTitle: Konfigurieren eines Trunks ohne Medienumgehung
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425831(v=OCS.15)
ms:contentKeyID: 49293624
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen Trunk mit aktivierter Medienumgehung konfigurieren möchten, finden Sie weitere Informationen unter [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

## So konfigurieren Sie einen Trunk ohne Medienumgehung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration** .

4.  Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    
      - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global** ), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    
      - Klicken Sie auf **Neu** , und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        
          - **Standorttrunk :** Wählen Sie den Standort für diese Trunkkonfiguration unter **Standort auswählen** aus, und klicken Sie anschließend auf **OK** . Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        
          - **Pooltrunk :** Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK** . Bei diesem Trunk kann es sich um einen Stammtrunk oder um einen der weiteren Trunks handeln, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen** .
    

    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.<BR>Das Feld <STRONG>Name</STRONG> wird mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts vorausgefüllt und kann nicht geändert werden.



5.  Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    
      - **Erforderlich :** Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    
      - **Optional :** Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    
      - **Nicht unterstützt :** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

6.  Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

7.  Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung** , wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

8.  Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden von REFER an das Gateway aktivieren** .

9.  (Optional) Für die Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu, und konfigurieren Sie diese. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden auf alle über den Trunk eingehenden Anrufe angewendet, die nicht von einem Lync-Endpunkt stammen. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:
    
      - Klicken Sie zur Auswahl eines oder mehrerer Datensätze in einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Datensätze auf **Auswählen** . Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen** , um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:
        
        1.  Klicken Sie auf **Neu** .
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.
            

            > [!NOTE]
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen** , markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK** .
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus, und klicken Sie auf **Entfernen** .
            
              - Klicken Sie auf **Neu** , um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)
            
              - Wählen Sie eine Route aus, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, und klicken Sie auf **Details anzeigen** , um die Route zu bearbeiten. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)
        
        4.  Klicken Sie auf **OK** .
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:
        
        1.  Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen** .
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen** , markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK** .
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus, und klicken Sie auf **Entfernen** .
            
              - Klicken Sie auf **Neu** , um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)
            
              - Wählen Sie eine Route aus, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, und klicken Sie auf **Details anzeigen** , um die Route zu bearbeiten. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)
        
        3.  Klicken Sie auf **OK** .
    

    > [!IMPORTANT]
    > Es ist wichtig, dass PSTN-Verwendungsdatensätze entsprechend dem Vermittlungsserverpeer zugeordnet werden, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn der Vermittlungsserverpeer ein PSTN-Gateway oder ein Session Border Controller (SBC) ist, ist es sehr zu empfehlen, die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zuzuordnen, der zu einem PSTN-Ziel oder anderen nachgelagerten Systemen führt, die über Lync Server verbunden sind.



10. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Lync Server durchläuft die Liste von oben nach unten.



11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

12. **Anrufweiterleitungsverlauf aktivieren** sollte aktiviert sein, damit das Senden der Anrufverlaufsinformationen an den Gatewaypeer des Vermittlungsservers aktiviert wird.

13. **Weiterleitung von P-Asserted-Identity-Daten aktivieren** sollte ausgewählt sein, damit PAI-Informationen zum Anrufursprung zwischen dem Vermittlungsserver und dem Gateway (in beide Richtungen) weitergeleitet werden können, sofern vorhanden.

14. **Ausgehenden Routing-Failover-Timer aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Die Umleitung an einen anderen Trunk findet statt, wenn der Vermittlungsserver diese Benachrichtigung nicht erhält. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für anrufende Nummern** für den Trunk. Diese Übersetzungsregeln gelten für anrufende Nummern für ausgehende Anrufe
    
      - Klicken Sie auf **Auswählen** , um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen** , um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Sicherheit Hinweis:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</td>
    </tr>
    </tbody>
    </table>


16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für angerufene Nummern** für den Trunk. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf
    
      - Klicken Sie auf **Auswählen** , um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen** , um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    
    > [!CAUTION]  
	> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.


17. Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Lync Server durchläuft die Liste der Übersetzungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.



18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK** .

19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** , und klicken Sie anschließend auf **Commit für alle** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Weitere Ressourcen

[Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md)

