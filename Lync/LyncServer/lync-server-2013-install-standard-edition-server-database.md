---
title: 'Lync Server 2013: Installieren der Standard Edition-Serverdatenbank'
TOCTitle: Installieren der Standard Edition-Serverdatenbank
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398167(v=OCS.15)
ms:contentKeyID: 49293146
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren der Standard Edition-Serverdatenbank für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Das Einrichten einer Standard Edition-Server als einziger Server in der Infrastruktur, auf dem Benutzerprofile gespeichert werden, unterscheidet sich von anderen Serverinstallationen, da es in diesem Fall eine Option im **Bereitstellungs-Assistenten** gibt, die speziell für die Einrichtung des ersten Servers vorgesehen ist.

## So installieren Sie einen Standard Edition-Server

1.  Melden Sie sich bei dem Server an, auf dem Sie den Standard Edition-Server als lokaler Administrator oder über ein Domänenkonto mit gleichwertigen Berechtigungen installieren.

2.  Wenn Sie Active Directory-Domänendienste noch nicht vorbereitet haben, führen Sie zuerst diese Verfahren aus. Ausführliche Informationen hierzu finden Sie unter [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Klicken Sie im Lync Server-Bereitstellungs-Assistenten auf **Vorbereiten des ersten Standard Edition-Servers**.

4.  Klicken Sie auf der Seite **Einzelnen Standard Edition-Server vorbereiten** auf **Weiter**.

5.  Auf der Seite **Befehle ausführen** installieren Sie SQL Server 2012 Express als zentralen Verwaltungsspeicher. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen** , wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    

    > [!NOTE]
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies hängt mit der Installation der SQL Server Express zusammen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.



6.  Klicken Sie auf der Seite Lync Server-Bereitstellungs-Assistent auf **Topologie-Generator installieren** , wenn Sie die Verwaltungstools noch nicht installiert haben. Ausführliche Informationen finden Sie unter [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vergewissern Sie sich, dass neben "Vorbereiten von Active Directory", "Vorbereiten des ersten Standard Edition-Servers" und "Installieren des Topologie-Generators" grüne Häkchen angezeigt werden.

