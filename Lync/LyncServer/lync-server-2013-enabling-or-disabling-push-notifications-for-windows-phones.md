---
title: Aktivieren oder Deaktivieren von Pushbenachrichtigungen für Windows Phones
TOCTitle: Aktivieren oder Deaktivieren von Pushbenachrichtigungen für Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49890873
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren von Pushbenachrichtigungen für Windows Phones

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können auch dann an ein Windows Phone gesendet werden, wenn die mobile Anwendung inaktiv ist. Mithilfe von Pushbenachrichtigungen wird ein Benutzer über Ereignisse wie eine neue oder verpasste Sofortnachrichteneinladung und Voicemai benachrichtigt. Sie können Pushbenachrichtigungen für Windows Phone-Geräte mit der Systemsteuerung für Lync Server 2013 oder der Verwaltungsshell für Lync Server 2013 aktivieren und deaktivieren.

## So aktivieren Sie Pushbenachrichtigungen für Windows Phone in der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Pushbenachrichtigungskonfiguration** auf den zu bearbeitenden Standort, klicken Sie auf das Menü **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren Sie das Kontrollkästchen **Microsoft-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit**.

## So deaktivieren Sie Pushbenachrichtigungen für Windows Phone in Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Pushbenachrichtigungskonfiguration** auf den zu bearbeitenden Standort, klicken Sie auf das Menü **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Deaktivieren Sie das Kontrollkästchen **Microsoft-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit**.

## So aktivieren und deaktivieren Sie Pushbenachrichtigungen für Windows Phone mithilfe der Windows PowerShell-Cmdlets

Mithilfe des Cmdlets **Set-CsPushNotificationConfiguration** können sie Pushbenachrichtigungen für Windows Phone aktivieren und deaktivieren. Die Ausführung dieses Cmdlets ist über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell möglich. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie Pushbenachrichtigungen für Windows Phone

  - Wenn Sie Pushbenachrichtigungen für Windows Phone aktivieren möchten, legen Sie den Wert der Eigenschaft "EnableMicrosoftPushNotificationService" auf "True" ($True) fest. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

## So deaktivieren Sie Pushbenachrichtigungen für Windows Phone

  - Wenn Sie Pushbenachrichtigungen für Windows Phone deaktivieren möchten, legen Sie den Wert der Eigenschaft "EnableMicrosoftPushNotificationService" auf "False" ($False) fest. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

Weitere Informationen dazu finden Sie im Hilfethema für das Cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## Siehe auch

#### Aufgaben

[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

