---
title: Anzeigen von Konfigurationseinstellungen für Beprechungen
TOCTitle: Anzeigen von Konfigurationseinstellungen für Beprechungen
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49890951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Konfigurationseinstellungen für Beprechungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der Systemsteuerung für Lync Server 2013 bestimmen Sie mithilfe von Besprechungskonfigurationseinstellungen, wie Besprechungen in Ihrer Bereitstellung implementiert werden. Dies beinhaltet die folgenden Besprechungskonfigurationen:

  - Eine globale Konfiguration, die beim Bereitstellen von Lync Server 2013 standardmäßig erstellt wird.

  - Optionale Konfigurationen auf Standard- und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Besprechungen für bestimmte Standorte oder Benutzer implementiert werden.

## So zeigen Sie Besprechungskonfigurationseinstellungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.

5.  Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details einblenden**.
    
    **Besprechungskonfiguration bearbeiten – \<Richtlinie\>** wird mit den Einstellungen für die ausgewählte Richtlinie angezeigt. Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Besprechungen](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

## Anzeigen der Besprechungskonfigurationsinformationen mithilfe der Lync Server PowerShell-Cmdlets

Besprechungskonfigurationseinstellungen können auch mit Lync Server PowerShell und dem Get-CsMeetingConfiguration-Cmdlet angezeigt werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen der Besprechungskonfigurationsinformationen

  - Um Informationen zu allen Ihren Besprechungskonfigurationseinstellungen anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsMeetingConfiguration
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

Weitere Informationen finden Sie im Hilfethema für das [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)-Cmdlet.

