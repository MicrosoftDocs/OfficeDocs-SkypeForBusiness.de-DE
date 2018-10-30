---
title: Konfigurieren von Sicherheitseinstellungen für Lync Phone Edition
TOCTitle: Konfigurieren von Sicherheitseinstellungen für Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521014(v=OCS.15)
ms:contentKeyID: 49294343
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Sicherheitseinstellungen für Lync Phone Edition

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Verbessern Sie über die SIP-Sicherheitseinstellung und Einstellungen für die Telefonsperre die Sicherheit der Geräte, auf denen Lync Phone Edition ausgeführt wird.

## So konfigurieren Sie Sicherheitseinstellungen für Lync Phone Edition

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Seite **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Sicherheitseinstellungen Sie ändern möchten.

5.  Geben Sie in **Gerätekonfiguration bearbeiten** in **SIP-Sicherheit** die SIP-Sicherheitsebene an. Die Standardebene, die auch empfohlen wird, lautet **Hoch**.

6.  Aktivieren oder deaktivieren Sie in **Gerätekonfiguration bearbeiten** unter **Telefonsperre** das Kontrollkästchen **Gerätesperre erzwingen** (standardmäßig ausgewählt), und geben Sie die minimale PIN-Länge (standardmäßig 6 Zeichen) und die Timeoutdauer (standardmäßig 10 Minuten) an. Es wird empfohlen, die genannten Standardwerte zu verwenden oder die PIN-Länge zu erhöhen bzw. die Timeoutdauer herabzusetzen.
    

    > [!NOTE]
    > Ausführliche Informationen erhalten Sie unter <A href="lync-server-2013-enforce-phone-locking.md">Erzwingen von Telefonsperren</A>.



## Konfigurieren der Sicherheitseinstellungen für Lync Phone Edition-Telefone mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Die Sicherheitseinstellungen können auch über die Lync Server-Verwaltungsshell und das **Get-CsUCPhoneConfiguration**-Cmdlet verwaltet werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So ändern Sie den SIP-Sicherheitsmodus

  - Der folgende Befehl legt für die Eigenschaft "SIPSecurityMode" für die globale Auflistung UC-Telefoneinstellungen "Mittel" fest. Die SIP-Sicherheit kann auch auf "Niedrig" oder "Hoch" (den Standardwert) gesetzt werden.
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## So ändern Sie die minimale PIN-Länge

  - In diesem Beispiel werden alle UC-Telefoneinstellungen so geändert, dass eine minimale PIN-Länge von sieben Ziffern erforderlich ist.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

Detaillierte Informationen finden Sie im Abschnitt [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Siehe auch

#### Konzepte

[Verwalten der Lync Server 2013-Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

