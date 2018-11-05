---
title: 'Lync Server 2013: Konfigurieren eines Trunks mit Medienumgehung'
TOCTitle: Konfigurieren eines Trunks mit Medienumgehung
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398792(v=OCS.15)
ms:contentKeyID: 49294858
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Gehen Sie wie folgt vor, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunk mit deaktivierter Medienumgehung finden Sie unter [Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Lync Server 2013-Routen für ausgehende Anrufe und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort zum richtigen Gateway geroutet werden.

Es wird dringend empfohlen, die Medienumgehung zu aktivieren. Bevor Sie die Medienumgehung jedoch für einen SIP-Trunk aktivieren, müssen Sie sicherstellen, dass Ihr qualifizierter SIP-Trunkanbieter die Medienumgehung unterstützt und die Anforderungen für eine erfolgreiche Aktivierung erfüllt. Insbesondere muss der Anbieter über die IP-Adressen der Server im internen Netzwerk Ihrer Organisation verfügen. Wenn der Anbieter dieses Szenario nicht unterstützen kann, ist die Medienumgehung nicht erfolgreich. Ausführliche Informationen finden Sie unter [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation.


> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs (Session Border Controller). Microsoft hat eine Reihe von PSTN-Gateways mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die Zertifizierung für die SBCs ist im Gange. Die Medienumgehung wird nur für die Produkte und Versionen unterstützt, die auf der Webseite für das Unified Communications Open Interoperability Program \endash Lync Server unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x407</A> aufgelistet werden.



Eine Trunkkonfiguration wie die unten beschriebene gruppiert Parametersätze, die auf Trunks angewendet werden, denen die entsprechende Trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann globale Reichweite haben (für alle Trunks, die keine spezifischere Standort- oder Poolkonfiguration haben) oder einen Standort oder Pool betreffen. Eine Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

## So konfigurieren Sie einen Trunk mit Medienumgehung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration** .

4.  Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    
      - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global** ), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    
      - Klicken Sie auf **Neu** , und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        
          - **Standorttrunk :** Wählen Sie den Standort für diese Trunkkonfiguration unter **Standort auswählen** aus, und klicken Sie dann auf **OK** . Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt.
        
          - **Pooltrunk :** Wählen Sie den Namen des Trunks aus, für den diese Trunkkonfiguration gilt. Bei diesem Trunk kann es sich um den Stammtrunk oder jeden anderen im Topologie-Generator definierten zusätzlichen Trunk handeln. Klicken Sie im Dialogfeld **Dienst auswählen** auf **OK** . Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird der Trunk nicht im Dialogfeld **Dienst auswählen** angezeigt.
    

    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden.<BR>Das Feld <STRONG>Name</STRONG> wird mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts vorausgefüllt und kann nicht geändert werden.



5.  Geben Sie in **Maximal unterstützte frühe Dialoge** einen Wert ein. Dies ist die maximale Anzahl von gegabelten Antworten auf an den Vermittlungsserver gesendete INVITE-Anforderungen, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) beim Dienstanbieter empfangen kann. Der Standardwert lautet 20.
    

    > [!NOTE]
    > Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten.



6.  Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    
      - **Erforderlich :** Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    
      - **Optional :** Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    
      - **Nicht unterstützt :** Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

7.  Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren** , wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.
    

    > [!IMPORTANT]
    > Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planung der Medienumgehung in Lync Server 2013</A> in der Planungsdokumentation.



8.  Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung** , wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

9.  Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden von REFER an das Gateway aktivieren** .
    

    > [!NOTE]
    > Wenn Sie diese Option deaktivieren, während die Option <STRONG>Medienumgehung aktivieren</STRONG> ausgewählt ist, sind zusätzliche Einstellungen erforderlich. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> ausführen, um RTCP für aktive und gehaltene Anrufe zu deaktivieren, um geeignete Bedingungen für die Medienumgehung zu schaffen. Ausführliche Informationen finden Sie in der Dokumentation zur <A href="lync-server-2013-lync-server-management-shell.md">Lync Server-Verwaltungsshell</A>.<BR>Alternativ können Sie <STRONG>Verweise mit Drittanbieteranrufsteuerung aktivieren</STRONG> , wenn Sie möchten, dass für übertragene Anrufe eine Medienumgehung stattfinden soll, und das Gateway keine SIP REFER-Anforderungen unterstützt.



10. (Optional) Für die Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu, und konfigurieren Sie diese. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden auf alle über den Trunk eingehenden Anrufe angewendet, die nicht von einem Lync-Endpunkt stammen. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:
    
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



11. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Lync Server durchläuft die Liste von oben nach unten.



12. Aktivieren Sie **RTP-Latching aktivieren** , um Umgehungsmedien für Clients hinter einer NAT oder Firewall und einem SBC, der Latching unterstützt, zu aktivieren.

13. **Anrufweiterleitungsverlauf aktivieren** sollte aktiviert sein, damit das Senden der Anrufverlaufsinformationen an den Gatewaypeer des Vermittlungsservers aktiviert wird.

14. **Weiterleiten von PAI-Daten aktivieren** sollte aktiviert sein, damit eventuell vorhandene PAI-Informationen (P-Asserted-Identity) zum Anrufer zwischen der Vermittlungsserverseite und der Gatewayseite (und umgekehrt) weitergeleitet werden.

15. **Ausgehenden Routing-Failover-Timer aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Die Umleitung an einen anderen Trunk findet statt, wenn der Vermittlungsserver diese Benachrichtigung nicht erhält. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.

16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für anrufende Nummern** für den Trunk. Diese Übersetzungsregeln gelten für anrufende Nummern für ausgehende Anrufe
    
      - Klicken Sie auf **Auswählen** , um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen** , um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    

    > [!WARNING]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.



17. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für angerufene Nummern** für den Trunk. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf
    
      - Klicken Sie auf **Auswählen** , um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen** , um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    

    > [!WARNING]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.



18. Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Lync Server 2013 durchläuft die Liste der Übersetzungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer <EM>unter</EM> der restriktiveren Regel platziert werden.



19. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK** .

20. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** , und klicken Sie anschließend auf **Commit für alle** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



Nachdem Sie den Trunk konfiguriert haben, können Sie mit der Konfiguration der Medienumgehung fortfahren. Legen Sie die Optionen für die globale Medienumgehung fest, wie beschrieben unter [Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in der Bereitstellungsdokumentation.

## Siehe auch

#### Aufgaben

[Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  

#### Konzepte

[Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Weitere Ressourcen

[Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md)

