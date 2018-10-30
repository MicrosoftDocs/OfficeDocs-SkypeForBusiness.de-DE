---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Normalisierungsregel'
TOCTitle: Manuelles Erstellen oder Ändern einer Normalisierungsregel
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413074(v=OCS.15)
ms:contentKeyID: 49295997
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Führen Sie die folgenden Schritte aus, um eine Normalisierungsregel manuell zu erstellen oder zu ändern. Informationen zum Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel in der Lync Server-Systemsteuerung finden Sie unter [Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

## So definieren Sie eine Normalisierungsregel manuell

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) oder [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) durch.

4.  Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (weisen Sie der Normalisierungsregel beispielsweise den Namen **5StellenDurchwahl** zu).

5.  (Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise "Übersetzt 5-stellige Durchwahlnummern").

6.  Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten** .

7.  Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:
    
      - Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.
    
      - Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.
    
    Beispiel: Bei Eingabe von **^(\\d{7})$** in **Dieses Muster abgleichen** und **+1425$1** in **Übersetzungsregel** übersetzt die Regel 5550100 in +14255550100.

8.  (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl** .

9.  (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein, und klicken Sie auf **Los** . Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in Lync Server 2013</A>.



10. Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.

11. Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.

12. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Weitere Ressourcen

[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)

