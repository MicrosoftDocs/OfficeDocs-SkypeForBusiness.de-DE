---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
TOCTitle: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49890925
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verbinden des Pilotpools mit Edgeservern der Vorversion

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Nach der Bereitstellung von Lync Server 2013 müssen Sie eine Partnerverbundroute für Ihren Standort konfigurieren. Wenn Sie die Partnerverbundroute nutzen möchten, die von Lync Server 2010 verwendet wird, müssen Sie Lync Server 2013 entsprechend konfigurieren.

Damit der Lync Server 2013-Standort den Director und Edgeserver der Lync Server 2010-Bereitstellung verwenden kann, ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu.

## So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1.  Öffnen Sie den **Topologie-Generator**.

2.  Wählen Sie Ihren Standort aus, der sich direkt unterhalb des **Lync Server**-Knotens befindet.

3.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten** .

4.  Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.

5.  Klicken Sie unter **Zuweisung der Partnerverbundroute des Standorts** auf **SIP-Partnerverbund aktivieren** , und wählen Sie dann den Lync Server 2010-Director oder den Lync Server 2010-Edgeserver aus, falls kein Direktor aufgelistet ist.
    
    ![Eigenschaften bearbeiten, Partnerverbundroute (Seite)](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Eigenschaften bearbeiten, Partnerverbundroute (Seite)")  

6.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

7.  Navigieren Sie im Topologie-Generator im Knoten Lync Server 2013 zu **Standard Edition-Server** oder **Enterprise Edition-Front-End-Pools** , klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten** .

8.  Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)** .

9.  Wählen Sie in der Liste den Edgeserver der Vorversion aus.
    
    ![Dialogfeld zum Bearbeiten von Eigenschaften, Legacy-Edge auswählen](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Dialogfeld zum Bearbeiten von Eigenschaften, Legacy-Edge auswählen")  

10. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

11. Wählen Sie im Topologie-Generator den obersten Knoten aus, **Lync Server**.

12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und klicken Sie dann auf **Weiter** .

13. Klicken Sie nach Abschluss des Assistenten für die Veröffentlichung auf **Fertig stellen** .

