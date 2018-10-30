---
title: Manuelles Erstellen oder Ändern einer Übersetzungsregel
TOCTitle: Manuelles Erstellen oder Ändern einer Übersetzungsregel
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398099(v=OCS.15)
ms:contentKeyID: 49293031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Manuelles Erstellen oder Ändern einer Übersetzungsregel

 

_**Letztes Änderungsdatum des Themas:** 2012-08-06_

Führen Sie diese Schritte aus, um eine Übersetzungsregel zu definieren, indem Sie einen regulären Ausdruck für das Vergleichsmuster und die Übersetzungsregel schreiben. Alternativ können Sie im Tool **Übersetzungsregel erstellen** eine Reihe von Werten eingeben und das Vergleichsmuster und die Übersetzungsregel von der Lync Server-Systemsteuerung generieren lassen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

## So definieren Sie eine Übersetzungsregel manuell

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Führen Sie zur Definition einer Übersetzungsregel unter [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) die Anweisungen bis Schritt 10, oder unter [Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) die Anweisungen bis Schritt 9 aus.

4.  Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

5.  (Optional) Geben Sie unter **Beschreibung** eine Beschreibung der Übersetzungsregel ein, z. B. **Internationales Ferngespräch**.

6.  Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

7.  Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:
    
      - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    
      - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.
    
    Beispiel: Bei Eingabe von **^\\+(\\d{9}\\d+)$** unter **Übereinstimmung mit dem folgenden Muster** und **011$1** unter **Übersetzungsregel** übersetzt die Regel +441235551010 in 011441235551010.

8.  Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

9.  Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Konzepte

[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

