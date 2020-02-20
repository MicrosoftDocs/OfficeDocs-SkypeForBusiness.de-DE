---
title: 'Lync Server 2013: Konfigurieren von Kategorien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b808fff7a6356e437490a3f80a6f4f30b9a66801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Konfigurieren von Kategorien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Kategorie** der Seite für **beständigen Chat** verwenden, um Kategorien zu konfigurieren. Eine Kategorie für beständigen Chatroom ist eine logische Struktur zum Organisieren von Chatrooms. In einer Kategorie ist eine Standardgruppe von Zugriffssteuerungslisten (Access Control Lists, ACLs) zum Steuern der Benutzer und Benutzergruppen definiert, die zum Erstellen oder zum Beitreten zu Chatrooms berechtigt sind. Sie können Kategorien verwenden, um "Chinesische Mauern" zwischen verschiedenen Unterabteilungen der Organisationen einzurichten.

Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien. In jeder Kategorie wird der Inhalt mithilfe von Metadaten beschrieben, z. B. Name und Beschreibung. Zusätzlich verfügt die Kategorie über Eigenschaften, die festgelegt werden können, um das Verhalten der zur Kategorie gehörenden Chatrooms zu steuern, beispielsweise ob die Chatrooms Einladungen oder Dateiuploads zulassen oder einen Chatverlauf enthalten.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>So konfigurieren Sie Kategorien für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie**.
    
    Wählen Sie für mehrere Server Pool Bereitstellungen für beständigen Chat den entsprechenden Pool aus der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Kategorie** auf **Neu** oder **Bearbeiten**.

5.  Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem die Kategorie erstellt werden muss. Der Dienst ist der Server Pool für beständigen Chat, den der beständige Chat (Client) verwendet, um zu identifizieren, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur zu einem Server Pool für beständigen Chat gehören und kann nicht in einen anderen Pool verschoben oder in einen anderen Pool freigegeben werden.

6.  Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
    1.  Geben Sie unter **Name** einen Namen für die neue Chatroomkategorie an.
    
    2.  Geben Sie unter **Beschreibung** eine ausführliche Beschreibung der Chatroomkategorie an (z. B. eine Chatroomkategorie für Contoso).
    
    3.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** , um zu steuern, ob Einladungen für Chatrooms, die zu dieser Kategorie gehören, aktiviert werden können. Wenn diese Option aktiviert ist, können die Räume in dieser Kategorie Einladungen ein-oder ausschalten; Wenn diese Option deaktiviert ist, sind die Räume in dieser Kategorie nicht berechtigt, Einladungen zu erhalten. Wenn ein Raum Einladungen hat, wenn ein neues Mitglied einem Raum hinzugefügt wird, erhält er eine Benachrichtigung über den neuen Chatroom in seinem Client für beständigen Chat.
    
    4.  Um Dateiuploads in Chatrooms dieser Kategorie zu steuern, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren**. Ist diese Option aktiviert, können für die Chatrooms dieser Kategorie Dateiuploads aktiviert und deaktiviert werden. Ist die Option deaktiviert, sind Dateiuploads für die Chatrooms dieser Kategorie nicht zulässig.
        
        <div>
        

        > [!IMPORTANT]  
        > Diese Einstellung wird auf dem Server erzwungen, da benutzerdefinierte Anwendungen oder frühere Gruppenchatclients, die Office Communications Server 2007 R2&nbsp;Gruppenchatserver oder lync Server 2010 verwenden, Gruppenchat Dateien in einem Chatroom bereitstellen können. Der lync 2013-Client hat keine Dateiupload/Download-Funktion, wenn Sie also über eine reine lync 2013-Bereitstellung oder lync 2013-Client verfügen, ist es nicht möglich, Dateien in einem Chatroom für beständigen Chat Server bereitzustellen.

        
        </div>
    
    5.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **Chatverlauf aktivieren** , um Chatverlauf zu steuern. Wenn diese Option ausgewählt ist, werden Chatroom-Chats persistent; Andernfalls werden Chatnachrichten nicht dauerhaft gespeichert. Wenn die Kompatibilität aktiviert ist, werden Chatrooms in Übereinstimmung gespeichert, aber die Benutzer können nicht auf ältere Nachrichten zugreifen. Diese Option kann für Räume verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit vorgesehen sind und in denen kein Chatverlauf gespeichert werden muss.

7.  Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
      - Unter **Mitgliedschaft**können Sie im Abschnitt **zugelassene Mitglieder** Benutzer und andere Active Directory-Domänendienste Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.) hinzufügen oder entfernen, die als Mitglieder von Chatrooms hinzugefügt werden dürfen, die zur Kategorie gehören. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
      - Fügen Sie unter **Mitgliedschaft**im Abschnitt **Abgelehnte Mitglieder** Benutzer und andere Active Directory Prinzipale hinzu, die Mitgliedern verweigert werden, die aus dem Chatroom abgelehnt werden.
    
      - Fügen Sie unter **Mitgliedschaft**im Abschnitt **Ersteller** Benutzer und andere Active Directory Prinzipale hinzu, die Erstellern für die Kategorie zugeordnet sind. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.

8.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

