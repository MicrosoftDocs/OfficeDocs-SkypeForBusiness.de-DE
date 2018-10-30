---
title: Anzeigen von Informationen zu Einstellungen für Pushbenachrichtigungen
TOCTitle: Anzeigen von Informationen zu Einstellungen für Pushbenachrichtigungen
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49890914
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Einstellungen für Pushbenachrichtigungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die mobile Anwendung inaktiv ist. Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail. Pushbenachrichtigungseinstellungen für mobile Geräte können Sie mithilfe der Systemsteuerung für Lync Server 2013 oder der Verwaltungsshell für Lync Server 2013 anzeigen.

## So zeigen Sie Pushbenachrichtigungsinformationen in der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Pushbenachrichtigungskonfiguration** auf die Site, die Sie anzeigen möchten. Klicken Sie dann im Menü **Bearbeiten** auf **Details einblenden**.

## So zeigen Sie Informationen zur Pushbenachrichtigungskonfiguration mithilfe der Windows PowerShell-Cmdlets an

Konfigurationseinstellungen für die Pushbenachrichtigung können Sie auch mit der Lync Server-Verwaltungsshell und dem **Get-CsPushNotificationConfiguration**-Cmdlet anzeigen. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Informationen zur Pushbenachrichtigungskonfiguration an

  - Um Informationen zu allen Ihren Konfigurationseinstellungen für die Pushbenachrichtigung anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsPushNotificationConfiguration
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

Weitere Informationen finden Sie im Hilfethema für das [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPushNotificationConfiguration)-Cmdlet.

## Siehe auch

#### Aufgaben

[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

