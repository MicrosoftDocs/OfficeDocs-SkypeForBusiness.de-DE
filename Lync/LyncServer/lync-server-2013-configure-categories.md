---
title: 'Lync Server 2013: Konfigurieren von Kategorien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Konfigurieren von Kategorien in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In der lync Server 2013-Systemsteuerung können Sie auf der Seite "beständiger **Chat** " den Abschnitt " **Kategorie** " verwenden, um Kategorien zu konfigurieren. Eine beständige Chatroom-Kategorie ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen von oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um „Chinesische Mauern“ zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.

Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien. Jede Kategorie beschreibt ihren Inhalt mithilfe von Metadaten wie „Name“ und „Beschreibung“. Zusätzlich verfügt die Kategorie über Eigenschaften, die festgelegt werden können, um das Verhalten der zur Kategorie gehörenden Chatrooms zu steuern, beispielsweise ob die Chatrooms Invitations oder File Uploads zulassen oder einen Chat History enthalten.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter Konfigurieren des beständigen <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Chat Servers mithilfe von Windows PowerShell</A> -Cmdlets in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten**.

5.  Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, auf dem die Kategorie erstellt werden muss. Bei dem Dienst handelt es sich um den Server Pool für beständigen Chat, den der beständige Chat (Client) verwendet, um zu ermitteln, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur einem beständigen Chat Server Pool angehören und kann nicht in eine andere Gruppe verschoben oder für einen anderen Pool freigegeben werden.

6.  Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
    1.  Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
    2.  Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
    3.  Wenn Sie steuern möchten, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** . Wenn diese Option ausgewählt ist, können Chatrooms in dieser Kategorie möglicherweise Einladungen aktivieren oder deaktivieren. Wenn diese Option deaktiviert ist, dürfen die Räume in dieser Kategorie keine Einladungen haben. Wenn ein Raum Einladungen enthält, wenn ein neues Mitglied zu einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem beständigen Chat-Client.
    
    4.  Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder vorherige Gruppen-Chat-Clients, die den Office Communications&nbsp;Server 2007 R2-Gruppen-Chat Server oder lync Server 2010 verwenden, Gruppen-Chat Dateien in einem Raum bereitstellen können. Wenn Sie über eine reine lync 2013-Bereitstellung oder einen lync 2013-Client verfügen, ist der lync 2013-Client nicht in der Lage, Dateien in einem beständigen Chat Server-Chatroom zu Posten.

        
        </div>
    
    5.  Aktivieren oder deaktivieren Sie das Kontrollkästchen Chat- **Protokoll aktivieren** , um das Chat-Protokoll zu kontrollieren. Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls bleiben Chatnachrichten nicht erhalten. Wenn Compliance aktiviert ist, werden Chatroom-Chats unter Compliance gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen. Diese Option kann für Chatrooms verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und keine Beibehaltung des Chat-Verlaufs erforderlich machen.

7.  Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
      - Fügen Sie unter **Mitgliedschaft**im Abschnitt **zulässige Mitglieder** Benutzer und andere Active Directory-Domänendienst Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzu, die als Mitglieder von Chatrooms hinzugefügt werden dürfen. gehören zur Kategorie. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet; in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
      - Fügen Sie in der **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory-Prinzipale hinzu, die Mitgliedern zugeordnet sind, die aus dem Chatroom verweigert werden.
    
      - Fügen Sie unter **Mitgliedschaft**im **** Abschnitt Creators Benutzer und andere Active Directory-Prinzipale hinzu, die den Erstellern für die Kategorie zugeordnet sind. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.

8.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

