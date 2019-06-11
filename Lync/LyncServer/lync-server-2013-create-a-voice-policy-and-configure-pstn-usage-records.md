---
title: 'Lync Server 2013: Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11eafa265bf2ba20e8a68a84231092dcb01ffa3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, wenn Sie eine neue VoIP-Richtlinie erstellen möchten. Wenn Sie eine VoIP-Richtlinie bearbeiten möchten, lesen Sie [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) für das Verfahren.

<div>


> [!NOTE]  
> Für jede VoIP-Richtlinie muss mindestens ein zugeordneter PSTN-Nutzungs Eintrag (Public Switched Telephone Network) vorhanden sein. Informationen zum Anzeigen einer Liste aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Nutzungsdaten und zum Anzeigen der zugehörigen Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-voice-policy"></a>So erstellen Sie eine VoIP-Richtlinie

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.

4.  Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu** und wählen Sie einen Bereich für die neue Richtlinie:
    
      - Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.
    
      - Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

5.  Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.
    
    <div>
    

    > [!NOTE]  
    > Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld <STRONG>Name</STRONG> unter <STRONG>Neue VoIP-Richtlinie</STRONG> mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.

    
    </div>

6.  (Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.

7.  Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:
    
      - **Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn das gleichzeitige Klingeln konfiguriert ist und das Handy ausgeschaltet, entladen oder ohne Netz ist.
        
        <div>
        

        > [!NOTE]  
        > Dieses Feature kann nur über die lync Server-Verwaltungsshell konfiguriert werden.

        
        </div>
    
      - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Lync Server 2013 bietet eine wesentlich größere Auswahl an Konfigurationsoptionen für die Anrufweiterleitung. Wenn z. B. eine Organisation nicht möchte, dass eingehende Anrufe extern an das Festnetz (Public Switched Telephone Network, PSTN) weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie anwenden, um diese Einschränkungen durchzusetzen. Diese Option ist standardmäßig aktiviert.
    
      - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In lync Server 2013 kann eine Stellvertretung das gleichzeitige Klingeln konfigurieren, mit dem eingehende Anrufe an seinen Manager alle gleichzeitigen Klingel Ziele der Stellvertretung anrufen können. Dies bietet dem Stellvertreter eine größere Flexibilität bei der Reaktion auf Anrufe, die an den Manager weitergeleitet werden. Diese Option ist standardmäßig aktiviert.
    
      - **Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.
    
      - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.
    
      - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Lync Server 2013 bietet eine wesentlich größere Auswahl an Konfigurationsoptionen für das gleichzeitige Klingeln. Diese Option ist standardmäßig aktiviert.
    
      - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.
    
      - Durch **PSTN-** Umleitungen können Anrufe von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer weitergeleitet werden, wenn das WAN überlastet ist oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.
    
      - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.
        
        <div>
        

        > [!NOTE]  
        > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.

        
        </div>
    
      - Durch eine **böswillige Anrufprotokollierung** können Benutzer böswillige Anrufe (wie Bombendrohungen) mithilfe der Client-UI melden, die wiederum die Anrufe in den Anruf Detaildatensätzen (CDRs) kennzeichnet. Diese Option ist standardmäßig deaktiviert.

8.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten und klicken Sie anschließend auf **OK**.
    
      - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein. Sie könnten beispielsweise einen PSTN-Verwendungseintrag namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Eintrag namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.
            
            <div>
            

            > [!NOTE]  
            > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

            
            </div>
        
        3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Klicken Sie auf **OK**.
    
      - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
        
        1.  Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten und klicken Sie auf **Details einblenden**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.

9.  Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Reihenfolge, in der die Einträge für PSTN-Nutzung in der VoIP-Richtlinie aufgeführt sind, ist erheblich. Lync Server durchläuft die Liste von oben nach unten. Wir empfehlen, die Liste nach Häufigkeit der Verwendung zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

10. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.
    
      - Wenn Sie die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne lync-Benutzer zulassen möchten, wählen Sie die Option **nur für interne lync-Benutzer weiterleiten** aus dem Dropdownmenü aus. Calls will not be forwarded to external PSTN numbers.
    
      - Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.
        
          - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten und klicken Sie anschließend auf **OK**.
        
          - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zu entfernen.
        
          - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuzuordnen:
            
            1.  Klicken Sie auf **Neu**.
            
            2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
                
                <div>
                

                > [!NOTE]  
                > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld <STRONG>Name</STRONG> nicht mehr bearbeitet werden.

                
                </div>
            
            3.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Klicken Sie auf **OK**.
        
          - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
            
            1.  Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten und klicken Sie auf **Details einblenden**.
            
            2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Klicken Sie auf **OK**.

11. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer zum Testen** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine VoIP-Richtlinie speichern, die den Test noch nicht bestanden hat, und diese dann später erneut konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.

    
    </div>

12. Klicken Sie auf **OK**.

13. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

14. (Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde und trennt den Anruf von der Voicemail des Mobiltelefons. Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen. Ausführliche Informationen zum Konfigurieren einer Voicemail-Richtlinie finden Sie unter [Konfigurieren von Voicemail-Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Konfigurieren von Voicemail-Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

