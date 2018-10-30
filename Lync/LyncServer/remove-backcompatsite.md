---
title: Entfernen von BackCompatSite
TOCTitle: Entfernen von BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204637(v=OCS.15)
ms:contentKeyID: 49293016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen von BackCompatSite

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Nach dem Deaktivieren aller Pools und dem Deinstallieren aller Edgeserver führen Sie den Zusammenführungs-Assistenten des Topologie-Generators aus, um **BackCompatSite** zu entfernen.

## So entfernen Sie "BackCompatSite" aus dem Topologie-Generator

1.  Öffnen Sie im Topologie-Generator eine vorhandene Bereitstellung.

2.  Klicken Sie im Menü **Aktion** auf **Topologie von Office Communications Server 2007 R2 zusammenführen**.

3.  Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

4.  Stellen Sie auf der Seite **Edge der Vorversion angeben** sicher, dass die Liste der Edgeserver leer ist, Falls die Liste nicht leer ist, entfernen Sie alle Edgeserver aus Vorversionen mithilfe der Schaltfläche **Entfernen** , und klicken Sie dann auf **Weiter** .
    
    ![Zusammenführungs-Assistent für Topologien, Edgesetup angeben (Seite)](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Zusammenführungs-Assistent für Topologien, Edgesetup angeben (Seite)")  

5.  Klicken Sie auf der Seite **Internen SIP-Port angeben** auf **Weiter**.

6.  Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter**, um mit dem Zusammenführen der Topologien zu beginnen und den Vorversionsstandort zu entfernen.

7.  Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet und klicken Sie zum Schließen des Assistenten auf **Fertig stellen**.

8.  Erweitern Sie im linken Bereich des Topologie-Generators die Option "BackCompatSite" und stellen Sie sicher, dass keine Server aufgeführt sind.

9.  Klicken Sie mit der rechten Maustaste auf **BackCompatSite** und klicken Sie dann auf **Löschen**.

10. Wählen Sie im **Topologie-Generator** den obersten Knoten **Lync Server** aus.

11. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus und klicken Sie auf **Weiter**.

12. Nach Abschluss des **Veröffentlichungs-Assistenten** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

