---
title: Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73801c006f7ef5487960628d0f981809cdfd2d38
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-01_

Die Server Bereitstellung für beständigen Chat kann viele gleichzeitige beständige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und erbt Einstellungen von dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zum Identifizieren von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.

<div>


> [!NOTE]  
> Obwohl viele Verwaltungsfeatures von Chatrooms in Computern mit persistent Chat (lync-Client) für den Benutzer verfügbar sind, müssen Administratoren für beständigen Chat (in der <STRONG>"cspersistentchatadministrator"</STRONG> -Rolle) die lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets verwenden, um Kategorien zu erstellen oder zu verwalten.



</div>

Administratoren für beständigen Chat verwenden lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien und zum Entwerfen des Zugriffs für Chatrooms für die Benutzer in Ihrer Organisation.

Manager für beständigen Chatrooms, die die Möglichkeit haben, einen oder mehrere Chatrooms zu verwalten, können den lync-Client verwenden, um eine Raum Verwaltungsdienst-Webanwendung zum Erstellen und Verwalten von Räumen zu starten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden). Administratoren für beständigen Chat können auch lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Räumen verwenden.

<div>


> [!NOTE]  
> Ein beständiger Chatroom kann nicht den gleichen Namen wie eine Kategorie für beständigen Chat haben.



</div>

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

<div>

## <a name="delegated-administration"></a>Delegierte Administration

Das Erstellen und Verwalten von beständigen Chatrooms ist mit der korrekten Verwendung von Kategorien wesentlich einfacher. Ein Administrator für beständigen Chat kann **AllowedMembers** und **Ersteller** für jede Kategorie definieren und kann auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Administratoren für beständigen Chat erstellen und Verwalten von Kategorien mithilfe von lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets.

Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller der Kategorie identifiziert werden, sind die einzigen Personen und Gruppen, die Räume in der Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können Sie Benutzer, OUs und Benutzergruppen aus der **AllowedMembers** -Liste der Kategorie als Chatroommanager und Mitglieder zur Verwaltung und Teilnahme am Chatroom auswählen.

Chatrooms, die in einer Kategorie erstellt werden, erfüllen die von der Kategorie erzwungenen Richtlinien und Einstellungen (z. B. wer Mitglied beim Chatroom sein kann, wer den Chatroom verwalten kann, ob Dateiuploads zulässig sind, ob Einladungen versendet werden usw.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

