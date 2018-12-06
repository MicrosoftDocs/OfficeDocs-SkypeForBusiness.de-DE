---
title: Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat
TOCTitle: Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398988(v=OCS.15)
ms:contentKeyID: 49295653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat

 

_**Letztes Änderungsdatum des Themas:** 2013-10-01_

Von der Bereitstellung für den Server für beständigen Chat können viele gleichzeitige Beständiger Chatrooms gehostet werden. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.


> [!NOTE]
> Viele der Verwaltungsfeatures von Chatrooms sind zwar auf Computern mit Beständiger Chat ( Lync-Client) für den Benutzer verfügbar, aber Administratoren für Beständiger Chat (in der Rolle <STRONG>cspersistentchatadministrator</STRONG>) müssen zum Erstellen oder Verwalten von Kategorien die Lync Server-Systemsteuerung oder Windows PowerShell-Cmdlets verwenden.



Administratoren für Beständiger Chat verwenden die Lync Server-Systemsteuerung oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien und zum Festlegen des Zugriffs auf Chatrooms für die Benutzer in ihrer Organisation.

Chatroommanager für Beständiger Chat, die einen oder mehrere Chatrooms verwalten können, können mit dem Lync-Client eine Webanwendung für die Chatroomverwaltung starten, um Chatrooms zu erstellen und zu verwalten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden sollen). Administratoren für Beständiger Chat können auch mit der Lync Server-Systemsteuerung oder mit Windows PowerShell-Cmdlets Chatrooms erstellen und verwalten.


> [!NOTE]
> Ein Beständiger Chat-Raum darf nicht denselben Namen haben wie eine Beständiger Chat-Kategorie.



Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:

  - Deaktivieren eines Chatrooms

  - Ändern des Namens eines Chatrooms

  - Ändern der Beschreibung eines Chatrooms

  - Ändern des Chatroomtyps ("Auditorium" bzw. "Normal")

  - Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)

  - Hinzufügen oder Entfernen von Mitgliedern

  - Hinzufügen oder Entfernen von Chatroommanagern

  - Hinzufügen oder Entfernen eines Add-Ins

  - Ändern von Einstellungen wie z. B. Einladungen (je nachdem, was durch die Kategorie zulässig ist)

## Delegierte Administration

Das Erstellen und Verwalten von Beständiger Chatrooms wird durch die ordnungsgemäße Verwendung von Kategorien wesentlich vereinfacht. Ein Administrator für Beständiger Chat kann **AllowedMembers** und **Creators** für jede Kategorie sowie die Standardeinstellungen und -verhaltensweisen für Chatrooms definieren, die für alle in dieser Kategorie erstellten Chatrooms gelten. Administratoren für Beständiger Chat erstellen und verwalten Kategorien mit der Lync Server-Systemsteuerung oder mit Windows PowerShell-Cmdlets.

Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Creators der Kategorie definiert werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können sie Benutzer, Organisationseinheiten und Benutzergruppen in der Liste **AllowedMembers** der Kategorie als Chatroommanager und Mitglieder auswählen, die den Chatroom verwalten und an diesem teilnehmen.

Chatrooms, die in einer Kategorie erstellt werden, erfüllen die von der Kategorie erzwungenen Richtlinien und Einstellungen (z. B. wer Mitglied beim Chatroom sein kann, wer den Chatroom verwalten kann, ob Dateiuploads zulässig sind, ob Einladungen versendet werden usw.).

