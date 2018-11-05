---
title: Verbinden einer Survivable Branch Appliance
TOCTitle: Verbinden einer Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49891041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verbinden einer Survivable Branch Appliance

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Jede Survivable Branch Appliance (SBA) ist einem Front-End-Pool zugeordnet, der als Sicherungsregistrierung für die SBA fungiert. Wird der Front-End-Pool zu Lync Server 2013 migriert, muss die Zuordnung der SBA zum Lync Server 2010-Front-End-Pool aufgehoben werden, während der Pool geupgradet wird. Sobald der Pool zu Lync Server 2013 migriert worden ist, kann die SBA dem geupgradeten Front-End-Pool wieder zugeordnet werden. Dazu muss die SBA aus der Lync Server 2010-Topologie der Vorgängerversion im Topologie-Generator gelöscht und dann der Lync Server 2013-Topologie hinzugefügt werden. Benutzer, die auf der Lync Server 2010-SBA der Vorgängerversion verwaltet werden, müssen zuerst in einen anderen Front-End-Pool verschoben werden, bevor die SBA aus der Topologie entfernt wird. Sobald die SBA der Lync Server 2013-Topologie hinzugefügt worden ist, können diese Benutzer wieder auf die SBA zurück verschoben werden. Diese Schritte werden im Folgenden zusammengefasst:

1.  Verschieben der Zweigstellenbenutzer, die auf der Lync Server 2010-SBA der Vorgängerversion verwaltet werden, in einen anderen Front-End-Pool.

2.  Entfernen der SBA aus der Lync Server 2010-Topologie der Vorgängerversion und Aufheben der Zuordnung des vorhandenen Front-End-Pools als Sicherungsregistrierung.

3.  Hinzufügen der SBA zur Lync Server 2013-Topologie und Konfigurieren dieses neuen Front-End-Pools als Sicherungsregistrierung.

4.  Verschieben der Zweigstellenbenutzer auf die neue Lync Server 2013-SBA.

**Hinzufügen einer Lync Server 2010-SBA-Zweigniederlassung zu einer Topologie**

1.  Öffnen Sie den **Topologie-Generator**.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Zweigniederlassungen**, und klicken Sie dann auf **Neue Zweigniederlassung**.

3.  Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** auf **Name**, und geben Sie den Namen für die Zweigniederlassung ein.

4.  (Optional) Klicken Sie auf **Beschreibung** und geben Sie eine aussagekräftige Beschreibung für die Zweigniederlassung ein.

5.  Klicken Sie auf **Weiter**.

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neue Zweigniederlassung definieren** einen der folgenden Schritte aus:
    
    1.  Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich die Zweigniederlassung befindet.
    
    2.  Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich die Zweigniederlassung befindet.
    
    3.  Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich die Zweigniederlassung befindet.

7.  Klicken Sie auf **Weiter** und führen Sie einen der folgenden Schritte aus:
    
    1.  Wenn Sie eine Lync 2010 Survivable Branch Appliance oder einen Survivable Branch Server verwenden, deaktivieren Sie unbedingt die Option **Assistent für neue Survivable Branch Appliance oder neuen Survivable Branch Server öffnen, wenn dieser Assistent geschlossen wird**. Klicken Sie dann auf **Fertig stellen**.

8.  So ordnen Sie die Lync Server 2010-SBA der Vorgängerversion dem Lync Server 2013-Front-End-Pool zu:
    
    1.  Erweitern Sie die zuvor erstellte Zweigniederlassung.
    
    2.  Klicken Sie mit der rechten Maustaste auf **Lync Server 2010**, und klicken Sie dann auf **Neu**.
    
    3.  Klicken Sie auf **Survivable Branch Appliance…**

9.  Befolgen Sie die Anweisungen im nun geöffneten Assistenten. Informationen zu den Elementen im Assistenten finden Sie unter [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    

    > [!NOTE]
    > Eine Lync Server 2010-Survivable Branch Appliance kann nur einem Lync Server 2010-Überwachungsspeicher zugeordnet werden.



10. Wenn Sie an diesem Standort keine Survivable Branch Appliance bzw. keinen Survivable Branch Server verwenden, deaktivieren Sie das Kontrollkästchen **Assistent für neue Survivable Branch Appliance oder neuen Survivable Branch Server öffnen, wenn dieser Assistent geschlossen wird**, und klicken Sie anschließend auf **Fertig stellen**.

11. Wiederholen Sie die oben beschriebenen Schritte für jede Zweigniederlassung, die zur Topologie hinzugefügt werden soll.

