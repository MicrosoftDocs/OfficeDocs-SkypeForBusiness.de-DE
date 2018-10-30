---
title: Von der Gruppenanrufannahme verwendete Komponenten
TOCTitle: Von der Gruppenanrufannahme verwendete Komponenten
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945625(v=OCS.15)
ms:contentKeyID: 52056354
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Von der Gruppenanrufannahme verwendete Komponenten

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Die Gruppenanrufannahme wird bei einer Bereitstellung von Enterprise-VoIP und der Anwendung zum Parken von Anrufen automatisch bereitgestellt. Sie aktivieren die Gruppenanrufannahme, indem Sie die Orbittabelle für das Parken von Anrufen mit separaten Nummernbereichen konfigurieren, die als Gruppennummern für die Anrufannahme fungieren. Anschließend weisen Sie Benutzer an Anrufannahmegruppen zu und aktivieren diese Benutzer für die Gruppenanrufannahme. Folgende Lync Server-Komponenten unterstützen die Gruppenanrufannahme:

  - **Anwendungsdienst**   Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen wie z. B. die Anwendung zum Parken von Anrufen. Der Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert.

  - **Anwendung zum Parken von Anrufen**   Die Anwendung zum Parken von Anrufen ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden. Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen.

  - **Lync Server-Verwaltungsshell**   Sie können die Lync Server-Verwaltungsshell zum Verwalten von Gruppen für die Gruppenanrufannahme verwenden.

  - **SEFAUtil-Resource Kit-Tool**   Sie verwenden SEFAUtil (Secondary Extension Feature Activation Utility) zum Zuweisen von Benutzern an einer Anrufannahmegruppe sowie zum Aktivieren bzw. Deaktivieren der Anrufannahme für Benutzer.

