---
title: 'Lync Server 2013: Konfigurieren von Kategorien'
TOCTitle: Konfigurieren von Kategorien
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204859(v=OCS.15)
ms:contentKeyID: 49293856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Kategorien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In Systemsteuerung für Lync Server 2013 können Sie den Bereich **Kategorie** der Seite **Beständiger Chat** verwenden, um Kategorien zu konfigurieren. Eine Beständiger Chat-Chatroomkategorie ist eine logische Struktur zur Organisation von Chatrooms. Eine Kategorie definiert einen Standardsatz von Zugriffssteuerungslisten zur Kontrolle der Benutzer und Benutzergruppen, die Chaträume erstellen oder ihnen beitreten können. Sie können Kategorien verwenden, um Chinesische Mauern zwischen verschiedenen Unterteilungen innerhalb der Organisationen zu erzwingen.

Chatroomkategorien können Chatrooms enthalten, jedoch keine anderen Kategorien. Jede Kategorie beschreibt ihre Inhalte mit Metadaten wie *Name* und *Beschreibung* . Zusätzlich verfügt die Kategorie über Eigenschaften, die festgelegt werden können, um das Verhalten der zur Kategorie gehörenden Chatrooms zu steuern, beispielsweise ob die Chatrooms *Einladungen* oder *Dateiuploads* zulassen oder einen *Chatverlauf* enthalten.

## So konfigurieren Sie Kategorien für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im StartmenüLync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein. Informationen zu den verschiedenen Methoden zum Starten von Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A>.



3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Kategorie** .
    
    Bei Mehrfachbereitstellungen von Serverpool für beständigen Chat wählen Sie den entsprechenden Pool aus der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Kategorie** auf **Neu** oder auf **Bearbeiten** .

5.  Wählen Sie unter **Dienst auswählen** den Dienst aus, der dem Serverpool für beständigen Chat entspricht, auf dem die Kategorie erstellt werden soll. Der Dienst ist der Server für beständigen Chat-Pool, den der Beständiger Chat (Client) verwendet, um zu identifizieren, zu welchem Pool die Kategorie gehört. Eine Kategorie kann nur zu einem Serverpool für beständigen Chat gehören und kann nicht in einen anderen Pool verschoben oder gemeinsam mit einem anderen Pool genutzt werden.

6.  Führen Sie unter **Neue Kategorie** die folgenden Schritte aus:
    
    1.  Geben Sie unter **Name** einen Namen für die neue Raumkategorie an.
    
    2.  Geben Sie unter **Beschreibung** Einzelheiten über die Raumkategorie an (z. B. eine Raumkategorie für Contoso).
    
    3.  Um zu kontrollieren, ob Einladungen für Chatrooms in dieser Kategorie aktiviert werden können, aktivieren oder deaktivieren Sie das Kontrollkästchen **Einladungen aktivieren** . Wenn diese Option ausgewählt ist, können Einladungen für Chatrooms in dieser Kategorie aktiviert oder deaktiviert werden. Wenn sie nicht ausgewählt ist, sind für Chatrooms in dieser Kategorie keine Einladungen zulässig. Wenn die Einladungen für einen Raum aktiviert sind und ein neues Mitglied zu dem Raum hinzugefügt wird, erhält die Person eine Benachrichtigung über den neuen Raum in ihrem Beständiger Chat-Client.
    
    4.  Um Dateiuploads in Chatrooms in dieser Kategorie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Dateiupload aktivieren** . Wenn diese Option ausgewählt ist, können Sie für Räume in dieser Kategorie Dateiuploads aktivieren oder deaktivieren. Wenn sie nicht ausgewählt ist, sind für Räume in dieser Kategorie keine Dateiuploads zulässig.
        

        > [!IMPORTANT]
        > Diese Einstellung wird auf dem Server erzwungen, weil benutzerdefinierte Anwendungen oder vorherige Gruppenchat-Clients, die Office Communications Server 2007 R2Gruppenchatserver oder Lync Server&nbsp;2010-Gruppenchat verwenden, Dateien in einem Raum veröffentlichen können. Der Lync 2013-Client ist nicht zum Hoch- oder Herunterladen von Dateien fähig, daher ist es, wenn Sie eine reine Lync 2013-Bereitstellung oder einen Lync 2013-Client haben, nicht möglich, Dateien in einem Server für beständigen Chat-Chatroom zu veröffentlichen.

    
    5.  Um den Chatverlauf zu kontrollieren, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Chatverlauf aktivieren** . Wenn diese Option ausgewählt ist, werden Chats im Raum permanent. Andernfalls werden Chatnachrichten nicht beibehalten. Wenn die Kompatibilität aktiviert ist, werden Chats im Raum im Kompatibilitätsdienst gespeichert, Benutzer können jedoch nicht auf ältere Nachrichten zugreifen. Diese Option kann für Räume verwendet werden, die für die Ad-hoc-Zusammenarbeit in Echtzeit gedacht sind und bei denen kein Chatverlauf beibehalten werden muss.

7.  Führen Sie unter **Kategorie bearbeiten** die folgenden Schritte aus:
    
      - Unter **Mitgliedschaft** im Bereich **Zugelassene Mitglieder** können Sie Benutzer und andere Active Directory-Domänendienste-Prinzipale (Benutzer, Verteilergruppen, Organisationseinheiten usw.), die als Mitglieder von Chatrooms dieser Kategorie hinzugefügt werden können, hinzufügen oder entfernen. Prinzipale, die in einer Kategorie zugelassen sind, können nach den Räumen in der Kategorie suchen (es sei denn, der Raum ist ausgeblendet, in diesem Fall können nur Mitglieder des Raums im Verzeichnis danach suchen).
    
      - Unter **Mitgliedschaft** im Bereich **Nicht zugelassene Mitglieder** können Sie Benutzer und andere Active Directory-Prinzipale hinzufügen oder entfernen, die Mitgliedern zugeordnet sind, die für diesen Raum nicht zugelassen sind.
    
      - Unter **Mitgliedschaft** im Bereich **Ersteller** können Sie Benutzer und andere Active Directory-Prinzipale hinzufügen oder entfernen, die Erstellern dieser Kategorie zugeordnet sind. Ein Ersteller ist ein Benutzer, der Berechtigungen zum Erstellen von Chatrooms und zum Zuweisen von Chatroom-Managern und -mitgliedern besitzt.

8.  Klicken Sie auf **Commit** .

