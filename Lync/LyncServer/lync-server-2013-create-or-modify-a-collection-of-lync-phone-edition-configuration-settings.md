---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Lync Phone Edition
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Lync Phone Edition
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49890784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Lync Phone Edition

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei der Installation von Lync Server erhalten Sie eine globale Auflistung der Lync Phone Edition-Einstellungen. Diese Einstellungen gelten für alle Geräte, auf denen Lync Phone Edition in Ihrer Bereitstellung ausgeführt wird. Sie können diese Einstellungen jederzeit ändern. Sie können auch eine neue Auflistung der Einstellungen einrichten, die für die Geräte an einem bestimmten Standort gelten. Standorteinstellungen haben Vorrang vor globalen Einstellungen.

Zu den Konfigurationseinstellungen zählen der Auflistungsname, der Geltungsbereich (global oder standortweit), die SIP-Sicherheitseinstellung, der Protokolliergrad, die Stufe der VoIP-Dienstqualität (QoS), das Einstellen der Telefonsperre sowie Details zur Telefonsperre, d. h., a) wie lang die Persönliche Identifikationsnummer (PIN-Nummer) sein muss, und b) nach wie viel Zeit im Ruhezustand das Telefon automatisch gesperrt wird.

## So erstellen Sie eine Auflistung der Lync Phone Edition-Konfigurationseinstellungen oder bearbeiten Einstellungen für eine vorhandene Aufstellung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Führen Sie auf der Seite **Gerätekonfiguration** einen der folgenden Schritte aus:
    
      - Um eine neue Auflistung von Lync Phone Edition-Konfigurationseinstellungen zu erstellen, klicken Sie auf **Neu**, wählen Sie einen Standort aus, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen und führen Sie gemäß Ihren Wünschen Änderungen durch.
    
      - Zum Bearbeiten von Einstellungen in einer vorhandenen Auflistung klicken Sie auf die Auflistung und dann auf das Menü **Bearbeiten**. Wählen Sie **Details anzeigen** und nehmen Sie Ihre Änderungen vor.
        

        > [!TIP]
        > Wenn Sie wieder die Standardeinstellungen für die globale Auflistung verwenden möchten, klicken Sie auf das Menü <STRONG>Bearbeiten</STRONG>, dann auf <STRONG>Löschen</STRONG> und schließlich auf <STRONG>OK</STRONG>. Hierdurch wird die globale Auflistung nicht gelöscht; die Einstellungen werden lediglich auf die Standardwerte zurückgesetzt.



5.  Klicken Sie auf **Commit**.

## So erstellen Sie neue Lync Phone Edition-Konfigurationseinstellungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können Lync Phone Edition-Konfigurationseinstellungen (nur auf Standortebene) auch mithilfe der Lync Server-Verwaltungsshell und des **New-CsUCPhoneConfiguration**-Cmdlets erstellen. Sie können dieses Cmdlet über Verwaltungsshell für Lync Server 2013 oder über eine Windows PowerShell-Remotesitzung ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie neue Lync Phone Edition-Konfigurationseinstellungen, die die Standardwerte verwenden

  - Über diesen Befehl wird ein neuer Satz mit Konfigurationseinstellungen für das UC-Telefon für den Standort in Redmond erstellt:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Da im vorstehenden Befehl (abgesehen vom obligatorischen Identity-Parameter) keine Parameter angegeben wurden, verwendet die neue Auflistung mit Konfigurationseinstellungen für alle enthaltenen Eigenschaften die Standardwerte.

## So ändern Sie bei der Erstellung neuer Lync Phone Edition-Konfigurationseinstellungen einen einzelnen Eigenschaftswert

  - Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für UC-Telefone zu erstellen, für die standardmäßig die Telefonsperre erforderlich ist, müssen Sie einen Befehl wie den folgenden verwenden:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## So ändern Sie bei der Erstellung neuer Lync Phone Edition-Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Der folgende Befehl beispielsweise erzwingt die Telefonsperre und legt gleichzeitig als minimale PIN-Länge 8 Ziffern fest:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

Ausführliche Informationen erhalten Sie unter [New-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUCPhoneConfiguration).

## Siehe auch

#### Aufgaben

[Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen von Telefonsperren](lync-server-2013-enforce-phone-locking.md)

