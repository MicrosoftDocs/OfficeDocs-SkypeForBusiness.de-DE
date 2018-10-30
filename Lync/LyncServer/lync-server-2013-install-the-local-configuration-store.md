---
title: 'Lync Server 2013: Installieren des lokalen Konfigurationsspeichers'
TOCTitle: Installieren des lokalen Konfigurationsspeichers
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412874(v=OCS.15)
ms:contentKeyID: 49295157
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren des lokalen Konfigurationsspeichers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-06-27_

Vergewissern Sie sich vor dem Ausführen dieser Arbeitsschritte, dass Sie beim Server unter einem Domänenkonto angemeldet sind, das lokale Administratorrechte besitzt und Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" ist.

Um das Lync Server-Bereitstellungs-Assistent einsetzen zu können muss der lokale Konfigurationsspeicher auf einem Server vorhanden sein. Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie des zentralen Verwaltungsspeicher, der nach der lokalen Installation von SQL Server Express erstellt wird. Der zentralen Verwaltungsspeicher selbst wird zur vorhandenen SQL Server-Datenbank auf dem Standard Edition-Server oder der SQL Server Express-basierten Datenbank hinzugefügt.


> [!IMPORTANT]
> Wenn Sie das Lync Server 2013-Setup auf diesem Server noch nicht ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Installationspfad für Lync Server 2013 anzugeben. Auf diese Weise können Sie ein anderes Laufwerk als das Systemlaufwerk verwenden, sollte dies von Ihrer Organisation vorgeschrieben werden oder nicht ausreichend Speicherplatz vorhanden sein. Sie können als Installationspfad für die Lync Server-Dateien im Setup-Dialogfeld einfach ein anderes, verfügbares Laufwerk auswählen. Wenn Sie die Setupdateien, einschließlich "OCSCore.msi", in diesem Verzeichnis installieren, werden auch alle übrigen Lync Server 2013-Dateien auf diesem Laufwerk bereitgestellt.



## So installieren Sie den lokalen Konfigurationsspeicher

1.  Wechseln Sie auf dem Installationsdatenträger zu "\\setup\\amd64\\Setup.exe", und klicken Sie dann auf **OK** .

2.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ 2012 Redistributable aufgefordert werden.

3.  Klicken Sie auf der Seite **Installationsspeicherort von Lync Server 2013** auf **OK** .

4.  Lesen Sie sich auf der Seite **Endbenutzer-Lizenzvertrag** die Lizenzbedingungen durch, klicken Sie auf **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **OK** .

5.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren** .

6.  Klicken Sie auf der Seite **Lync Server 2013** neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** .

7.  Vergewissern Sie sich auf der Seite **Lokalen Konfigurationsspeicher installieren** , dass die Option **Direkt vom zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter** .

8.  Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen** .

