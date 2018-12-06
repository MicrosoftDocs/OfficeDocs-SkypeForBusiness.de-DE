---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Lync Phone Edition
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Lync Phone Edition
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49890647
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Lync Phone Edition

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie für Geräte, auf denen Lync Phone Edition ausgeführt wird, eine Auflistung von Einstellungen nicht mehr verwenden möchten, löschen Sie die Auflistung. Wenn Sie eine Auflistung für einen Standort löschen, gelten die globalen Einstellungen für die Telefone an diesem Standort. Die globale Auflistung kann nicht gelöscht werden.


> [!NOTE]
> Anstatt eine Auflistung zu löschen, können Sie auch nur einige der Einstellungen ändern. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Lync Phone Edition</A>.



## So löschen Sie eine Auflistung von Lync Phone Edition-Konfigurationseinstellungen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Klicken Sie auf der Seite **Gerätekonfiguration** auf die Auflistung, die Sie löschen möchten, klicken Sie auf das Menü **Bearbeiten** und dann auf **Löschen**.
    

    > [!NOTE]
    > Wenn Sie die globale Auflistung löschen, werden die Einstellungen lediglich auf die Standardeinstellungen zurückgesetzt. Die Auflistung verschwindet nicht.



5.  Klicken Sie im Bestätigungsfeld auf **OK**.

## So entfernen Sie die Lync Phone Edition-Konfigurationseinstellungen mithilfe der Cmdlets der Lync Server-Verwaltungsshell

Sie können Lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell und des **Remove-CsUCConfiguration**-Cmdlets löschen. Dieses Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine bestimmte Auflistung von Lync Phone Edition-Konfigurationseinstellungen

  - Mit diesem Befehl werden die UC-Telefonkonfigurationseinstellungen gelöscht, die am Standort Redmond angewendet werden:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## So entfernen Sie alle Lync Phone Edition-Konfigurationseinstellungen, die auf Standortebene angewendet werden

  - Mit diesem Befehl werden alle UC-Telefoneinstellungen entfernt, die auf Dienstebene angewendet werden:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## So entfernen Sie alle Lync Phone Edition-Konfigurationseinstellungen, für die die Telefonsperre deaktiviert ist

  - Mit diesem Befehl werden alle Auflistungen von UC-Telefonkonfigurationseinstellungen gelöscht, für die die Telefonsperre deaktiviert wurde:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

Ausführliche Informationen finden Sie unter [Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration).

