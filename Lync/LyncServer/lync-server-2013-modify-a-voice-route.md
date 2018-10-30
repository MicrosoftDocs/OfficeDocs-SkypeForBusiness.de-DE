---
title: Ändern einer VoIP-Route in Lync Server 2013
TOCTitle: Ändern einer VoIP-Route in Lync Server 2013
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412838(v=OCS.15)
ms:contentKeyID: 49295099
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern einer VoIP-Route in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Thema wird erläutert, wie Sie eine VoIP-Route bearbeiten. Informationen zum Erstellen einer neuen Route finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).

## So ändern Sie eine VoIP-Route

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf **Route**.

4.  Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:
    
      - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
      - Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.

6.  (Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.

7.  Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.
    
      - Geben Sie bei Verwendung des Tools **Muster für Vergleich erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:
        
          - **Anfangsziffern für Nummern, die Sie zulassen möchten:** Geben Sie die gewünschten Präfixwerte für diese Route ein (einschließlich eines vorangestellten +, sofern erforderlich). Geben Sie beispielsweise **+425** ein, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.
        
          - **Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**. Geben Sie einen oder mehrere Werte für den Mustervergleich ein, den bzw. die Sie für diese Route *nicht* verwenden möchten. Um beispielsweise Nummern für die Route auszuschließen, die mit +425237 beginnen, geben Sie im Feld **Ausnahmen** den Wert **+425237** ein, und klicken Sie dann auf **OK**.
    
      - Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird. Ausführliche Informationen zur Verwendung von regulären Ausdrücken finden Sie in "Reguläre Ausdrücke von .NET Framework" unter [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x407).

8.  Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Anrufer-ID** angeben, die dem Anrufempfänger auf dem Display angezeigt wird.

9.  Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere PSTN-Trunks (Public Switched Telephone Network Telefonfestnetz) zuzuordnen, und wählen Sie aus der Liste einen Trunk aus.
    

    > [!NOTE]
    > Wenn Ihre Bereitstellung Microsoft Office Communications Server 2007 R2-Vermittlungsserver umfasst, sind diese ebenfalls in der Liste verfügbar.



10. Wenn Sie der VoIP-Route eine oder mehrere PSTN-Verwendungen zuordnen möchten, klicken Sie auf **Auswählen**, und wählen Sie in der Liste der PSTN-Verwendungsdatensätze, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden, einen Eintrag aus.
    

    > [!NOTE]
    > Informationen zur Anzeige der Eigenschaften aller verfügbaren PSTN-Verwendungen finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013</A>.<BR>Informationen zum Erstellen oder Bearbeiten von PSTN-Verwendungsdatensätzen finden Sie unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013</A>.



11. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, markieren Sie den Datensatznamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!NOTE]
    > Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge der PSTN-Verwendungsdatensätze eine wichtige Rolle spielt, ist die Reihenfolge von PSTN-Verwendungsdatensätzen in einer VoIP-Route unerheblich. Dennoch wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren. Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server durchläuft die Liste von oben nach unten.)



12. (Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein**, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.
    

    > [!NOTE]
    > Sie können eine VoIP-Route speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



13. Klicken Sie auf **OK**.

14. Klicken Sie auf der Seite **Route** auf **Commit** und anschließend auf **Commit für alle**.
    

    > [!NOTE]
    > Bei jeder Erstellung oder Änderung einer VoIP-Route müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

