---
title: Aktivieren oder Deaktivieren der Clientversionsverwaltung
TOCTitle: Aktivieren oder Deaktivieren der Clientversionsverwaltung
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898475(v=OCS.15)
ms:contentKeyID: 52056313
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren der Clientversionsverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Konfigurationseinstellungen für Clientversionen werden verwendet, um die Clientversionskontrolle entweder global oder für bestimmte Standorte zu aktivieren und zu deaktivieren. Die globale Clientversionskonfiguration wird zusammen mit Lync Server 2013 installiert und zum Aktivieren bzw. Deaktivieren der Clientversionskontrolle für die gesamte Serverbereitstellung verwendet. Wenn die globale Konfiguration aktiviert ist, werden alle eingerichteten Clientversionsrichtlinien bei der Anmeldung von Benutzern wirksam. Sie können die globale Clientversionskonfiguration deaktivieren, wenn Sie die Clientversionskontrolle nicht nutzen möchten. Sie können die Clientversionsverwaltung in der Systemsteuerung für Lync Server 2013 oder in der Verwaltungsshell für Lync Server 2013 aktivieren bzw. deaktivieren.


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



## So aktivieren oder deaktivieren Sie die Clientversionsverwaltung mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionskonfiguration**.

4.  Führen Sie Folgendes aus:
    
      - Zum globalen Aktivieren oder Deaktivieren der Clientversionsverwaltung doppelklicken Sie auf die Konfiguration **Global** und ändern dann die Einstellungen.
    
      - Zum Aktivieren oder Deaktivieren der Clientversionsverwaltung für einen bestimmten Standort klicken Sie auf **Neu**, wählen den Standort aus, klicken auf **OK** und ändern dann die Einstellungen für den Standort.

## Aktivieren oder Deaktivieren der Clientversionsverwaltung mithilfe von Windows PowerShell-Cmdlets

Sie können die Clientversionsverwaltung mithilfe des Cmdlets **Set-CsClientVersionConfiguration** aktivieren bzw. deaktivieren. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie die Clientversionsverwaltung

  - Sie können die Clientversionsverwaltung aktivieren, indem Sie die **Enabled**-Eigenschaft auf "True" ($True) festlegen.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## So deaktivieren Sie die Clientversionsverwaltung

  - Sie können die Clientversionsverwaltung deaktivieren, indem Sie die **Enabled**-Eigenschaft auf "False" ($False) festlegen.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

