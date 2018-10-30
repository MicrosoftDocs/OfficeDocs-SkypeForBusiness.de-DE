---
title: Verwenden der Lync Server 2010 Management Packs in einem Szenario mit Koexistenz
TOCTitle: Verwenden der Lync Server 2010 Management Packs in einem Szenario mit Koexistenz
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205078(v=OCS.15)
ms:contentKeyID: 49294680
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden der Lync Server 2010 Management Packs in einem Szenario mit Koexistenz

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Viele Kunden entscheiden sich für ein Rolloutprogramm in ihren Unternehmen, bei den die Benutzer nach und nach von Microsoft Lync Server 2010 zu Lync Server 2013 migriert werden. Die Administratoren in diesen Unternehmen übernehmen die Überwachung beider Versionen von Lync Server, um sicherzustellen, dass allen Endbenutzern die bestmöglichen Kommunikationsmöglichkeiten zur Verfügung stehen. Das Lync Server 2013 Management Pack unterstützt für dieses Szenario einen parallelen Migrationspfad mit dem Lync Server 2010 Management Pack.

In Lync Server 2010, Lync Server wurden Computer über das Topologiedokument erkannt, das im zentralen Verwaltungsspeicher gespeichert ist. In dieser Konfiguration würde ein einziger Computer über das Vorhandensein all der anderen Lync Server-Computer berichten.

Die Management Packs für Lync Server 2013 verwenden nun die Ermittlung auf Computerebene anstatt des zentralen Ermittlungsmechanismus, der in Lync Server 2010 verwendet wurde. Das bedeutet, dass sich jeder System Center-Agent im Prinzip selbst ermittelt und sein Vorhandensein dem System Center Operations Manager berichtet. Bei der Verwendung der Ermittlung auf Computerebene wird die Verwaltung Ihrer System Center-Infrastruktur vereinfacht, und es wird auch ermöglicht, dass verschiedene Versionen der Lync Server Management Packs (z. B. Management Packs für Lync Server 2010 und Management Packs für Lync Server 2013) nebeneinander verwendet werden können.

Zur Unterstützung dieser Migration müssen Sie zuerst Ihre bestehende Lync Server 2010-Überwachung aktualisieren, um Lücken in der Abdeckung zu verhindern. Wählen sie dafür einen bestehenden Lync Server 2010-Computer aus, um das zentrale Ermittlungsskript für die Lync Server 2010 vor der Aktualisierung Ihr zentraler Verwaltungsspeicher in Lync Server 2013 bereitzustellen. Dies ist ein Prozess in vier Schritten:

1.  Aktualisieren Sie die Lync Server 2010 Management Packs auf das kumulative Update 7.

2.  Weisen Sie einen Lync Server 2010-Computer an, das zentrale Ermittlungsskript auszuführen.

3.  Setzen Sie den zentralen Ermittlungskandidaten im Microsoft Lync Server 2010 Management Pack außer Kraft.

4.  Stellen Sie sicher, dass der neue zentrale Ermittlungskandidat ermittelt wurde.

## Anweisen eines Lync Server 2010-Computer zum Ausführen eines zentralen Ermittlungsskripts

Zum Benennen des Servers für einen nicht zentralen Verwaltungsspeicher (z. B. ein Lync Server-Front-End-Server) zum Verarbeiten zentraler Ermittlungen müssen Sie den folgenden Registrierungsschlüssel auf dem Server für den nicht zentralen Verwaltungsspeicher erstellen:

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

Sie können diesen Registrierungsschlüssel erstellen, indem Sie das folgende Verfahren durchführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE**, erweitern Sie dann **SOFTWARE**, erweitern Sie **Microsoft**, und erweitern Sie anschließend **Real-Time Communications**.

4.  Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie dann auf **Neu**, und klicken Sie anschließend auf **Schlüssel**. Wenn der Schlüssel **Status** nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Real-Time Communications**, zeigen auf **Neu**, und klicken Sie dann auf **Schlüssel**. Wenn der neue Schlüssel erstellt wurde, geben Sie "Status" ein, und drücken Sie dann die EINGABETASTE.
    
    Geben Sie **CentralDiscoveryCandidate** ein, nachdem der neue Schlüssel erstellt wurde, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.

Es kann einige Stunden dauern, bis diese Änderung vom Computer übernommen wurde. Damit die Änderungen sofort wirksam werden, sollte der Health Agent-Dienst beendet und dann erneut gestartet werden. Führen Sie die folgenden Schritte auf dem Lync Server 2010-Computer aus, um den Health Agent-Dienst erneut zu starten:

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

## Außer Kraft setzen des zentralen Ermittlungskandidaten im Lync Server 2010 Management Pack

Nachdem ein Lync Server 2010-Computer angewiesen wurde, Berichte über Lync Server 2010-Computer zu erstellen, müssen Sie die Informationen über diese Änderung dem Lync Server 2010 Management Pack weitergeben. Dafür müssen Sie im Management Pack eine Außerkraftsetzung erstellen. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie in der Operations Manager-Konsole auf **Konfiguration**.

2.  Erweitern Sie in der Registerkarte "Konfiguration" die Option **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen** und anschließend auf **Bereiche**.

3.  Wählen Sie im Dialogfeld **Management Pack-Objekte in Bereiche einteilen** das Element mit dem Ziel-**LS-Ermittlungskandidat** aus, und klicken Sie dann auf **OK**. Beachten Sie, dass der LS-Ermittlungskandidat nur angezeigt wird, wenn das Lync Server 2010 Management Pack installiert wurde.

4.  Klicken Sie mit der rechten Maustaste in der Operations Manager-Konsole auf **LS-Ermittlungskandidat**, zeigen Sie auf **Außerkraftsetzungen**, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie anschließend auf **Für alle Objekte der Klasse: LS-Ermittlungskandidat**.

5.  Aktivieren Sie im Dialogfeld **Außerkraftsetzungseigenschaften** das Kontrollkästchen **Außerkraftsetzung** neben dem Parameter **Central Discovery WatcherNode Fqdn**. Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Lync Server 2010-Computers in die Felder **Außerkraftsetzungswert** und **Gültiger Wert** ein. Aktivieren Sie das Kontrollkästchen **Erzwungen**, und klicken Sie auf **OK**.

Nachdem die Außerkraftsetzung erstellt wurde, müssen Sie den Integritätsdienst auf dem Stammverwaltungsserver neu starten. Führen Sie die folgenden Schritte auf dem Stammverwaltungsserver aus, um den Integritätsdienst neu zu starten:

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

## So wird sichergestellt, dass der neue zentrale Ermittlungskandidat ermittelt wurde

Als letzter Schritt vor der Aktualisierung des zentralen Verwaltungsspeichers muss sichergestellt werden, dass der neue zentrale Ermittlungskandidat vom Lync Server 2010 Management Pack ermittelt wurde. Öffnen Sie dafür die Operations Manager-Konsole, und klicken Sie auf "Überwachung". Erweitern Sie in der Registerkarte "Überwachung" die Option **Microsoft Lync Server 2010 Health**, erweitern Sie dann **Topologieerkennung**, und klicken Sie dann auf **Ansicht Ermittlungsstatus**. Stellen Sie sicher, dass eine Zeile in der Anzeige über einen **Pfad** verfügt, der den vollqualifizierten Domänennamen des zentralen Ermittlungskandidaten auflistet. Es sollte auch sichergestellt werden, dass als Computerstatus **Fehlerfrei** angezeigt wird.

