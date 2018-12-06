---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie'
TOCTitle: Veröffentlichen der aktualisierten Topologie
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204910(v=OCS.15)
ms:contentKeyID: 49294089
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen der aktualisierten Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Nach dem Aktualisieren Ihrer Topologie im Topologie-Generator müssen Sie die Topologie im zentraler Verwaltungsspeicher veröffentlichen, bevor Sie Server für beständigen Chat konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf allen Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind. UNRESOLVED\_TOKEN\_VAL()

## So veröffentlichen Sie eine aktualisierte Topologie

Installieren Sie zunächst die Datenbanken für Server für beständigen Chat, bevor Sie Ihre Topologie veröffentlichen. Installieren Sie die Datenbanken mit Topologie-Generator, und wählen Sie dazu **Aktion** und **Datenbank installieren** aus.

1.  Melden Sie sich auf einem Computer mit Lync Server 2013 oder mit den Lync Server-Verwaltungstools unter Verwendung eines Kontos an, das sowohl Mitglied der Gruppe **Domänen-Admins** als auch Mitglied der Gruppe **RTCUniversalServerAdmins** ist. Darüber hinaus muss dieses Konto über uneingeschränkte Berechtigungen (Schreiben, Lesen und Ändern) in dem Dateispeicher verfügen, der als Dateispeicher für Server für beständigen Chat verwendet werden soll. Dies ist erforderlich, damit die erforderlichen besitzerverwalteten Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) von Topologie-Generator konfiguriert werden können. Es ist auch möglich, ein anderes Konto mit vergleichbaren Benutzerrechten zu verwenden.

2.  Starten Sie Topologie-Generator. Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen** oder, wenn Sie die Topologie lokal gespeichert haben, **Topologie aus einer lokalen Datei öffnen** aus.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **Lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen** .

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter** .

5.  Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen** , dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen** .
    

    > [!IMPORTANT]
    > Nachdem Sie die Topologie veröffentlicht haben, müssen Sie noch die Unterstützung für Server für beständigen Chat konfigurieren, bevor Inhalte archiviert werden können.


