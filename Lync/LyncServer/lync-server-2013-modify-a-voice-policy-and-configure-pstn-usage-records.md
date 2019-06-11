---
title: 'Lync Server 2013: Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, wenn Sie eine VoIP-Richtlinie ändern möchten. Wenn Sie eine neue VoIP-Richtlinie erstellen möchten, lesen Sie [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) für das Verfahren.

<div>


> [!NOTE]  
> Wenn ein Benutzer einer VoIP-Richtlinie zugewiesen ist, die keine zugehörigen PSTN-Nutzungsdatensätze (Public Switched Telephone Network) hat, kann der Benutzer keine ausgehenden Anrufe tätigen. Eine Auflistung aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Nutzungsdatensätze und Anzeigen der zugehörigen Eigenschaften finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</A>.



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>So ändern Sie eine VoIP-Richtlinie

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.

4.  Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.
    
    <div>
    

    > [!NOTE]  
    > Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.

    
    </div>

5.  (Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.

6.  Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:
    
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
    
      - Die **Überschreibung von Bandbreitenrichtlinien** ermöglicht Administratoren das außer Kraft setzen von Richtlinien Entscheidungen zur Anrufannahme Steuerung für einen bestimmten Benutzer. Diese ist standardmäßig deaktiviert.
        
        <div>
        

        > [!NOTE]  
        > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.

        
        </div>
    
      - Durch eine **böswillige Anrufprotokollierung** können Benutzer bösartige Anrufe (wie Bombendrohungen) mithilfe der Client-UI melden, die wiederum die Anrufe in den Anruf Detaildatensätzen (CDRs) kennzeichnet. Diese Option ist standardmäßig deaktiviert.

7.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste aller PSTN-Verwendungseinträge auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Einträge, die Sie dieser VoIP-Richtlinie zuordnen möchten und klicken Sie anschließend auf **OK**.
    
      - Markieren Sie einen Eintrag und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus der VoIP-Richtlinie zu entfernen.
    
      - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser VoIP-Richtlinie zuzuordnen:
        
        1.  Klicken Sie auf **Neu**.
        
        2.  Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie könnten beispielsweise einen PSTN-Verwendungsdatensatz namens **Redmond** für Vollzeitbeschäftigte in Redmond und einen weiteren Datensatz namens **RedmondTemps** für Mitarbeiter mit Zeitverträgen erstellen.
            
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
        
        1.  Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.
        
        2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            
              - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung die Routen, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
            
              - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
            
              - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Klicken Sie auf **OK**.

8.  Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    
    <div>
    

    > [!NOTE]  
    > Die Reihenfolge, in der die Einträge für PSTN-Nutzung in der VoIP-Richtlinie aufgeführt sind, ist erheblich. Lync Server durchläuft die Liste von oben nach unten. Wir empfehlen, die Liste nach Häufigkeit der Verwendung zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

9.  Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungseinträge für die Anrufweiterleitung und das gleichzeitige Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:
    
      - Um dieselben PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie in dieser VoIP-Richtlinie zu verwenden, wählen Sie aus dem Dropdownmenü die Option **Mithilfe der PSTN-Anrufverwendung weiterleiten** aus.
    
      - Wenn Sie die Anrufweiterleitung und gleichzeitiges Klingeln nur für interne lync-Benutzer zulassen möchten, wählen Sie nur im Dropdownmenü die Option **an interne lync-Benutzer weiterleiten** aus. Calls will not be forwarded to external PSTN numbers.
    
      - Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.
        
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
                
                  - Markieren Sie die Route und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Klicken Sie auf **OK**.
        
          - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:
            
            1.  Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten und klicken Sie auf **Details anzeigen**.
            
            2.  Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
                
                  - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine, die Sie diesem PSTN-Verwendungseintrag zuordnen wollen und klicken Sie dann auf **OK**.
                
                  - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route und klicken Sie auf **Entfernen**.
                
                  - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Markieren Sie die Route und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Klicken Sie auf **OK**.

10. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Übersetzte Nummer zum Testen** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine VoIP-Richtlinie speichern, die den Test noch nicht bestanden hat, und diese dann später erneut konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.

    
    </div>

11. Klicken Sie auf **OK**.

12. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit ausführen** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

13. (Optional) Die Voicemail-Umgehung erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers entgegengenommen wurde und trennt den Anruf von der Voicemail des Mobiltelefons. Somit kann der Anruf weiterhin auf den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen. Ausführliche Informationen zum Konfigurieren einer Voicemail-Richtlinie finden Sie unter [Konfigurieren von Voicemail-Escape in lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
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

