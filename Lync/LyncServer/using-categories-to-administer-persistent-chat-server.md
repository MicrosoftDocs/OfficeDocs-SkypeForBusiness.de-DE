---
title: Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-01_

Ihre beständige Chat Server-Bereitstellung kann viele gleichzeitig beständige Chatrooms hosten. Chatrooms können in Kategoriegruppen auf dem Server angeordnet werden. Jeder Chatroom gehört einer Kategorie an und übernimmt die Einstellungen dieser Kategorie. Diese Anordnung ergibt eine hilfreiche Struktur zur Identifikation von Konversationen basierend auf ihrem geschäftlichen Anlass und ermöglicht die delegierte Administration und eine einfachere Verwaltung.

<div>


> [!NOTE]  
> Obwohl viele Verwaltungsfeatures von Chatrooms in Computern, auf denen persistenter Chat (lync-Client) ausgeführt wird, für den Benutzer verfügbar sind, müssen beständige chatadministratoren (in der Rolle <STRONG>cspersistentchatadministrator</STRONG> ) die lync Server-Systemsteuerung oder Windows PowerShell-Cmdlets verwenden, um Kategorien zu erstellen oder zu verwalten.



</div>

Beständige Chat Administratoren verwenden die lync Server Control Panel-oder Windows PowerShell-Cmdlets zum Erstellen und Verwalten von Kategorien sowie zum Entwerfen des Zugriffs für Chatrooms für die Benutzer in Ihrer Organisation.

Beständige Chatroom-Manager, die in der Lage sind, einen oder mehrere Chatrooms zu verwalten, können mithilfe des lync-Clients eine Webanwendung für die Raumverwaltung starten, um Räume zu erstellen und zu verwalten (oder Kunden können benutzerdefinierte Lösungen und Workflows erstellen, die aufgerufen werden sollen). Administratoren für beständigen Chat können auch die lync Server Control Panel-oder Windows PowerShell-Cmdlets verwenden, um Räume zu erstellen und zu verwalten.

<div>


> [!NOTE]  
> Ein beständiger Chatroom kann nicht den gleichen Namen wie die Kategorie "beständiger Chat" haben.



</div>

Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen. Die Kategorie des Chatrooms können Sie jedoch nicht ändern. Sie können nicht am Ausführen der folgenden Aktionen gehindert werden:

  - Deaktivieren eines Chatrooms

  - Ändern des Namens eines Chatrooms

  - Ändern der Beschreibung eines Chatrooms

  - Ändern des Chatroomtyps („Auditorium“ bzw. „Normal“)

  - Ändern des Datenschutzes eines Chatrooms (offen, geschlossen bzw. geheim)

  - Hinzufügen oder Entfernen von Mitgliedern

  - Hinzufügen oder Entfernen von Chatroommanagern

  - Hinzufügen oder Entfernen eines Add-Ins

  - Ändern von Einstellungen wie z. B. Einladungen (je nachdem, was durch die Kategorie zulässig ist)

<div>

## <a name="delegated-administration"></a>Delegierte Administration

Das Erstellen und verwalten beständiger Chatrooms ist mit der korrekten Verwendung von Kategorien viel einfacher. Ein beständiger Chat-Administrator kann **AllowedMembers** und **Creators** für jede Kategorie definieren und auch die Standardeinstellungen und-Verhaltensweisen für Chatrooms definieren, die auf alle Chatrooms angewendet werden, die in der Kategorie erstellt wurden. Beständige Chat Administratoren erstellen und verwalten Kategorien mithilfe der lync Server Control Panel-oder Windows PowerShell-Cmdlets.

Benutzer, Organisationseinheiten (Organizational Units, OUs) und Benutzergruppen, die als Ersteller einer Kategorie definiert werden, sind die einzigen Personen und Benutzergruppen, die Chatrooms in dieser Kategorie erstellen dürfen. Nachdem die Kategorie erstellt wurde, können sie Benutzer, Organisationseinheiten und Benutzergruppen in der Liste **Zugelassene Mitglieder** der Kategorie als Chatroommanager und Mitglieder auswählen, die den Chatroom verwalten und an diesem teilnehmen.

Chatrooms, die in einer Kategorie erstellt wurden, befolgen die Richtlinien und Einstellungen, die von der Kategorie erzwungen werden (beispielsweise wer in der Mitgliedschaft des Chatrooms sein kann, wer den Chatroom verwalten kann, ob Dateiuploads zulässig sind, ob Einladungen gesendet werden usw.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

