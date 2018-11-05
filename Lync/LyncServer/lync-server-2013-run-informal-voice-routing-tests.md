---
title: Ausführen informeller Tests für das VoIP-Routing
TOCTitle: Ausführen informeller Tests für das VoIP-Routing
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399049(v=OCS.15)
ms:contentKeyID: 49295779
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen informeller Tests für das VoIP-Routing

 

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Sie können mit dem Dialogfeld **Testfallinformationen für das VoIP-Routing erstellen** interne Tests ausführen, bevor Sie einen tatsächlichen Testfall erstellen. Wenn Sie mit dem Ergebnis eines Tests zufrieden sind, können Sie den Test als formalen Testfall speichern.

## So führen Sie einen informellen Test für das VoIP-Routing aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Testfallinformationen für das VoIP-Routing erstellen**.

5.  Geben Sie im Feld **Gewählte Nummer** die Telefonnummer ein, die Sie für diesen Test verwenden möchten. Diese Nummer wird normalisiert und im Feld **Normalisierte Nummer** des Ergebnisbereichs angezeigt.

6.  Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen, der zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.
    
    Wenn Sie den Test ausführen, wird die erste Normalisierungsregel in diesen Wähleinstellungen, die mit der gewählten Nummer übereinstimmt, im Feld **Normalisierungsregel** des Ergebnisbereichs angezeigt.

7.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.

8.  (Optional) Aktivieren Sie das Kontrollkästchen **Aus Benutzer auffüllen**, wenn Sie die gewählte Nummer für eine VoIP-Richtlinie testen möchten, die einem bestimmten Benutzer zugewiesen ist.
    
    1.  Klicken Sie auf **Durchsuchen**, um das Dialogfeld **Enterprise-VoIP-Benutzer auswählen** anzuzeigen.
    
    2.  Klicken Sie auf **Suchen**, um die Liste der Benutzer anzuzeigen, die für Enterprise-VoIP aktiviert sind.
    
    3.  Doppelklicken Sie auf den Benutzernamen, dessen zugewiesene VoIP-Richtlinie Sie für diesen Test verwenden möchten. Das Feld **Richtlinie** wird jetzt mit der VoIP-Richtlinie gefüllt, die dem ausgewählten Benutzer zugewiesen ist.
    
    Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.

9.  Klicken Sie auf **Ausführen**, um den Testfall auszuführen. Die Ergebnisse werden im rechten Bereich des Dialogfelds angezeigt.

10. (Optional) Klicken Sie auf **Speichern unter**, wenn Sie diese Testkonfiguration als formalen Testfall speichern möchten.
    
    1.  Geben Sie im Feld **Name** des Dialogfelds **Testfallinformationen für das VoIP-Routing speichern** einen eindeutigen Namen für den Testfall ein.
        
        Der Name muss unter allen VoIP-Routing-Testfällen in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Er kann bis zu 32 Zeichen lang sein und beliebige alphanumerische Zeichen sowie umgekehrte Schrägstriche (\\), Punkte (.) oder Unterstriche (\_) enthalten.
    
    2.  Beachten Sie, dass die verbleibenden Felder im Dialogfeld **Testfallinformationen für das VoIP-Routing speichern** schreibgeschützt sind und mit den Daten *und* Ergebnissen aus der informellen Testkonfiguration vorausgefüllt werden. Stellen Sie sicher, dass dies die Konfiguration ist, die Sie für den Testfall speichern möchten.
        

        > [!NOTE]
        > Die Werte aus den Testergebnissen werden folgendermaßen zum Vorausfüllen der Felder im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> verwendet: 
        > <UL>
        > <LI>
        > <P><STRONG>Erwartete Übersetzung</STRONG> wird mit dem Wert im Feld <STRONG>Normalisierte Nummer</STRONG> vorausgefüllt.</P>
        > <LI>
        > <P><STRONG>Erwartete Route</STRONG> wird mit dem Wert im Feld <STRONG>Erste Route</STRONG> vorausgefüllt.</P>
        > <LI>
        > <P><STRONG>Erwarteter PSTN-Verwendungsdatensatz</STRONG> wird mit dem Wert im Feld <STRONG>Erste PSTN-Verwendung</STRONG> vorausgefüllt.</P></LI></UL>Wenn für einen dieser Werte beim Test keine Übereinstimmungen gefunden werden, bleibt das entsprechende Feld im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> leer.

    
    3.  Klicken Sie auf **OK**, um den Testfall zu speichern, oder klicken Sie auf **Abbrechen**, um zum Dialogfeld **Testfallinformationen für das VoIP-Routing anzeigen** zurückzukehren und weitere Änderungen vorzunehmen, bevor Sie den Test speichern.

11. Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Testfall für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um den Testfall zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Ausführen von Testfällen für das VoIP-Routing](lync-server-2013-run-voice-routing-test-cases.md)  
[Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  

#### Weitere Ressourcen

[Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

