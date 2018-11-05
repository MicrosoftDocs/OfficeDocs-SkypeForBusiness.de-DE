---
title: Verbinden des Pilotpools mit Edgeservern der Vorversionsumgebung
TOCTitle: Verbinden des Pilotpools mit Edgeservern der Vorversionsumgebung
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205136(v=OCS.15)
ms:contentKeyID: 49294918
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verbinden des Pilotpools mit Edgeservern der Vorversionsumgebung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Nach der Bereitstellung von Lync Server 2013 ist für diesen Standort keine Partnerverbundroute konfiguriert. Wenn Sie die Partnerverbundroute nutzen möchten, die von Office Communications Server 2007 R2 verwendet wird, müssen Sie Lync Server 2013 entsprechend konfigurieren.

Damit der Lync Server 2013-Standort den Director und den Edge Server von BackCompatSite verwenden kann, ordnen Sie den Edgepool der Vorgängerversion mit dem Topologie-Generator zu.

## So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1.  Öffnen Sie den Pilotpool im Topologie-Generator.

2.  Wählen Sie Ihren Lync Server 2013-Standort aus.

3.  Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten** .

4.  Klicken Sie unter **Zuweisung der Partnerverbundroute des Standorts** auf **SIP-Partnerverbund aktivieren** und wählen Sie dann den Office Communications Server 2007 R2-Director oder den Office Communications Server 2007 R2-Edgeserver aus, falls kein Direktor aufgelistet ist.
    
    ![Eigenschaften bearbeiten (Dialogfeld), Partnerverbundroute (Seite)](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Eigenschaften bearbeiten (Dialogfeld), Partnerverbundroute (Seite)")  

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

6.  Navigieren Sie im Topologie-Generator im Knoten Lync Server 2013 zu **Standard Edition-Server** oder **Enterprise Edition-Front-End-Pools** , klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten** .

7.  Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)** .

8.  Wählen Sie in der Liste die Edgeserverschnittstelle für BackCompatSite aus.
    
    ![Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)")  

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

10. Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

11. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und klicken Sie dann auf **Weiter** .

12. Klicken Sie nach Abschluss des Assistenten für die Veröffentlichung auf **Fertig stellen** .

