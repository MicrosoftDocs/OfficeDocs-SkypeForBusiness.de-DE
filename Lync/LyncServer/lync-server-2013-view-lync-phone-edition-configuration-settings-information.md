---
title: Anzeigen von Informationen zu den Konfigurationseinstellungen für Lync Phone Edition
TOCTitle: Anzeigen von Informationen zu den Konfigurationseinstellungen für Lync Phone Edition
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49890638
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu den Konfigurationseinstellungen für Lync Phone Edition

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können Konfigurationsinformationen zu Geräten anzeigen, auf denen Lync Phone Edition ausgeführt wird. Die Informationen sind in Auflistungen angeordnet. Bei der Installation von Lync Server erhalten Sie eine Auflistung von Lync Phone Edition-Einstellungen, die Sie auf alle Geräte in Ihrer Bereitstellung anwenden, auf denen Lync Phone Edition ausgeführt wird. Sie können auch neuen Auflistungen von Einstellungen für einen bestimmten Standort erstellen. Standorteinstellungen haben Vorrang vor globalen Einstellungen. Jede Auflistung von Einstellungen besteht aus einem Namen, dem Bereich (global oder Standort), der SIP-Sicherheitseinstellung, dem Protokolliergrad, der VoIP-Dienstqualitätsebene, der Telefonsperreinstellung und Details zur Telefonsperre, d. h., die Mindestlänge der PIN zum Entsperren und die Zeit bis zur Sperrung des Telefons.

## So zeigen Sie Informationen zu Geräten an, auf denen Lync Phone Edition ausgeführt wird

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Klicken Sie auf der Seite **Gerätekonfiguration** auf die Auflistung von Einstellungen, zu der Sie Informationen anzeigen möchten. Der Name, der Bereich, die SIP-Sicherheitseinstellung, die VoIP-Qualitätsebene und die Telefonsperreinstellung werden auf der Hauptseite aufgeführt. Zum Anzeigen des Protokolliergrads und der Details zur Telefonsperre klicken Sie auf das Menü **Bearbeiten** und dann auf **Details anzeigen**.

## So zeigen Sie mithilfe der Lync Server-Verwaltungsshell-Cmdlets die Konfigurationsinformationen für Lync Phone Edition an

Sie können die Konfigurationseinstellungen für Lync Phone Edition auch mithilfe der Lync Server-Verwaltungsshell und des Cmdlets **Get-CsUCPhoneConfiguration** anzeigen. Sie können dieses Cmdlet in der Verwaltungsshell für Lync Server 2013 oder in einer Windows PowerShell-Remotesitzung ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Lync Phone Edition-Konfigurationsinformationen an

  - Zum Anzeigen von Informationen zu all Ihren Konfigurationseinstellungen für Lync Phone Edition geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken dann die EINGABETASTE:
    
        Get-CsUCPhoneConfiguration
    
    Der Befehl gibt ähnliche Informationen wie die Folgenden zurück:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Lync Phone Edition](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen von Telefonsperren](lync-server-2013-enforce-phone-locking.md)

