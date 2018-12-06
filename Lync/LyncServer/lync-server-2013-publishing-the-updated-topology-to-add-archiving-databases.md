---
title: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken
TOCTitle: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204860(v=OCS.15)
ms:contentKeyID: 49293858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Nach dem Aktualisieren Ihrer Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie die Archivierung konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.

## So veröffentlichen Sie Ihre aktualisierte Topologie

1.  Melden Sie sich an einem Computer, auf dem Lync Server 2013 ausgeführt wird oder auf dem die Lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit äquivalenten Benutzerrechten).
    

    > [!NOTE]
    > Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist. Zum Veröffentlichen einer Topologie (Vorraussetzung für das Hinzufügen eines Servers zur Topologie) müssen Sie ein Konto verwenden, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist und über Vollzugriff (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Lync Server 2013-Dateispeicher verwenden möchten, damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) konfigurieren kann. Alternativ dazu können Sie ein Konto mit äquivalenten Rechten verwenden.



2.  Öffnen Sie die Topologie, die Sie im vorigen Abschnitt mithilfe von Topologie-Generator erstellt haben.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**.
    

    > [!NOTE]
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. Ausführliche Informationen zu den erforderlichen Administratorrechten und Berechtigungen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Über den Topologie-Generator können nur Datenbanken auf dedizierten SQL Server-Servern installiert werden. Datenbanken auf SQL Server-Servern, die gemeinsam mit anderen Serverkomponenten ausgeführt werden, müssen über das lokale Setup auf dem jeweiligen Computer installiert werden.



6.  Überprüfen Sie auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, ob die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    

    > [!IMPORTANT]
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung</A> in der Bereitstellungsdokumentation.


