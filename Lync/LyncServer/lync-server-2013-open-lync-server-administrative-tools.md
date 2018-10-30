---
title: Öffnen von Lync Server-Verwaltungstools
TOCTitle: Öffnen von Lync Server-Verwaltungstools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg195741(v=OCS.15)
ms:contentKeyID: 49294690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Öffnen von Lync Server-Verwaltungstools

 

_**Letztes Änderungsdatum des Themas:** 2012-06-28_

Mithilfe der Verfahren in diesem Thema können Sie Verwaltungstools für die Bereitstellung, Konfiguration oder Problembehandlung Ihrer Lync Server 2013-Topologie öffnen.

  - Bereitstellungs-Assistent

  - Topologie-Generator

  - Systemsteuerung für Lync Server 2013

  - Verwaltungsshell für Lync Server 2013

## Bereitstellungs-Assistent

Starten Sie mithilfe des folgenden Verfahrens den Bereitstellungs-Assistenten lokal, um Lync Server 2013-Komponentendateien hinzuzufügen oder zu entfernen.

## So starten Sie den Bereitstellungs-Assistenten für Lync Server 2013

1.  Melden Sie sich auf dem Computer, auf dem der Lync Server-Bereitstellungs-Assistent installiert ist, als Mitglied der Gruppen "Domänen-Admins" und "RTCUniversalServerAdmins" an.

2.  Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Microsoft Lync Server 2013** und anschließend auf **Lync Server-Bereitstellungs-Assistent**.

## Topologie-Generator

Öffnen Sie den Topologie-Generator mithilfe des folgenden Verfahrens, um die Server zu definieren, die in Ihrer Lync Server 2013-Topologie bereitgestellt werden sollen.

## So öffnen Sie den Topologie-Generator für Lync Server 2013 zum Entwerfen der Topologie

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    

    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Gruppe "Benutzer" ist. Zum Lesen, Veröffentlichen oder Aktivieren einer Topologie, die zum Installieren eines Servers mit Lync Server 2013 erforderlich ist, benötigen Sie jedoch ein Konto, das Mitglied der Gruppe "Domänen-Admins" sowie der Gruppe "RTCUniversalServerAdmins" ist und über Vollzugriffsberechtigungen (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Archivierungsdateispeicher verwenden, damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) konfigurieren kann. Alternativ dazu können Sie ein Konto mit entsprechenden Rechten verwenden .



2.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

## Systemsteuerung für Lync Server 2013

Öffnen Sie die Systemsteuerung für Lync Server 2013 mithilfe eines der folgenden Verfahren, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.


> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen wurde, um beliebige Aufgaben in Systemsteuerung für Lync Server 2013 auszuführen. Sie können andere Rollen verwenden, um sich bei Systemsteuerung für Lync Server 2013 anzumelden und spezifische Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise "CSArchivingAdministrator" für die Verwaltung der Archivierung in Systemsteuerung für Lync Server 2013 verwenden. Ausführliche Informationen zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Rollen, die zum Durchführen einer bestimmten Aufgabe verwendet werden können, finden Sie in der Dokumentation für die entsprechende Aufgabe.



## So öffnen Sie die Systemsteuerung für Lync Server 2013 von einem beliebigen Computer innerhalb der Firewall Ihrer Organisation

1.  Melden Sie sich über ein Benutzerkonto, das der Rolle "CsAdministrator" oder einer anderen Rolle mit den entsprechenden Rechten und Berechtigungen für die durchzuführende Aufgabe zugewiesen ist, bei einem beliebigen Computer in der internen Bereitstellung an.
    

    > [!IMPORTANT]
    > Wenn Sie eine einfache Admin-URL (Uniform Resource Locator) konfiguriert haben, können Sie von einem Internetbrowser, der auf einem beliebigen Computer innerhalb der Firewall Ihrer Organisation ausgeführt wird, auf Systemsteuerung für Lync Server 2013 zugreifen. Ausführliche Informationen zur Konfiguration der einfachen Admin-URL finden Sie unter <A href="lync-server-2013-planning-for-simple-urls.md">Planung für einfache URLs in Lync Server 2013</A> und unter <A href="lync-server-2013-edit-or-configure-simple-urls.md">Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013</A>.



2.  Öffnen Sie ein Browserfenster, und geben Sie die für Ihre Organisation konfigurierte Admin-URL ein.

## So öffnen Sie die Systemsteuerung für Lync Server 2013 auf einem Computer, auf dem Lync Server 2013 ausgeführt wird

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Rolle "sAdministrator" oder einer anderen Rolle mit den entsprechenden Rechten und Berechtigungen für die durchzuführende Aufgabe ist, auf einem Computer an, auf dem Lync Server 2013 oder mindestens die Verwaltungstools von Lync Server 2013 installiert sind. Zum Konfigurieren von Einstellungen muss der Computer eine Bildschirmauflösung von 1024x768 (Mindestanforderung) aufweisen.

2.  Starten Sie die Systemsteuerung für Lync Server 2013: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, zeigen Sie auf **Verwaltungstools**, zeigen Sie auf **Microsoft Lync Server 2013**, und klicken Sie dann auf **Systemsteuerung für Lync Server 2013**.

## Verwaltungsshell für Lync Server 2013

Öffnen Sie die Verwaltungsshell für Lync Server 2013 mithilfe des folgenden Verfahrens, um Server, Benutzer, Clients und Geräte in Ihrer Umgebung unter Verwendung der Befehlszeile zu verwalten.


> [!NOTE]
> Sie können ein Benutzerkonto verwenden, das der Rolle "CsAdministrator" zugewiesen wurde, um beliebige Aufgaben in Verwaltungsshell für Lync Server 2013 auszuführen. Melden Sie sich über andere Rollen an, um spezifische Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise "CSArchivingAdministrator" zum Ausführen von Cmdlets für die Archivierungsverwaltung verwenden. Ausführliche Informationen zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Rollen, die zum Ausführen eines bestimmten Cmdlets verwendet werden können, finden Sie in der Dokumentation für das entsprechende Cmdlet.<BR>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen "RTCUniversalServerAdmins", "RTCUniversalUserAdmins" oder "RTCUniversalReadOnlyAdmins" ausführen, abhängig vom Cmdlet.



## So öffnen Sie das Verwaltungsshell für Lync Server 2013

  - Wenn Sie anstelle der Verwaltungsshell für Lync Server 2013 ein Windows PowerShell-Fenster öffnen, können Sie in der Standardeinstellung keine Lync Server 2013-Cmdlets ausführen. Geben Sie zum Ausführen der Lync Server 2013-Cmdlets aus Windows PowerShell den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein:
    
    `Import-Module Lync`

  - Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

## Siehe auch

#### Aufgaben

[Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)  

#### Konzepte

[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)

