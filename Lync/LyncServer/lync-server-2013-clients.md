---
title: 'Lync Server 2013: Clients'
TOCTitle: Clients für Lync Server
ms:assetid: e143ce9b-3624-4066-942d-6c86ad99be91
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398996(v=OCS.15)
ms:contentKeyID: 49295675
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clients für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 unterstützt unterschiedliche Arten von Clientsoftware, die Sie für die Benutzer in Ihrer Organisation bereitstellen können. Hierzu zählen auf Computern installierte Clientsoftwareanwendungen, webbasierte Clients und mobile Geräte. In diesem Thema werden die Clients beschrieben, die Sie verwenden können. Einen ausführlichen Vergleich der von den Lync Server 2013-Clients bereitgestellten Features finden Sie unter [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

## Lync 2013

Lync 2013 ist der Client mit umfangreichem Funktionsspektrum für Lync Server. Die Benutzeroberfläche von Lync 2013 wurde vollständig umgestaltet und weist neue Features auf, wie Beständiger Chat (in Lync 2010 gab es einen separaten Client für Chatfunktionalität), Unterhaltung in Registerkarten, Videovorschau und Video mit mehreren Teilnehmern. Eine Zusammenfassung der Änderungen finden Sie unter [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Das Lync 2013-Clientsetup ist Bestandteil des Office-Setupprogramms auf den Installationsmedien.

## Onlinebesprechungs-Add-In für Lync 2013

Das Onlinebesprechungs-Add-In für Lync 2013 unterstützt die Besprechungsverwaltung aus dem Microsoft Outlook-Client für Messaging und Zusammenarbeit. Das Onlinebesprechungs-Add-In für Lync 2013 wird automatisch mit Lync 2013 installiert.

## Lync Web Scheduler

Lync ist ein webbasiertes Tool zum Planen und Verwalten von Besprechungen für Benutzer, die keinen Zugriff auf Microsoft Outlook haben oder ein Betriebssystem verwenden, das nicht auf Windows basiert. Mit Lync Web Scheduler können die Benutzer neue Besprechungen erstellen, vorhandene Besprechungen ändern und Einladungen mit ihrem bevorzugten E-Mail-Programm senden.

## Lync Web App

Lync Web App ist ein webbasierter Konferenzclient für Lync Server 2013-Besprechungen. In dieser Version ermöglichen die neuen Audio- und Videofunktionen in Lync Web App realistische Besprechungen für Benutzer, die keinen Lync-Client lokal installiert haben. Die Besprechungsteilnehmer haben Zugriff auf alle Features für die Zusammenarbeit und die Freigabe und auf alle Steuerelemente für Referenten in Besprechungen.

Falls Lync 2013 nicht auf dem Computer eines Benutzers installiert ist und der Benutzer auf einen Besprechungslink in einer Besprechungsanfrage klickt, wird Lync Web App geöffnet. Darüber hinaus können Sie die Seite für die Besprechungsteilnahme so konfigurieren, dass die Benutzer mithilfe früherer Versionen von Clients an Besprechungen teilnehmen können. Weitere Informationen hierzu finden Sie unter [Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.

Aufgrund der Verbesserungen bei Lync Web App ist keine aktualisierte Version von Microsoft Lync 2010-Teilnehmer für Lync Server 2013 verfügbar. Lync Web App ist der Client der Wahl für Teilnehmer außerhalb Ihrer Organisation. Mit Lync Web App, ist keine lokale Installation eines Clients erforderlich. Für die Audio-, Video- und Freigabefeatures muss jedoch bei der erstmaligen Verwendung ein Plug-In installiert werden.

## Lync 2013 Basic

Lync 2013 Basic ist ein herunterladbarer Client für Kunden, die über eine lizenzierte, lokale Lync Server 2013-Bereitstellung verfügen, und für Kunden, die einen Microsoft Office 365-Plan abonnieren, der den Lync 2013-Vollclient nicht beinhaltet. Der Lync Basic-Client enthält optimierte Funktionen für Anwesenheit, Kontakte, Chat, Lync-Besprechungen und einfaches VoIP. Zu den Features, die in Lync Basic nicht unterstützt werden, gehören Video mit mehreren Teilnehmern, OneNote-Integration, Unterstützung von VDI (Virtual Desktop Infrastructure), Qualifikationssuche, Aufzeichnung, Enterprise-VoIP und erweiterte Anrufabwicklung (z. B. Anrufweiterleitung und Teamanruf). Ausführliche Informationen finden Sie unter [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

## Lync-Windows Store-App

Die Windows Store-App für Lync ist eine für die Toucheingabe optimierte Lync-App, die speziell für Windows 8.1, Windows 8 und Windows RT entworfen wurden. Benutzer können die App aus dem Windows Store herunterladen, indem Sie nach "Lync" suchen. Weitere Informationen finden Sie unter [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md), [Anforderungen für Lync Windows Store-App](lync-server-2013-lync-windows-store-app-requirements.md) und [Bereitstellen der Lync-Windows Store-App](lync-server-2013-deploying-lync-windows-store-app.md).

## Lync 2013 für mobile Geräte

Mobile Lync 2013-Apps enthalten nun neben den Funktionen für Kontakte, Anwesenheit und Chat auch Funktionen, die Voice over IP (VoIP) und Video over IP ermöglichen. Mobile Benutzer können mit anderen per Chat, Sprachanruf oder Videoanruf entweder über eine WLAN- oder eine Mobilfunkverbindung kommunizieren. Mit einem einzigen Klick auf den Besprechungslink in einem Kalenderelement können mobile Benutzer an Sprach- und Videobesprechungen teilnehmen. Weitere Informationen zu mobilen Lync 2013-Apps finden Sie unter [Planung für mobile Clients](lync-server-2013-planning-for-mobile-clients.md).

## Unterstützte Clients aus vorherigen Versionen

Lync Server 2013 unterstützt die folgenden Clients aus früheren Serverversionen. Sie können bestimmte vorherige Clients Benutzern zur Verfügung stellen, wenn sie an Besprechungen teilnehmen. Ausführliche Informationen finden Sie unter [Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.

  - **Lync 2010**    Lync 2010 stellt eine umfassende Desktopdarstellung bereit, einschließlich Chat, erweiterter Anwesenheit, Sprache, Video, Freigabe und Telefonie. Die neuen in Lync Server 2013 eingeführten Features stehen jedoch erst zur Verfügung, wenn für den Client des Benutzers ein Upgrade auf Lync 2013 vorgenommen wurde.

  - **Lync 2010 Mobile**    Lync Server 2013 unterstützt alle mobilen Apps von Microsoft Lync 2010 Mobile. Microsoft Lync 2010 Mobile stellt Chatfunktionen, erweiterte Anwesenheitsinformationen und Telefoniefunktionen für Benutzer in Ihrer Organisation bereit, die über ein Smartphone oder ein Mobiltelefon mit der Professional Edition von Windows Mobile Verbindungen herstellen. Sie können Ihre Benutzer auffordern, Microsoft Lync 2010 Mobile zu installieren, indem Sie die Benutzer von ihren Telefonen aus auf den App Marketplace verweisen. Ausführliche Informationen finden Sie im Thema "Planung für mobile Clients" in der Lync Server 2010-Dokumentation unter <http://go.microsoft.com/fwlink/?linkid=235955>.

  - **Lync Phone Edition**   Die Lync Phone Edition-Software für intelligente IP-Telefone (z. B. über USB angeschlossene Telefone) wurde für Lync Server 2013 nicht aktualisiert. Lync Phone Edition wird weiterhin unterstützt und ermöglicht das Tätigen und Empfangen von Anrufen, erweiterte Anwesenheitsfunktionen sowie Clientaudiofunktionen für Konferenzen.

  - **Lync 2010-Vermittlung**    Microsoft Lync 2010-Vermittlung ist ein integriertes Programm für die Anrufverwaltung, mit dem ein Empfangsmitarbeiter über eine schnelle Anrufabwicklung, Chat und Routing auf dem Bildschirm viele Unterhaltungen gleichzeitig verwalten kann.

## Siehe auch

#### Konzepte

[Clientinteroperabilität in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md)

