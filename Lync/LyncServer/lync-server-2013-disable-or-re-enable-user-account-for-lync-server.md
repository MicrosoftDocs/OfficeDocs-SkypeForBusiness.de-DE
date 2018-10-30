---
title: Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server
TOCTitle: Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429696(v=OCS.15)
ms:contentKeyID: 49293232
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2016-04-04_

Sie können mit dem folgenden Verfahren ein zuvor aktiviertes Benutzerkonto in Lync Server 2013 deaktivieren, ohne dass die für das Benutzerkonto konfigurierten Lync Server-Einstellungen verloren gehen. Da die Lync Server-Einstellungen für das Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne es neu konfigurieren zu müssen.

## So deaktivieren Sie ein Benutzerkonto für Lync Server oder aktivieren Sie ein zuvor aktiviertes Konto erneut

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6.  Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Vorübergehend für Lync Server deaktivieren**, um das Benutzerkonto vorübergehend für Lync Server 2013 zu deaktivieren.
    
      - Klicken Sie auf **Erneut für Lync Server aktivieren**, um das Benutzerkonto für Lync Server 2013 zu aktivieren.

## Deaktivieren und erneutes Aktivieren eines Benutzerkontos mithilfe von Windows PowerShell-Cmdlets

Benutzerkonten können mithilfe des Cmdlets **Set-CsUser** auch vorübergehend deaktiviert und später erneut aktiviert werden. Dieses Cmdlet kann entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Deaktivieren eines Benutzerkontos

  - Zum vorübergehenden Deaktivieren eines Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "False" ($False). Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

## Erneutes Aktivieren eines Benutzerkontos

  - Zum erneuten Aktivieren eines deaktivierten Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "True" ($True). Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser).

## Siehe auch

#### Aufgaben

[Hinzufügen und Aktivieren eines Benutzerkontos für Lync Server](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  

#### Weitere Ressourcen

[Aktivieren und Deaktivieren von Benutzern für Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

