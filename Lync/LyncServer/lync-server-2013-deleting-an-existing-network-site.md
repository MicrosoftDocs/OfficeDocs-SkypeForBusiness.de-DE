---
title: Löschen eines vorhandenen Netzwerkstandorts
TOCTitle: Löschen eines vorhandenen Netzwerkstandorts
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49890673
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines vorhandenen Netzwerkstandorts

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die Systemsteuerung für Lync Server 2013 verwenden, um Standorte zu konfigurieren und Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. Über die Lync Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen vorhandenen Netzwerkstandort zu löschen. Details zum Erstellen oder Ändern von Netzwerkstandorten finden Sie unter [Erstellen oder Ändern von Netzwerkstandorten](lync-server-2013-creating-or-modifying-network-sites.md)

## So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]
    > Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>.


