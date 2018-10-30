---
title: Anzeigen von Berichten in Best Practices Analyzer
TOCTitle: Anzeigen von Berichten in Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg607690(v=OCS.15)
ms:contentKeyID: 49294377
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Berichten in Best Practices Analyzer

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn Sie Best Practices Analyzer zur Überprüfung Ihrer Umgebung verwenden, geben Sie einen Namen für die Überprüfung an. Nach Abschluss der Überprüfung speichert Best Practices Analyzer die Überprüfungsergebnisse in Berichten und speichert diese Berichte unter dem Namen der Überprüfung. Sobald die Überprüfung abgeschlossen ist, können Sie die erstellten Berichte anzeigen, indem Sie direkt auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen** klicken. Sie können die Berichte für diese oder frühere Überprüfungen auch zu einem späteren Zeitpunkt anzeigen. Sie können die Berichte auf dem lokalen Computer anzeigen, auf dem die Überprüfung erfolgt ist, die Überprüfungsergebnisse von einem anderen Computer importieren oder die Überprüfungsergebnisse exportieren, um sie auf einem Computer anzuzeigen, auf dem Best Practices Analyzer installiert ist.

Die Überprüfungsergebnisse werden in den folgenden Arten von Berichten dargestellt:

  - Listenberichte

  - Strukturberichte

  - Sonstige Berichte

Diese Berichte umfassen Fehler, Warnungen und andere Informationen. Ausführliche Informationen zu den einzelnen Berichtstypen und -problemen finden Sie im Thema [Grundlegendes zu den von Best Practices Analyzer erstellten Berichten](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Verwenden Sie das folgende Verfahren, um die Überprüfungsergebnisse anzuzeigen, die zuvor mit Best Practices Analyzer erstellt wurden.

## So zeigen Sie Berichte aus einer früheren Überprüfung an

1.  Melden Sie sich auf einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied des Kontos für lokale Benutzer ist.
    

    > [!NOTE]
    > Sie können zwar die Ergebnisse einer Überprüfung anzeigen, wenn Sie ein Konto verwenden, das Mitglied der lokalen Administratorengruppe ist; Sie können jedoch nur eine Überprüfung ausführen, wenn Sie über die erforderlichen Benutzerrechte und Berechtigungen verfügen. Ausführliche informationen finden Sie unter <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Voraussetzungen hinsichtlich Gruppenmitgliedschaften und Benutzerberechtigungen für Best Practices Analyzer</A>.



2.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, und klicken Sie dann auf **Microsoft Lync Server 2013** und anschließend auf **Best Practices Analyzer**.

3.  Klicken Sie im Willkommensbildschirm auf **Anzuzeigende Überprüfungsergebnisse auswählen**.

4.  Führen Sie auf der Seite **Bewährte Methoden-Überprüfung zum Anzeigen auswählen** einen der folgenden Schritte aus:
    
      - Wenn Sie Berichte aus der Liste der lokal gespeicherten Überprüfungsergebnisse anzeigen möchten, klicken Sie auf den Namen der Überprüfung, und klicken Sie dann auf **Bericht für diese Überprüfung anzeigen**.
        

        > [!NOTE]
        > Von Best Practices Analyzer wird die Liste der lokalen Dateien aus dem Ordner „<EM>&lt;systemDrive&gt;</EM>\Dokumente und Einstellungen\\<EM>&lt;Benutzer&gt;</EM>\Application Data\Microsoft\RtcBPA“ erstellt.

    
      - Wenn Sie Berichte zu Ergebnissen einer Überprüfung anzeigen möchten, die sich an einem anderen Speicherort befinden, klicken Sie auf **Überprüfung importieren**, suchen Sie nach der Datei, in der die Überprüfungsergebnisse enthalten sind, und klicken Sie dann auf **Öffnen**.
        

        > [!NOTE]
        > Wenn die Version von Best Practices Analyzer auf diesem Computer nicht mit der Version übereinstimmt, die verwendet wurde, um die Daten in der importierten Datei zu erfassen, wird die Datei von dem Tool auf Ihrem Computer möglicherweise nach dem Import erneut analysiert.



5.  Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:
    
      - Wenn Sie Berichte in einer Liste anzeigen möchten, die nach Serverkomponenten angeordnet ist, klicken Sie auf **Berichte auflisten**, und klicken Sie dann entweder auf die Registerkarte **Alle Probleme** oder auf **Informationselemente**.
    
      - Wenn Sie Berichte als hierarchische Liste anzeigen möchten, die nach Ergebnistypen angeordnet ist, klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **Detaillierte Ansicht** oder auf **Zusammenfassungsansicht**.
    
      - Wenn Sie sonstige Berichte anzeigen möchten, klicken Sie auf **Sonstige Berichte**.
    

    > [!NOTE]
    > Ausführliche Informationen zu den Best Practices Analyzer-Berichten und den darin ermittelten Problemen finden Sie in den Abschnitten <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Anzeigen und Verwenden von Berichten, die von Best Practices Analyzer erstellt wurden</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analysieren und Beheben von Problemen, die von Best Practices Analyzer erkannt wurden</A>.


