---
title: Entfernen eines Benutzerkontos aus Lync Server
TOCTitle: Entfernen eines Benutzerkontos aus Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49890683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen eines Benutzerkontos aus Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Sie können das folgende Verfahren verwenden, um ein zuvor hinzugefügtes Benutzerkonto in Lync Server 2013 zu entfernen.


> [!NOTE]
> Durch das Entfernen eines Benutzers gehen alle Einstellungen verloren, die für das Benutzerkonto konfiguriert wurden. Sie können ein Benutzerkonto auch vorübergehend deaktivieren. Informationen hierzu finden Sie im Thema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server</A>.



## So entfernen Sie ein Lync Server-Benutzerkonto aus Lync Server

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6.  Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7.  Wählen Sie im Dialogfeld**OK** aus, um den Benutzer zu entfernen.

## Entfernen eines Benutzerkontos mithilfe von Lync Server-PowerShell-Cmdlets

Sie können Benutzerkonten auch mithilfe des Cmdlets **Disable-CsUser** entfernen. Sie können dieses Cmdlet entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung über Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Entfernen eines Benutzerkontos

  - Sie können das Cmdlet **Disable-CsUser** verwenden, um ein Benutzerkonto zu entfernen. Beispiel:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Nachdem dieser Befehl ausgeführt wurde, gibt es keine Möglichkeit, das Konto erneut zu aktivieren und die vorherigen Kontoeinstellungen wiederherzustellen. Stattdessen müssen Sie das Cmdlet **Enable-CsUser-** verwenden, um für Ken Myer ein ganz neues Konto zu erstellen.

Weitere Informationen finden Sie im Hilfethema für das [Disable-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsUser)-Cmdlet.

## Siehe auch

#### Aufgaben

[Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  

#### Weitere Ressourcen

[Aktivieren und Deaktivieren von Benutzern für Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

