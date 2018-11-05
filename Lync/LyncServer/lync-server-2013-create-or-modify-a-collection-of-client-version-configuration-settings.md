---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898477(v=OCS.15)
ms:contentKeyID: 52056332
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Konfigurationseinstellungen für Clientversionen werden verwendet, um die Clientversionskontrolle zu aktivieren und zu deaktivieren. Die globale Clientversionskonfiguration wird zusammen mit Lync Server installiert und zum Aktivieren bzw. Deaktivieren der Clientversionskontrolle für die gesamte Serverbereitstellung verwendet. Sie können auch Konfigurationseinstellungen für Clientversionen für einzelne Standorte konfigurieren. Sie können Konfigurationseinstellungen für Clientversionen entweder in der Systemsteuerung für Lync Server 2013 oder in der Verwaltungsshell für Lync Server 2013 erstellen oder ändern.


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



## So erstellen oder ändern Sie Konfigurationseinstellungen für Clientversionen mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionskonfiguration**.

4.  Führen Sie auf der Seite **Clientversionskonfiguration** die folgenden Schritte aus:
    
      - Klicken Sie zum Erstellen einer neuen Konfiguration auf **Neu**, wählen Sie einen Standort aus, klicken Sie auf **OK**, und aktualisieren Sie die Einstellungen.
    
      - Wählen Sie eine Konfiguration aus, um sie zu ändern, klicken Sie auf **Bearbeiten** und auf **Details anzeigen**, und nehmen Sie dann Änderungen an den Einstellungen vor.

## Erstellen oder Ändern von Konfigurationseinstellungen für Clientversionen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen für Clientversionen mit dem Cmdlet **New-CsClientVersionConfiguration** erstellen und sie dann mit dem Cmdlet **Set-CsClientVersionConfiguration** ändern. Diese Cmdlets können Sie entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie eine neue Auflistung von Konfigurationseinstellungen für Clientversionen

  - Mit dem folgenden Befehl wird eine neue Auflistung von Konfigurationseinstellungen für Clientversionen erstellt, die auf den Standort Redmond angewendet wird. In diesem Beispiel ist die Clientversionsverwaltung für den Standort Redmond deaktiviert.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

## So aktivieren Sie die Clientversionsverwaltung für einen Standort

  - Mit diesem Befehl wird die Clientversionsverwaltung für den Standort Redmond aktiviert.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## So deaktivieren Sie die Clientversionsverwaltung in der gesamten Organisation

  - In diesem Beispiel ist die Clientversionsverwaltung für alle in der Organisation verwendeten Konfigurationseinstellungen für Clientversionen deaktiviert.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionConfiguration) und [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

