---
title: Erzwingen von Telefonsperren
TOCTitle: Erzwingen von Telefonsperren
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520963(v=OCS.15)
ms:contentKeyID: 49293388
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erzwingen von Telefonsperren

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Lync Phone Edition-Geräte können zu Sicherheitszwecken gesperrt werden. Wenn Sie die Telefonsperre erzwingen, wird das Gerät, auf dem Lync Phone Edition ausgeführt wird, nach einem von Ihnen konfigurierten Zeitraum gesperrt. Wenn ein Telefon gesperrt ist, kann ein Benutzer zwar Anrufe tätigen, jedoch nicht auf Kalender- und Kontaktinformationen, Voicemail und Anrufprotokolle zugreifen oder die Suche nutzen. Zum Entsperren des Telefons gibt der Benutzer eine PIN ein.

Zum Erzwingen der Telefonsperre wird diese mithilfe der Lync Server-Systemsteuerung oder mit Lync Server-PowerShell-Cmdlets konfiguriert. Sie können die Telefonsperre entweder global oder nur an dem Standort erzwingen, an dem sie konfiguriert ist.

## So konfigurieren Sie die Telefonsperre und erzwingen sie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Clients** und anschließend auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Einstellungen für die Telefonsperre Sie ändern möchten.

5.  Stellen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Gerätesperre erzwingen** aktiviert ist.

6.  Übernehmen Sie in **PIN-Mindestlänge** den Standardwert für die Mindestanzahl von Ziffern für die PIN zum Entsperren, oder geben Sie einen neuen Wert an. Der zulässige Bereich für die PIN-Länge umfasst vier bis 15 Stellen, der Standardwert ist sechs.

7.  Übernehmen Sie in **Telefonsperren-Timeout** den Standardwert für die Mindestlänge des Zeitraums bis zur Sperre des Telefons, oder geben Sie einen neuen Wert an. Der Bereich für das Timeout umfasst 0 bis 60 Minuten, der Standardwert ist 10. Geben Sie den Wert im Format HH:MM:SS ein.

8.  Klicken Sie auf **Commit**.

## Erzwingen der Telefonsperre mithilfe von Windows PowerShell-Cmdlets

Die Telefonsperre kann mithilfe des Cmdlets "Set-CsUCPhoneConfiguration" erzwungen werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie die Telefonsperre

  - Mit dem folgenden Befehl können Sie die Telefonsperre für den Standort Redmond aktivieren. Setzen Sie zum Deaktivieren der Telefonsperre die Eigenschaft "EnforcePhoneLock" auf "False" ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

## So aktivieren Sie die Telefonsperre und ändern das Telefonsperren-Timeout

  - Mit diesem Befehl wird die Telefonsperre aktiviert und das Timeout für die Telefonsperre auf 30 Minuten festgelegt.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## So aktivieren Sie die Telefonsperre in der gesamten Organisation

  - In diesem Beispiel ist die Telefonsperre für alle in der Organisation eingesetzten UC-Telefonkonfigurationseinstellungen aktiviert.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUCPhoneConfiguration).

## Siehe auch

#### Konzepte

[Verwalten der Lync Server 2013-Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

