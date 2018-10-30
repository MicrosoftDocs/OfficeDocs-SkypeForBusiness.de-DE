---
title: 'Lync Server 2013: Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene'
TOCTitle: Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204731(v=OCS.15)
ms:contentKeyID: 49293379
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In der Systemsteuerung für Lync Server 2013 können Sie im Abschnitt **Konfiguration für Beständiger Chat** auf der Seite **Beständiger Chat** Einstellungen für Beständiger Chat global konfigurieren, die auf alle Serverpools für beständigen Chat oder einen bestimmten Serverpool für beständigen Chat angewendet werden.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## So konfigurieren Sie Beständiger Chat-Optionen global

1.  Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung anwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A>.



3.  Klicken Sie in der Navigationsleiste auf der linken Seite auf **Beständiger Chat** und dann auf **Konfiguration für Beständiger Chat**.

4.  Klicken Sie auf der Seite **Konfiguration für Beständiger Chat** auf **Neu** und dann auf **Standortkonfiguration** .
    

    > [!IMPORTANT]
    > Wählen Sie diese Option, wenn die Konfiguration auf alle Serverpools für beständigen Chat angewendet werden soll, die für den Standort bereitgestellt wurden. Klicken Sie auf <STRONG>Poolkonfiguration</STRONG> , falls die Konfiguration auf einen bestimmten Serverpool für beständigen Chat angewendet werden soll.



5.  Wählen Sie unter **Standort auswählen** den Standort aus, der für die Standortkonfiguration von Server für beständigen Chat konfiguriert werden soll.

6.  Gehen Sie unter **Neue Konfiguration für Beständiger Chat** folgendermaßen vor:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        

        > [!IMPORTANT]
        > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diesen Wert erhöhen, werden also mehr Nachrichten zwischengespeichert. Mit der Suchfunktion können Sie jederzeit auf die Verlaufsdaten zugreifen. Mit dem Standardwert wird lediglich die maximale Anzahl von Nachrichten angegeben, die nach dem Herstellen der Verbindung zu einem Chatroom angezeigt wird.

    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        

        > [!IMPORTANT]
        > Diese Einstellung wird auf dem Server erzwungen, weil benutzerdefinierte Anwendungen oder vorherige Gruppenchat-Clients ( Office Communications Server 2007 R2Gruppenchatserver oder Lync Server&nbsp;2010-Gruppenchat) Dateien in einem Chatroom bereitstellen können. Der Lync 2013-Client verfügt nicht über eine Funktion zum Hochladen und Herunterladen von Dateien. Falls Sie also über eine reine Lync 2013-Bereitstellung oder einen Lync 2013-Client verfügen, ist das Bereitstellen von Dateien in einem Chatroom von Server für beständigen Chat nicht möglich.

    
      - Unter **Teilnehmeraktualisierungsgrenze** wählen Sie den Grenzwert für Teilnehmeraktualisierungen aus. Server für beständigen Chat sendet Listeninformationen (Wer verfügt über eine Verbindung zum Chatroom?) an alle Teilnehmer, bis die Anzahl verbundener Benutzer diesen Wert erreicht. Der Standardwert lautet 75. Mit diesem Grenzwert wird die maximale Anzahl von Teilnehmern in einem Chatroom angegeben, nach dessen Erreichung Server für beständigen Chat keine Listeninformationen zur Anwesenheit von Teilnehmern im Chatroom mehr an verbundene Clients sendet.
    
      - (Optional). Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte benutzerdefinierte Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen. Nach dem Festlegen der URL wird diese sowohl als interne als auch als externe Raumverwaltungs-URL angewendet.
        
        Falls Sie die Raumerstellung anpassen und Ihren speziellen Unternehmensworkflow einbinden möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen. Verwenden Sie dazu das Software Development Kit (SDK) von Server für beständigen Chat, hosten Sie es an einem beliebigen Ort, und fügen Sie die URL hier ein. Diese URL wird an den Client gesendet, damit ein Benutzer an Ihre benutzerdefinierte Raumverwaltungslösung weitergeleitet wird, wenn er einen Raum anzeigen oder erstellen möchte.

7.  Klicken Sie auf **Commit** .

## So konfigurieren Sie Optionen von Beständiger Chat für einen bestimmten Serverpool für beständigen Chat

1.  Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein. Ausführliche Informationen zu den unterschiedlichen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A>.



3.  Klicken Sie in der Navigationsleiste auf der linken Seite auf **Beständiger Chat** und dann auf **Konfiguration für Beständiger Chat**.

4.  Klicken Sie auf der Seite **Konfiguration für Beständiger Chat** auf **Neu** und dann auf **Poolkonfiguration**.

5.  Wählen Sie unter **Dienst auswählen** den Dienst aus, der dem zu konfigurierenden Serverpool für beständigen Chat zugeordnet ist.

6.  Gehen Sie unter **Neue Konfiguration für Beständiger Chat** folgendermaßen vor:
    
      - Geben Sie unter **Name** einen Namen für die neuen Konfigurationseinstellungen an. Standardmäßig ist der Standortpoolname bereits vorhanden.
    
      - Definieren Sie unter **Standardchatverlauf** die Anzahl von Chatnachrichten, die für jeden Chatroom bei der ersten Anforderung verarbeitet werden. Der Standardwert lautet 30. Dies ist der globale Standardwert, und Administratoren können den Chatverlauf pro Kategorie deaktivieren.
        

        > [!IMPORTANT]
        > Der Server für beständigen Chat speichert diese Nachrichten im Arbeitsspeicher zwischen. Wenn Sie diesen Wert erhöhen, werden also mehr Nachrichten zwischengespeichert. Mit der Suchfunktion können Sie jederzeit auf die Verlaufsdaten zugreifen. Mit dem Standardwert wird lediglich die maximale Anzahl von Nachrichten angegeben, die nach dem Herstellen der Verbindung zu einem Chatroom angezeigt wird.

    
      - Wählen Sie unter **Maximale Dateigröße (KB)** die maximale Dateigröße für jeden Chatverlauf aus. Der Standardwert lautet 20 MB (20.000 KB). Dies ist die maximale Größe einer Datei, die in einen Chatroom des Systems hochgeladen werden kann (Dateiuploads werden jeweils über die Einstellung **Kategorie** aktiviert).
        

        > [!IMPORTANT]
        > Diese Einstellung wird auf dem Server erzwungen, weil benutzerdefinierte Anwendungen oder vorherige Gruppenchat-Clients ( Office Communications Server 2007 R2Gruppenchatserver oder Lync Server&nbsp;2010-Gruppenchat) Dateien in einem Chatroom bereitstellen können. Der Lync 2013-Client verfügt nicht über eine Funktion zum Hochladen und Herunterladen von Dateien. Falls Sie also über eine reine Lync 2013-Bereitstellung oder einen Lync 2013-Client verfügen, ist das Bereitstellen von Dateien in einem Chatroom von Server für beständigen Chat nicht möglich.

    
      - Unter **Teilnehmeraktualisierungsgrenze** wählen Sie den Grenzwert für Teilnehmeraktualisierungen aus. Server für beständigen Chat sendet Listeninformationen (Wer verfügt über eine Verbindung zum Chatroom?) an alle Teilnehmer, bis die Anzahl verbundener Benutzer diesen Wert erreicht. Der Standardwert lautet 75. Mit diesem Grenzwert wird die maximale Anzahl von Teilnehmern in einem Chatroom angegeben, nach dessen Erreichung Server für beständigen Chat keine Listeninformationen zur Anwesenheit von Teilnehmern im Chatroom mehr an verbundene Clients sendet.
    
      - Wählen Sie unter **Raumverwaltungs-URL** die Raumverwaltungs-URL aus. Dies ist die URL für die webbasierte Bereitstellung der Raumverwaltung. Wenn Sie die Raumverwaltung nicht anpassen müssen und lediglich die Standardeinstellung verwenden möchten, können Sie diese Option leer lassen.
        
        Falls Sie die Raumerstellung anpassen und Ihren speziellen Unternehmensworkflow einbinden möchten, können Sie eine benutzerdefinierte Raumverwaltungslösung erstellen. Verwenden Sie dazu das Software Development Kit (SDK) von Server für beständigen Chat, hosten Sie es an einem beliebigen Ort, und fügen Sie die URL hier ein. Diese URL wird an den Client gesendet, damit ein Benutzer an Ihre benutzerdefinierte Raumverwaltungslösung weitergeleitet wird, wenn er einen Raum anzeigen oder erstellen möchte.

7.  Klicken Sie auf **Commit** .

