---
title: Migrieren von Einwahlnummern
TOCTitle: Migrieren von Einwahlnummern
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204898(v=OCS.15)
ms:contentKeyID: 49294053
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Einwahlnummern

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Das Migrieren von Einwahlnummern erfordert zwei Schritte: das Ausführen des Cmdlets **Import-CsLegacyConfiguration** (zuvor abgeschlossen in [Importieren von Richtlinien und Einstellungen](import-policies-and-settings.md)), um Wähleinstellungen und andere Einwahlnummerneinstellungen zu migrieren, sowie das Ausführen des Cmdlets **Move-CsApplicationEndpoint** , um die Kontaktobjekte zu migrieren.

## So migrieren Sie Zugriffsnummern für die Einwahl

1.  Öffnen Sie das Verwaltungstool von Office Communications Server 2007 R2.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten für die Gesamtstruktur, klicken Sie auf **Eigenschaften** und dann auf **Eigenschaften der Konferenzzentrale** .

3.  Klicken Sie auf der Registerkarte **Zugriffstelefonnummern** auf **Verarbeitet vom Pool** , um die Zugriffstelefonnummern nach dem zugeordneten Pool zu ordnen und alle Zugriffnummern für den zu migrierenden Pool zu identifizieren.

4.  Zum Identifizieren der SIP-URI für jede Zugriffsnummer doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld **Zum Identifizieren der SIP-URI für jede Zugriffsnummer doppelklicken Sie auf die Zugriffsnummer, um das Dialogfeld** zu öffnen, und sehen Sie dann unter **SIP-URI** nach.

5.  Öffnen Sie die Lync Server-Verwaltungsshell.

6.  Zum Verschieben aller Einwahlnummern in einen auf Lync Server 2013 gehosteten Pool führen Sie Folgendes aus:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Vergewissern Sie sich, dass im Office Communications Server 2007 R2-Verwaltungstool auf der Registerkarte **Zugriffstelefonnummern** keine Zugriffsnummern für die Einwahl mehr für den Office Communications Server 2007 R2-Pool verzeichnet sind, von dem Sie die Migration durchführen.

