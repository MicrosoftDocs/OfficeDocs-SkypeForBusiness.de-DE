---
title: Deaktivieren eines Benutzers für Enterprise-VoIP
TOCTitle: Deaktivieren eines Benutzers für Enterprise-VoIP
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49890728
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deaktivieren eines Benutzers für Enterprise-VoIP

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Mit dem folgenden Verfahren können Sie Enterprise-VoIP für ein Benutzerkonto deaktivieren, das für Lync Server 2013 aktiviert wurde.

## So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** den Anzeigenamen, den Vornamen, den Nachnamen, den SAM (Security Accounts Manager)-Kontonamen, die SIP-Adresse oder die Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos teilweise oder vollständig ein, das Sie aktivieren möchten, und klicken Sie auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das für Enterprise-VoIP aktiviert werden soll.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.
    

    > [!NOTE]
    > Um einem Benutzer das Tätigen von Audio- oder Videoanrufen mit Lync zu untersagen, klicken Sie unter <STRONG>Telefonie</STRONG> auf <STRONG>Audio/Video deaktiviert</STRONG>.



8.  Klicken Sie auf **Commit**.

Die Funktion Enterprise-VoIP kann vom Benutzer jetzt nicht mehr verwendet werden.

## Siehe auch

#### Aufgaben

[Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  

#### Weitere Ressourcen

[Verwalten von Enterprise-VoIP für Benutzer](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md)

