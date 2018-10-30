---
title: Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel
TOCTitle: Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412909(v=OCS.15)
ms:contentKeyID: 49295213
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Führen Sie die folgenden Schritte aus, um eine Übersetzungsregel zu definieren, indem Sie einen Wertesatz im Tool **Übersetzungsregel erstellen** eingeben und das entsprechende Vergleichsmuster und die Übersetzungsregel durch Lync Server-Systemsteuerung generieren lassen. Alternativ können Sie manuell einen regulären Ausdruck erstellen, um das Vergleichsmuster und die Übersetzungsregel zu definieren. Ausführliche Informationen finden Sie unter [Manuelles Erstellen oder Ändern einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

## So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Führen Sie zur Definition einer Übersetzungsregel unter [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) die Anweisungen bis Schritt 10 oder unter [Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) die Anweisungen bis Schritt 9 aus.

4.  Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

5.  (Optional) Geben Sie unter **Beschreibung** eine Beschreibung der Übersetzungsregel ein, z. B. **Internationales Ferngespräch**.

6.  Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:
    
      - **Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise **+** in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).
    
      - **Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein, und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise **11** ein, und wählen Sie in der Dropdownliste die Einstellung **Mindestens**, um Nummern abzugleichen, die mindestens 11 Ziffern umfassen.
    
      - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen. Geben Sie beispielsweise **1** ein, um das **+** am Anfang der Nummer zu entfernen.
    
      - **Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen. Geben Sie beispielsweise **011** ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorstehend genannten Beispielwerte verwenden, lautet der reguläre Ausdruck im Feld **Muster für Vergleich** wie folgt:
    
    **^\\+(\\d{9}\\d+)$**
    
    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:
    
      - Einem Wert (z. B. **$1**), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert
    
      - (Optional) Ein Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können
    
    Bei Verwendung der vorstehend genannten Beispiele wird im Feld **Übersetzungsregel** der Wert **011$1** angezeigt.
    
    Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.

7.  Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8.  Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9.  Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.
    

    > [!NOTE]
    > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Manuelles Erstellen oder Ändern einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Konzepte

[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

