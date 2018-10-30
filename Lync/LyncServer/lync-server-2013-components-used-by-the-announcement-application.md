---
title: 'Lync Server 2013: Von der Ankündigungsanwendung verwendete Komponenten'
TOCTitle: Von der Ankündigungsanwendung verwendete Komponenten
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398608(v=OCS.15)
ms:contentKeyID: 49294501
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Von der Ankündigungsanwendung in Lync Server 2013 verwendete Komponenten

 

_**Letztes Änderungsdatum des Themas:** 2012-09-13_

In Lync Server 2013 ist die Ansageanwendung eine Komponente der Reaktionsgruppenanwendung. Bei der Bereitstellung von Enterprise-VoIP wird die Ansageanwendung automatisch mit der Reaktionsgruppenanwendung installiert und aktiviert. In diesem Abschnitt werden die Komponenten beschrieben, die die Ansageanwendung unterstützen.

## Komponenten der Ankündigungsanwendung

Die folgenden Lync Server-Komponenten unterstützen die Ansageanwendung:

  - **Anwendungsdienst**   Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen. Der Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert.

  - **Reaktionsgruppenanwendung**   Die Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen (UC), die vom Anwendungsdienst gehostet werden. Wenn ein Bereich nicht zugewiesener Rufnummern für das Routing an eine Ansage konfiguriert ist, wird die Reaktionsgruppenanwendung zum Weiterleiten der Anrufe an diese Rufnummer benötigt. (Die Reaktionsgruppenanwendung ist nicht erforderlich, wenn sämtliche Bereiche für die Weiterleitung an Exchange UM (Unified Messaging) konfiguriert sind.)

  - **Audiodateien**   Audiodateien werden für die Ansagen verwendet.

  - **Dateispeicher**   Die Ansageanwendung verwendet den Dateispeicher zum Speichern von Audiodateien.

  - **Lync Server-Systemsteuerung**   Die Lync Server-Systemsteuerung kann zum Konfigurieren der Tabelle nicht zugewiesener Nummern verwendet werden.

  - **Lync Server-Verwaltungsshell**   Die Cmdlets der Lync Server-Verwaltungsshell können zum Konfigurieren von Ansageeinstellungen und der Tabelle nicht zugewiesener Nummern verwendet werden.

