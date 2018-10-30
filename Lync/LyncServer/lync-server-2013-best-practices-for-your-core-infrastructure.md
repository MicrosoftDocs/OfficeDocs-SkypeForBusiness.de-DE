---
title: Bewährte Methoden für Ihre Kerninfrastruktur in Lync Server 2013
TOCTitle: Bewährte Methoden für Ihre Kerninfrastruktur in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518328(v=OCS.15)
ms:contentKeyID: 60476343
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bewährte Methoden für Ihre Kerninfrastruktur in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System über Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten entwickelt. Von diesen Verfahren profitiert nicht nur Ihre Microsoft Lync Server 2013-Infrastruktur, sondern Ihr gesamtes Netzwerk. Falls Sie diese Verfahren nicht implementiert haben, empfehlen wir Ihnen, dies vor der Bereitstellung von Lync Server 2013 zu tun.

Um die Server in Ihrer Lync Server 2013-Bereitstellung vor versehentlichen oder absichtlichen Schäden zu schützen, die zu Ausfallzeiten führen könnten, treffen Sie die folgenden Vorsichtsmaßnahmen:

  - Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Mit einem Abonnement für den Microsoft Security Notification Service können Sie sicherstellen, dass Sie sofort über Sicherheitsbulletinveröffentlichungen für alle Microsoft-Produkte benachrichtigt werden. Um ein Abonnement einzurichten, öffnen Sie die Microsoft Technical Security Notifications-Website unter [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).

  - Achten Sie darauf, dass Zugriffsrechte ordnungsgemäß eingerichtet sind.

  - Stellen Sie Ihre Server in einer physischen Umgebung auf, die einen nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software mit den neuesten Virussignaturdateien auf dem neuesten Stand. Verwenden Sie die Funktion für automatische Updates Ihrer Antivirenanwendung, um die Virussignaturen aktuell zu halten.

  - Wir empfehlen die Deaktivierung von nicht erforderlichen Windows Server-Betriebssystemdiensten auf den Computern, auf denen Sie Lync Server 2013 installieren.

  - Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten gespeichert sind, mit einem Verschlüsselungssystem für das gesamte Volume, es sei denn, Sie können eine beständige und vollständige Kontrolle der Server, vollkommene physische Isolation und das ordnungsgemäße und sichere Außerbetriebsetzen von ausgetauschten oder ausgefallenen Festplattenlaufwerken sicherstellen.

  - Deaktivieren Sie alle externen Ports für den direkten Speicherzugriff des Servers, es sei denn, Sie können eine sehr enge Kontrolle des physischen Zugriffs auf die Server sicherstellen. Angriffe auf der Basis von direktem Speicher, die realtiv einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel offenlegen.

