---
title: 'Lync Server 2013: Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel'
TOCTitle: Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399036(v=OCS.15)
ms:contentKeyID: 49295757
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um eine Normalisierungsregel in der Lync Server-Systemsteuerung zu erstellen oder zu ändern. Alternativ können Sie eine Normalisierungsregel auch manuell erstellen oder ändern. Informationen hierzu finden Sie unter [Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

## So definieren Sie eine Regel mit dem Tool zum Erstellen einer Normalisierungsregel

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Optional) Führen Sie die Schritte in [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) bis Schritt 11 oder [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) bis Schritt 10 durch.

4.  Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (beispielsweise **5StellenDurchwahl**).

5.  (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise "Übersetzt 5-stellige Durchwahlnummern").

6.  Geben Sie im Abschnitt **Erstellen einer Normalisierungsregel** Werte in die folgenden Felder ein:
    
      - **Anfangsziffern**    (Optional) Geben Sie die Anfangsziffern der gewählten Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise **425** ein, wenn das Muster für gewählte Nummern gelten soll, die mit 425 beginnen.
    
      - **Länge**    Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein, und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen.
    
      - **Zu entfernende Ziffern**   (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die aus gewählten Nummern entfernt werden sollen, die Sie mit dem Muster abgleichen möchten.
    
      - **Hinzuzufügende Ziffern**    (Optional) Geben Sie Ziffern ein, die gewählten Nummern hinzugefügt werden, die Sie mit dem Muster abgleichen möchten.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise **Anfangsziffern** leer lassen, im Feld **Länge** den Wert **7** eingeben und **Genau** auswählen und in **Zu entfernende Ziffern** den Wert **0** wählen, ergibt sich in **Muster für Vergleich** der folgende reguläre Ausdruck:
    
    **^(\\d{7})$**

7.  Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:
    
      - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn das Vergleichsmuster beispielsweise **^(\\d{7})$** lautet, dann repräsentiert **$1** in der Übersetzungsregel 7-stellige gewählte Nummern.
    
      - (Optional) Geben Sie einen Wert in das Feld **Hinzuzufügende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden (z. B. **+1425** ).
    
    Wenn beispielsweise **Zu suchendes Muster** den Wert **^(\\d{7})$** als Muster für gewählte Nummern und **Übersetzungsregel** den Wert **+1425$1** als Muster für E.164-Telefonnummern enthält, normalisiert die Regel die Nummer 5550100 in +14255550100.

8.  (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

9.  (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein, und klicken Sie auf **Los** . Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

12. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

