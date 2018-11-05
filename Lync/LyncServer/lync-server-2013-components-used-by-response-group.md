---
title: 'Lync Server 2013: Von Reaktionsgruppen verwendete Komponenten'
TOCTitle: Von Reaktionsgruppen verwendete Komponenten
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425768(v=OCS.15)
ms:contentKeyID: 49293513
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Von Reaktionsgruppen verwendete Komponenten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Die Reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen. In diesem Abschnitt werden die Komponenten beschrieben, die die Reaktionsgruppenanwendung unterstützen.

## Reaktionsgruppenkomponenten

Die folgenden Microsoft Lync Server 2013-Komponenten unterstützen die Reaktionsgruppenanwendung:

  - **Anwendungsdienst** Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen wie z. B. Reaktionsgruppen. Der Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert.

  - **Reaktionsgruppenanwendung**   Die Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen (UC), die vom Anwendungsdienst gehostet werden. Sie wird automatisch aktiviert, wenn Sie Reaktionsgruppe bereitstellen. Die Reaktionsgruppenanwendung leitet eingehende Anrufe bei Agentgruppen weiter und platziert diese ggf. in Warteschleifen.

  - **Sprachpaket**   Ein Sprachpaket ist erforderlich, damit Text-zu-Sprache-Funktionen und die Spracherkennung unterstützt werden. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete bei der Bereitstellung von Lync Server 2013 installiert.

  - **Audiodateien**   Audiodateien werden für Nachrichten und Wartemusik verwendet.

  - **Dateispeicher**   Die Reaktionsgruppe verwendet den Dateispeicher zum Speichern von Audiodateien. Dieselbe Instanz des Dateispeichers kann von mehreren Pools für Reaktionsgruppen verwendet werden.

  - **Konfigurationstool für Reaktionsgruppen**   Das Konfigurationstool für Reaktionsgruppen ist ein webbasiertes Tool, das für die Erstellung und Verwaltung von Reaktionsgruppen verwendet wird. Das Konfigurationstool für Reaktionsgruppen ist in der Installation der Webdienste enthalten.

  - **Systemsteuerung für Microsoft Lync Server 2013**   Sie können die Lync Server-Systemsteuerung zum Einrichten und Konfigurieren von Agentgruppen und Warteschleifen für Reaktionsgruppen verwenden.

  - **Lync Server-Verwaltungsshell**   Mit den Lync Server-Verwaltungsshell-Cmdlets können sämtliche Einstellungen für eine Reaktionsgruppe konfiguriert werden.

  - **Microsoft Lync 2013**   Formelle Agents (Agents, die sich nicht bei der Gruppe anmelden müssen, um Anrufe für die Gruppe entgegenzunehmen) verwenden Lync 2013 zur An- und Abmeldung an der Gruppe. Wenn eine Agentgruppe für formelle Agents konfiguriert ist, klicken die Agents auf eine Menüoption in Lync 2013, um Internet Explorer zu öffnen und eine Webseitenkonsole zur An- und Abmeldung bei der Gruppe anzuzeigen.

  - **Webdienste**   Webdienste sind für das Konfigurationstool für Reaktionsgruppen, die An- und Abmeldekonsole für Agents, für die Lync Server-Systemsteuerung und für den Clientwebdienst der Reaktionsgruppe erforderlich.

  - **Reaktionsgruppen-Clientwebdienst**   Die Reaktionsgruppenanwendung stellt einen Clientwebdienst bereit, der von Drittanbieteranwendungen zum Abrufen von Informationen zu Agents, Agentgruppenmitgliedschaften, dem Anmeldestatus von Agents, dem Anrufstatus für Gruppen und den Gruppen verwendet werden kann, die anonyme Anrufe unterstützen. Lync 2013 und Lync 2010-Vermittlung verwenden den Clientwebdienst der Reaktionsgruppe, um die Liste der Reaktionsgruppen abzurufen, die Agents zum Tätigen anonymer Anrufe verwenden können. Der Clientwebdienst ist in der Installation der Webdienste enthalten.

