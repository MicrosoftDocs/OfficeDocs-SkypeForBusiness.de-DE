---
title: Ausführen von Testfällen für das VoIP-Routing
TOCTitle: Ausführen von Testfällen für das VoIP-Routing
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413068(v=OCS.15)
ms:contentKeyID: 49295986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen von Testfällen für das VoIP-Routing

 

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Sie können sämtliche Testfälle in Ihrem Paket mit Testfällen für das VoIP-Routing oder lediglich einen bzw. einige ausgewählte Testfälle ausführen.

## So führen Sie alle Testfälle für das VoIP-Routing aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** und anschließend auf **Alle ausführen**.
    
    Ob ein Testfall erfolgreich war oder nicht, wird in der Spalte **Erfolgreich/Fehler** angezeigt. Für Testfälle, die noch nicht ausgeführt wurden, wird in der Spalte **Erfolgreich/Fehler** der Eintrag "N/A" angezeigt.

5.  (Optional) Doppelklicken Sie auf den Namen eines Testfalls, um detaillierte Ergebnisse anzuzeigen. Die Ergebnisse werden rechts auf der Seite **Testfall bearbeiten** im schattierten Bereich angezeigt:
    
    1.  **Testergebnis:** Gesamtstatus für die Ausführung des Testfalls (erfolgreich oder Fehler)
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel in den für diesen Testfall ausgewählten Wähleinstellungen, die mit der gewählten Nummer (dem Wert im Feld **Zu testende Nummer**) übereinstimmt.
    
    3.  **Normalisierte Nummer:** Der Wert der gewählten Nummer nach der Übersetzung mithilfe der Normalisierungsregel.
    
    4.  **Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdatensatz (Public Switched Telephone Network, Festnetz) in der für diesen Testfall ausgewählten VoIP-Richtlinie, der mit der gewählten Nummer übereinstimmt.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdatensatz, die mit der gewählten Nummer übereinstimmt.
        

        > [!NOTE]
        > Die Felder <STRONG>Erwarteter PSTN-Verwendungsdatensatz</STRONG> und <STRONG>Erwartete Route</STRONG> sind bei der Testfallkonfiguration für das VoIP-Routing optional. Wenn diese Werte nicht für den Testfall angegeben werden, sind die entsprechenden Felder in den Testergebnissen leer.



## So führen Sie einen oder mehrere ausgewählte Testfälle für das VoIP-Routing aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Testfälle, die Sie ausführen möchten.

5.  Klicken Sie im Menü **Aktion** auf **Ausgewählte ausführen**.
    
    Ob ein Testfall erfolgreich war oder nicht, wird in der Spalte **Erfolgreich/Fehler** angezeigt. Für Testfälle, die noch nicht ausgeführt wurden, wird in der Spalte **Erfolgreich/Fehler** der Eintrag "N/A" angezeigt.

6.  (Optional) Doppelklicken Sie auf den Namen eines Testfalls, um detaillierte Ergebnisse anzuzeigen. Die Ergebnisse werden rechts auf der Seite **Testfall bearbeiten** im schattierten Bereich angezeigt:
    
    1.  **Testergebnis:** Gesamtstatus für die Ausführung des Testfalls (erfolgreich oder Fehler)
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel in den für diesen Testfall ausgewählten Wähleinstellungen, die mit der gewählten Nummer (dem Wert im Feld **Zu testende Nummer**) übereinstimmt.
    
    3.  **Normalisierte Nummer:** Der Wert der gewählten Nummer nach der Übersetzung mithilfe der Normalisierungsregel.
    
    4.  **Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdatensatz in der für diesen Testfall ausgewählten VoIP-Richtlinie, der mit der gewählten Nummer übereinstimmt.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdatensatz, die mit der gewählten Nummer übereinstimmt.
        

        > [!NOTE]
        > Die Felder <STRONG>Erwarteter PSTN-Verwendungsdatensatz</STRONG> und <STRONG>Erwartete Route</STRONG> sind bei der Testfallkonfiguration für das VoIP-Routing optional. Wenn diese Werte nicht für den Testfall angegeben werden, sind die entsprechenden Felder in den Testergebnissen leer.



## Siehe auch

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Ausführen von Tests für das VoIP-Routing in Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)

