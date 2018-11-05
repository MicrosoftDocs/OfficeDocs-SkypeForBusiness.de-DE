---
title: Aktivieren oder Deaktivieren von Pushbenachrichtigungen für iPhones
TOCTitle: Aktivieren oder Deaktivieren von Pushbenachrichtigungen für iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49890827
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren von Pushbenachrichtigungen für iPhones

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein iPhone gesendet werden, auch wenn die mobile Anwendung inaktiv ist. Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Sofortnachrichteneinladungen und Voicemails. Pushbenachrichtigungen für iPhone können Sie aktivieren oder deaktivieren, indem Sie entweder Systemsteuerung für Lync Server 2013 oder Verwaltungsshell für Lync Server 2013 verwenden.

## So aktivieren Sie Pushbenachrichtigungen für iPhone aus Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Pushbenachrichtigungskonfiguration** auf den zu bearbeitenden Standort, klicken Sie dann auf das Menü **Bearbeiten** und dann auf **Details anzeigen**.

5.  Aktivieren Sie das Kontrollkästchen **Apple-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit ausführen**.

## So deaktivieren Sie Pushbenachrichtigungen für iPhone aus Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Pushbenachrichtigungskonfiguration** auf den zu bearbeitenden Standort, klicken Sie dann auf das Menü **Bearbeiten** und dann auf **Details anzeigen**.

5.  Deaktivieren Sie das Kontrollkästchen **Apple-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit ausführen**.

## So werden Pushbenachrichtigungen für iPhone mithilfe von Windows PowerShell-Cmdlets aktiviert bzw. deaktiviert

Sie können Pushbenachrichtigungen für Apple iPhone mithilfe des **Set-CsPushNotificationConfiguration**-Cmdlet aktivieren bzw. deaktivieren. Sie können dieses Cmdlet entweder über Verwaltungsshell für Lync Server 2013 oder über eine Remote-Sitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie Pushbenachrichtigungen für iPhone

  - Setzen Sie den Wert der Eigenschaft "EnableApplePushNotificationService" auf "True" ($True), um Pushbenachrichtigungen für iPhone zu aktivieren. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

## So deaktivieren Sie Pushbenachrichtigungen für iPhone

  - Setzen Sie den Wert der Eigenschaft "EnableApplePushNotificationService" auf "False" ($False), um Pushbenachrichtigungen für iPhone zu deaktivieren. Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

Weitere Informationen finden Sie im Hilfethema zum [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration)-Cmdlet.

## Siehe auch

#### Aufgaben

[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

