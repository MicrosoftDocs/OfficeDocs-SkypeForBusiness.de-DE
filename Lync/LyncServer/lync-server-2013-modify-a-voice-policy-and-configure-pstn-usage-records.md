---
title: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013
TOCTitle: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398511(v=OCS.15)
ms:contentKeyID: 49294319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um eine VoIP-Richtlinie zu ändern. Wenn Sie eine neue VoIP-Richtlinie erstellen möchten, finden Sie das entsprechende Verfahren unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md).


> [!NOTE]
> Wenn ein Benutzer einer VoIP-Richtlinie ohne zugeordnete PSTN-Verwendungsdatensätze (Public Switched Telephone Network, Telefonfestnetz) zugewiesen wird, kann der Benutzer keine ausgehenden Anrufe tätigen. Eine Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungsdatensätze und deren Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013</A>.



## So ändern Sie eine VoIP-Richtlinie

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.

4.  Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.
    

    > [!NOTE]
    > Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.



5.  (Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.

6.  Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:
    
      - Die **Voicemailumgehung** verhindert, dass Anrufe unmittelbar an das Voicemailsystem des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon deaktiviert ist, keine Akkukapazitäten mehr hat oder sich außerhalb des abgedeckten Bereichs befindet.
        

        > [!NOTE]
        > Dieses Feature ist nur über die Lync Server-Verwaltungsshell konfigurierbar.

    
      - Die **Anrufweiterleitung** ermöglicht dem Benutzer die Weiterleitung von Anrufen an andere Telefone und andere Clientgeräte. Lync Server 2013 bietet eine viel umfassendere Palette an Konfigurationsoptionen für die Anrufweiterleitung. Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen. Diese Option ist standardmäßig aktiviert.
    
      - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Lync Server 2013 kann ein Stellvertreter das gleichzeitige Klingeln konfigurieren, wodurch die bei dessen Manager eingehenden Anrufe ein Klingeln bei sämtlichen für gleichzeitiges Klingeln vorgesehenen Zielen des Stellvertreters auslösen. Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren. Diese Option ist standardmäßig aktiviert.
    
      - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.
    
      - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.
    
      - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Lync Server 2013 ermöglicht eine breitere Palette an Konfigurationsoptionen für das gleichzeitige Klingeln. Diese Option ist standardmäßig aktiviert.
    
      - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.
    
      - **PSTN-Umleitung** ermöglicht das Umleiten der Anrufe von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.
    
      - **Außerkraftsetzen der Bandbreitenrichtlinie** ermöglicht Administratoren das Außerkraftsetzen der Entscheidungen der Anrufsteuerungsrichtlinie für einen bestimmten Benutzer. Diese Option ist standardmäßig deaktiviert.
        

        > [!NOTE]
        > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.

    
      - **Nachverfolgung bei Missbrauch durch Anrufer** ermöglicht Benutzern das Melden von Drohanrufen (z. B. Bombendrohungen) über die Clientbenutzeroberfläche, wo die Anrufe anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet werden. Diese Option ist standardmäßig deaktiviert.

7.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.
    
      - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie könnten beispielsweise einen PSTN-Verwendungsdatensatz namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Datensatz namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.
            

            > [!NOTE]
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, um eine oder mehrere Routen aus der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen, markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Klicken Sie auf **OK**.
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
        
        1.  Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, um eine oder mehrere Routen aus der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen, markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen erhalten Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen erhalten Sie im Abschnitt [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.

8.  Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!NOTE]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der VoIP-Richtlinie aufgeführt werden, ist relevant. Lync Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.



9.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.
    
      - Wenn die Anrufweiterleitung und gleichzeitiges Klingeln nur für interne Lync-Benutzer zulässig sein soll, wählen Sie im Dropdownmenü die Option **Nur an interne Lync-Benutzer weiterleiten** aus. Die Anrufe werden dann nicht an externe PSTN-Nummern weitergeleitet.
    
      - Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.
        
          - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln auszuwählen. Markieren Sie die Datensätze, die Sie der Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.
        
          - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.
        
          - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:
            
            1.  Klicken Sie auf **Neu**.
            
            2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.
                

                > [!NOTE]
                > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

            
            3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen erhalten Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route, und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen erhalten Sie im Abschnitt [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Klicken Sie auf **OK**.
        
          - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
            
            1.  Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
            
            2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Klicken Sie auf **OK**.

10. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.
    

    > [!NOTE]
    > Sie können eine VoIP-Richtlinie speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



11. Klicken Sie auf **OK**.

12. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



13. (Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde, und trennt den Anruf von der Voicemail des Mobiltelefons. Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen. Ausführliche Informationen zur Konfiguration einer Voicemailumgehung finden Sie im Abschnitt [Konfigurieren des Wechsels der Voicemail in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

## Siehe auch

#### Aufgaben

[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Ändern einer VoIP-Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Konfigurieren des Wechsels der Voicemail in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

