---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat'
TOCTitle: Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398372(v=OCS.15)
ms:contentKeyID: 49294051
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-01-15_

Bevor Sie Server für beständigen Chat für Ihre Organisation bereitstellen, sollten Sie sich unbedingt mit den folgenden zentralen Fragen beschäftigen, um eine möglichst optimale Bereitstellung zu gewährleisten:

  - Wer (Benutzerprofil) soll für Server für beständigen Chat aktiviert werden? Server für beständigen Chat wird durch eine Richtlinie aktiviert, die auf globaler Ebene, auf Standortebene, auf Poolebene oder auf Benutzerebene festgelegt werden kann.

  - Wie viele Benutzer (Skalierung) sollen für Server für beständigen Chat aktiviert werden? Server für beständigen Chat unterstützt bis zu 150.000 bereitgestellte (durch Richtlinien aktivierte) Benutzer, von denen maximal 80.000 Server für beständigen Chat gleichzeitig verwenden können. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen, und ein einzelner Serverpool für beständigen Chat kann bis zu 4 aktive Server mit insgesamt 80.000 gleichzeitig verbundenen Benutzern umfassen.

  - Führen Sie eine Migration von einer früheren Version von Gruppenchatserver durch, oder stellen Sie Server für beständigen Chat zum ersten Mal bereit?

  - Welche Kompatibilitätsanforderungen bestehen? Server für beständigen Chat unterstützt die Verwendung von Kompatibilitätsrichtlinien. Der Kompatibilitätsdienst wird im Gegensatz zu früheren Bereitstellungen von Gruppenchatserver, in denen ein separater Computer erforderlich war, jetzt ebenfalls in der Front-End-Server von Server für beständigen Chat ausgeführt. Die Kompatibilität ist optional und erfordert ggf. eine Kompatibilitätsdatenbank, die zum Speichern von Kompatibilitätsdaten und -ereignissen konfiguriert werden muss. Darüber hinaus können Sie einen Adapter konfigurieren, um die Daten aus der Kompatibilitätsdatenbank in ein anderes Format (beispielsweise XML-Dateien oder Exchange-Hostingarchiv) zu konvertieren.

  - Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Mithilfe von **Kategorien** können Sie diese Grenzen ziehen und auswählen, welche Benutzer auf die Räume zugreifen können, die in den einzelnen Kategorien erstellt werden.

  - Wie soll kontrolliert werden, welche Benutzer Räume erstellen dürfen? Sie können unter Berücksichtigung Ihrer Kategorien **Ersteller** konfigurieren, die Räume erstellen dürfen. Ersteller können darüber hinaus andere Mitglieder für die laufende Verwaltung der Räume (Hinzufügen oder Entfernen von Mitgliedern) als **Chatroomanager** einsetzen. Die Grundlage hierfür ist der Bereich für **AllowedMembers/DeniedMembers**, der durch die jeweilige Kategorie festgelegt wird.

  - Wie sollen Räume erstellt werden? Server für beständigen Chat bietet eine webbasierte Funktion zum Erstellen und Verwalten von Räumen. Diese Funktion kann über den Lync 2013-Client gestartet werden. Mithilfe des Server für beständigen Chat-Software Development Kits (SDK) können Sie eine benutzerdefinierte Lösung erstellen, um Ihre Geschäftsanforderungen und -workflows zu implementieren. Außerdem können Sie auf diese Weise Server für beständigen Chat konfigurieren und Benutzer auf Ihre individuelle Lösung verweisen.

  - Welche Arten von Add-Ins möchten Sie bereitstellen? **Add-Ins** erweitern die Möglichkeiten in Räumen, indem sie den Erweiterbarkeitsbereich im Lync 2013-Client nutzen, um relevanten Kontext für den Raum bereitzustellen. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen.

  - Welche Vorkehrungen wurden bezüglich der Anforderungen an die Hochverfügbarkeit sowie der Notfallwiederherstellung getroffen? Server für beständigen Chat unterstützt SQL Server-Spiegelungen und SQL Server-Clustering für die Hochverfügbarkeit und unterstützt bis zu 8 Server (4 aktive und 4 im Standby) in einem erweiterten Pool, einschließlich SQL Server-Protokollversand für die Notfallwiederherstellung.

  - Gibt es gesetzliche Vorschriften, die eingehalten werden müssen? Wenn Ihr Unternehmen in einem Land bzw. in einer Region aktiv ist, wo Daten innerhalb des Landes aufbewahrt werden müssen, müssen Sie möglicherweise mehrere Serverpools für beständigen Chat bereitstellen, d. h. jeweils einen Pool für eine bestimmte Region oder ein bestimmtes Land. Ein Raum, eine Kategorie oder ein Add-In erstrecken sich nicht auf mehrere Pools. Diese Elemente gehören jeweils nur einem Serverpool für beständigen Chat an. Sie können die Kategorien, Add-Ins und Räume für jeden Serverpool für beständigen Chat verwalten. Benutzer können so konfiguriert werden, dass sie – in Abhängigkeit von Ihrer Gestaltung der einzelnen Kategorien – im Rahmen von AllowedMembers der Kategorie oder im Rahmen der Mitgliedschaft eines Raums auf Räume in einem oder mehreren Pools zugreifen können.
    

    > [!IMPORTANT]
    > Durch die Verwendung mehrerer Serverpools für beständigen Chat wird Ihre Skalierung nicht vergrößert. Die Anzahl der Benutzer in allen Serverpools für beständigen Chat, die gleichzeitig eine Verbindung herstellen können, ist auch weiterhin auf 80.000 begrenzt. Der primäre Grund für die Unterstützung mehrerer Serverpools für beständigen Chat ist die Unterstützung von Bedenken rund um die Einhaltung gesetzlicher Vorschriften.


