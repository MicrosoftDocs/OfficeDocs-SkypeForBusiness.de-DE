---
title: Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013
TOCTitle: Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399027(v=OCS.15)
ms:contentKeyID: 49295735
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um eine neue VoIP-Richtlinie zu erstellen. Wenn Sie eine VoIP-Richtlinie bearbeiten möchten, finden Sie weitere Informationen unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).


> [!NOTE]
> Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. Informationen zum Anzeigen einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungseinträge und deren Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013</A>.



## So erstellen Sie eine VoIP-Richtlinie

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.

4.  Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu**, und wählen Sie einen Bereich für die neue Richtlinie:
    
      - Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.
    
      - Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

5.  Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.
    

    > [!NOTE]
    > Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld <STRONG>Name</STRONG> unter <STRONG>Neue VoIP-Richtlinie</STRONG> mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.



6.  (Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.

7.  Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:
    
      - **Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn das gleichzeitige Klingeln konfiguriert ist und das Handy ausgeschaltet, entladen oder ohne Netz ist.
        

        > [!NOTE]
        > Dieses Feature kann nur über die Lync Server-Verwaltungsshell konfiguriert werden.

    
      - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Lync Server 2013 bietet erheblich mehr Konfigurationsoptionen für die Anrufweiterleitung. Wenn z. B. eine Organisation nicht möchte, dass eingehende Anrufe extern an das Festnetz (Public Switched Telephone Network, PSTN) weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie anwenden, um diese Einschränkungen durchzusetzen. Diese Option ist standardmäßig aktiviert.
    
      - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und entgegennehmen können. In Lync Server 2013 kann ein Delegat das gleichzeitige Klingeln konfigurieren. Wenn dann bei seinem Vorgesetzten Anrufe eingehen, klingelt es auf allen Zielgeräten für das gleichzeitige Klingeln des Delegaten. Dies bietet dem Delegat mehr Flexibilität beim Beantworten von Anrufen für seinen Vorgesetzten. Diese Option ist standardmäßig aktiviert.
    
      - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.
    
      - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.
    
      - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Lync Server 2013 bietet erheblich mehr Konfigurationsoptionen für das gleichzeitige Klingeln. Diese Option ist standardmäßig aktiviert.
    
      - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.
    
      - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.
    
      - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.
        

        > [!NOTE]
        > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.

    
      - **Nachverfolgung von Missbrauch durch Anrufer** ermöglicht Benutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche. Die Anrufe werden anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet. Diese Option ist standardmäßig deaktiviert.

8.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein. Sie könnten beispielsweise einen PSTN-Verwendungseintrag namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Eintrag namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.
            

            > [!NOTE]
            > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Klicken Sie auf **OK**.
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
        
        1.  Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.

9.  Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der VoIP-Richtlinie aufgeführt werden, ist relevant. Lync Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.



10. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.
    
      - Um die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne Lync-Benutzer zu aktivieren, wählen Sie aus dem Dropdownmenü die Option **Nur an interne Lync-Benutzer weiterleiten** aus. Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.
    
      - Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.
        
          - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.
        
          - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zu entfernen.
        
          - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuzuordnen:
            
            1.  Klicken Sie auf **Neu**.
            
            2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
                

                > [!NOTE]
                > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

            
            3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Klicken Sie auf **OK**.
        
          - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
            
            1.  Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.
            
            2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Klicken Sie auf **OK**.

11. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer für Test** angezeigt.
    

    > [!NOTE]
    > Sie können eine VoIP-Richtlinie speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



12. Click **OK**.

13. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen**, und klicken Sie anschließend auf **Commit für alle Elemente ausfhren**.
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



14. (Optional) Voicemail-Escape erkennt, dass ein Anruf sofort vom Voicemail-System des Mobiltelefons des Benutzers entgegengenommen wurde und trennt den Anruf beim Voicemail-System des Mobiltelefons. Dadurch klingelt es für diesen Anruf auf den anderen Endpunktgeräten des Benutzers weiterhin, und der Benutzer hat die Gelegenheit, den Anruf anzunehmen. Ausführliche Informationen zum Konfigurieren einer VoIP-Richtlinie finden Sie unter [Konfigurieren des Wechsels der Voicemail in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

## Siehe auch

#### Aufgaben

[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Konfigurieren des Wechsels der Voicemail in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

