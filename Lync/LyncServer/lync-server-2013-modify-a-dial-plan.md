---
title: 'Lync Server 2013: Ändern eines Wählplans'
TOCTitle: Ändern eines Wählplans
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412797(v=OCS.15)
ms:contentKeyID: 49295030
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern eines Wählplans in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um einen vorhandenen Wählplan zu ändern. Informationen zum Erstellen eines neuen Wählplans finden Sie unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## So ändern Sie einen Satz mit Wähleinstellungen

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan** .

4.  Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.
    

    > [!NOTE]
    > Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt. Sie können nicht geändert werden.



5.  (Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.
    

    > [!IMPORTANT]
    > Der Name im Feld <STRONG>Einfacher Name</STRONG> muss unter den Wählplänen innerhalb der Lync Server 2013-Bereitstellung eindeutig sein. Der Name darf nicht mehr als 256&nbsp;Unicode-Zeichen umfassen und kann Buchstaben oder Zahlen, Bindestriche (-), Punkte (.), Pluszeichen (+) oder Unterstriche (_) enthalten.<BR>Leerzeichen sind im Feld <STRONG>Einfacher Name</STRONG> nicht zulässig.



6.  (Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.

7.  (Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.
    

    > [!NOTE]
    > Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.



8.  (Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9). Sie können ein Präfix eingeben, das aus bis zu vier Zeichen besteht (d. h. \#, \* und 0-9).
    

    > [!NOTE]
    > Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.



9.  Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:
    
      - Klicken Sie auf **Auswählen** , um eine oder mehrere Regeln aus einer Liste aller Normalisierungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten, und klicken Sie anschließend auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details einblenden** , um eine Normalisierungsregel zu bearbeiten, die bereits dem Wählplan zugeordnet ist. Ausführliche Informationen zum Bearbeiten einer Regel finden Sie unter [Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    

    > [!NOTE]
    > Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein. Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln in Lync Server 2013</A> in der Planungsdokumentation.



10. Stellen Sie sicher, dass die Normalisierungsregeln für den Wählplan in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    

    > [!IMPORTANT]
    > Lync Server durchläuft die Liste der Normalisierungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Wähleinplan so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.<BR>Die standardmäßige Normalisierungsregel <STRONG>Alle beibehalten</STRONG> lautet <STRONG>^(\d{11})$</STRONG> und stimmt mit einer beliebigen elfstelligen Nummer überein. Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die auf elfstellige Nummern zutrifft, die mit 1425 beginnen, müssen Sie sicherstellen, dass die Regel <STRONG>Alle beibehalten</STRONG> unterhalb der restriktiveren Regel <STRONG>^(1425\d{7})$</STRONG> einsortiert wird.



11. (Optional) Geben Sie eine Nummer zum Testen des Wählplans ein, und klicken Sie auf **Los** . Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    

    > [!NOTE]
    > Sie können einen Wählplan speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



12. Klicken Sie auf **OK** .

13. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Wählplan erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Weitere Ressourcen

[Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

